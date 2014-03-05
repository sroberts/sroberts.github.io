---
layout: post
title: OSX Airport Preferences Forensics
---

While doing some work on OSXAuditor, one of my favorite OSX incident response tools. Unfortunately when I started working with it I hit a quick snag.

When using the ```-a, --all``` (Analyze all (it is equal to -qsidbAkUe)) or ```-A, --airportprefs``` (Analyze Airport preferences) you hit a hard error, Python stacktrace and all:

TODO: Add stack trace picture

This is all based on the line:

```python
PrintAndLog(u"SSID: " + RememberedNetwork["SSIDString"].decode("utf-8") + u" - BSSID: " + RememberedNetwork["CachedScanRecord"]["BSSID"] + u" - RSSI: " + str(RememberedNetwork["CachedScanRecord"]["RSSI"]) + u" - Last connected: " + str(RememberedNetwork["LastConnected"]) + u" - Security type: " + RememberedNetwork["SecurityType"] + u" - Geolocation: " + Geolocation, "INFO")
```

Yuck right? This is all an attempt to parse ```com.apple.airport.preferenes.plist```. This is the file that tracks stores information about a users wireless usage. Most interesting, this plist includes information about every saved wireless network a user has accessed in the ```RememberedNetworks``` array.

The issue was clear pretty quickly (you likely already have a guess as a programmer). There was a change between OSX 10.8 and 10.9, including the removal of the ```BSSID``` & ```RSSI``` dictionary keys, which was clearly breaking that PrintAndLog statement.

I submitted a [Pull Request](https://github.com/jipegit/OSXAuditor/pull/8) (you always submit a PR when you find broken code right?) to OSXAuditor to fix the parsing error, but I was struck by how limited the information about many of these crucial plists. Apple has a habit of not documenting things they don't intend for users such as private APIs, so the lack of official documentation isn't hard to believe. Even my go to guide,  Mac OS X and iOS Internals by Jonathan Levin didn't offer any help. Here's my limited attempt to document ```com.apple.airport.preferences.plist```.

### com.apple.airport.preferences.plist format in OSX 10.9

```
Root
⌊ AirPortGlobalDebug (Number)
⌊ AirPortUserLandDebug (Number)
⌊ RememberedNetworks (Array)
  ⌊ Item 0 (Dictionary)
    ⌊ AutoLogin (Boolean) - ??
    ⌊ Captive (Boolean) - ??
    ⌊ Closed (Boolean) - I believe this indicates if the network is in use
    ⌊ Disabled (Boolean) - ??
    ⌊ LastConnected (Date) - Optional: Indicates the last time this AP was connected to
    ⌊ Passpoint (Boolean) - ???
    ⌊ PossiblyHiddenNetwork (Boolean) - Is this AP is broadcasting it's SSID?
    ⌊ SPRoaming (Boolean) - ???
    ⌊ SSID (Data) - [Service Set Identification](http://en.wikipedia.org/wiki/Service_set_(802.11_network))
    ⌊ SSIDString (String) - The wireless network name, one of the most useful items
    ⌊ SecurityType (String) - WPA or WPA2? WEP or open?
    ⌊ SystemMode(Boolean) - ???
    ⌊ TemporarilyDisabled (Boolean) - ???
  ⌊ Item 1 (Dictionary)
  ⌊ Item ... (Dictionary)
  ⌊ Item n (Dictionary)  
⌊ Version (Number)
```

### Going Further
If you want to look into this more the best place to start is digging into the plist itself. Just go to a Terminal and run the following:

> open /Library/Preferences/SystemConfiguration/com.apple.airport.preferences.plist

This will open Xcode's plist viewer. And be sure to let me know if you figure anything out.