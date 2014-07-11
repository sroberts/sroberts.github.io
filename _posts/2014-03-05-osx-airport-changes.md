---
layout: post
title: OSX Airport Preferences Forensics
---

I've been a huge fan of [@jipe_](https://twitter.com/Jipe_)'s [OSXAuditor](https://github.com/jipegit/OSXAuditor). In the limited  field of [OS X](http://www.apple.com/osx/) incident response tools OSXAudtior is the best quick triage tool out there. Unfortunately recently when I started working with I hit a quick snag.

![](/public/osxauditor-error.png)

When using the ```-a, --all``` (Analyze all) or ```-A, --airportprefs``` (Analyze Airport preferences) options in ```OSXAuditory.py``` you hit a hard error, Python stack trace and all.

This is all based on the line:

```python
PrintAndLog(u"SSID: " + RememberedNetwork["SSIDString"].decode("utf-8") + u" - BSSID: " + RememberedNetwork["CachedScanRecord"]["BSSID"] + u" - RSSI: " + str(RememberedNetwork["CachedScanRecord"]["RSSI"]) + u" - Last connected: " + str(RememberedNetwork["LastConnected"]) + u" - Security type: " + RememberedNetwork["SecurityType"] + u" - Geolocation: " + Geolocation, "INFO")
```

Yuck. Turns out this is attempting to parse ```com.apple.airport.preferenes.plist```. This is the [plist](https://developer.apple.com/library/mac/documentation/Darwin/Reference/Manpages/man5/plist.5.html) file that tracks stores information about a users wireless usage. Most interesting, this plist includes information about every saved wireless network a user has accessed in the ```RememberedNetworks``` array.

![](/public/wireless-plist.png)

The issue was clear pretty quickly (you likely already have a guess as a programmer). There was a change between OSX 10.8 and 10.9, including the removal of the ```BSSID``` & ```RSSI``` dictionary keys, which was clearly breaking that PrintAndLog statement.

I submitted a [Pull Request](https://github.com/jipegit/OSXAuditor/pull/8) (you always submit a PR when you find broken code right?) to OSXAuditor to fix the parsing error, but I was struck by how limited the information about many of these crucial plists.

Apple has a habit of not documenting things they don't intend for users such as private APIs, so the lack of official documentation isn't hard to believe. Even my go to guide,  [Mac OS X and iOS Internals by Jonathan Levin](http://www.wiley.com/WileyCDA/WileyTitle/productCd-1118057651.html) didn't offer any help. Here's my limited attempt to document ```com.apple.airport.preferences.plist```.

### com.apple.airport.preferences.plist format in OSX 10.9

At it's root this plist contains the following:

| Key | Datatype | Use | Notes |
| --- | -------- | --- | ----- |
| AirPortGlobalDebug | Number | Is the AirPort being debugged by root. | |
| AirPortUserLandDebug | Number | Is the AirPort being debugged by a user. | |
| RememberedNetworks | Array | The list of previously a  accessed wireless access points. | See below for RememberedNetwork item format. |
| Version | Number | | |

The ```RememberedNetworks``` array contains a number of dictionaries in the following format:

| Key | Datatype | Use | Notes |
| --- | -------- | --- | ----- |
| AutoLogin | Boolean | Is the profile for this network configured to automatically connect and auth? | |
| Captive | Boolean | Is there a captive portal for this AP? | |
| Closed | Boolean | I believe this indicates if the network is in use. | |
| Disabled | Boolean | ?? | |
| LastConnected | Date | Indicates the last time this AP was connected to. | This seems to be an optional item. |
| Passpoint | Boolean | Did this AP support [Passpoint](http://www.wi-fi.org/discover-wi-fi/wi-fi-certified-passpoint)?  | |
| PossiblyHiddenNetwork | Boolean | Is this AP is broadcasting it's SSID? | |
| SPRoaming | Boolean | Does the AP allow authentication to a [roaming SP consortium](http://www.wi-fi.org/system/files/20121010_Passpoint_r1_DP.pdf "see 3.1.3 Roaming Consortium List ANQP and Beacon Frame Elements")? | |
| SSID | Data | [Service Set Identification](http://en.wikipedia.org/wiki/Service_set_(802.11_network)) | |
| SSIDString | String | The wireless network name, one of the most useful items. | |
| SecurityType | String | WPA or WPA2? WEP or open? | |
| SystemMode | Boolean | [Supplicant mode](http://training.apple.com/pdf/WP_8021X_Authentication.pdf "see p.7 and p.19 first note") is System Mode? | |
| TemporarilyDisabled | Boolean | ??? | |

I have guesses on a few of the others, but no hard indications of their purpose.

### Going Further
If you want to look into this more the best place to start is digging into the plist itself. Just go to a Terminal and run the following:

> open /Library/Preferences/SystemConfiguration/com.apple.airport.preferences.plist

This will open Xcode's plist viewer. And be sure to let me know if you figure anything out.
