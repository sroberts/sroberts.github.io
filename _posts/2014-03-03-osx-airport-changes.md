---
layout: post
title: OSX Airport Preferences Forensics
---

While doing some work on OSXAuditor, one of my favorite OSX incident response tools. Unfortunately when I started working with it I hit a quick snag.

When using the ```-a, --all``` (Analyze all (it is equal to -qsidbAkUe)) or ```-A, --airportprefs``` (Analyze Airport preferences) you hit a hard error, Python stacktrace and all:

This is all based on the line:

```python
PrintAndLog(u"SSID: " + RememberedNetwork["SSIDString"].decode("utf-8") + u" - BSSID: " + RememberedNetwork["CachedScanRecord"]["BSSID"] + u" - RSSI: " + str(RememberedNetwork["CachedScanRecord"]["RSSI"]) + u" - Last connected: " + str(RememberedNetwork["LastConnected"]) + u" - Security type: " + RememberedNetwork["SecurityType"] + u" - Geolocation: " + Geolocation, "INFO")
```

### com.apple.airport.preferenes.plist Format
```
Root
⌊ AirPortGlobalDebug (Number)
⌊ AirPortUserLandDebug (Number)
⌊ RememberedNetworks (Array)
  ⌊ Item 0 (Dictionary)
    ⌊ AutoLogin (Boolean)
    ⌊ Captive (Boolean)
    ⌊ Closed (Boolean)
    ⌊ Disabled (Boolean)
    ⌊ LastConnected (Date)
    ⌊ Passpoint (Boolean)
    ⌊ PossiblyHiddenNetwork (Boolean)
    ⌊ SPRoaming (Boolean)
    ⌊ SSID (Data)
    ⌊ SSIDString (String)
    ⌊ SecurityType (String)
    ⌊ SystemMode(Boolean)
    ⌊ TemporarilyDisabled (Boolean)
  ⌊ Item 1 (Dictionary)
  ⌊ Item ... (Dictionary)
  ⌊ Item n (Dictionary)  
⌊ Version (Number)
```

### Required
- "AutoLogin"
- "Captive"
- "Closed"
- "Disabled"
- "Passpoint"
- "PossiblyHiddenNetwork"
- "SPRoaming"
- "SSID"
- "SSIDString"
- "SecurityType"
- "TemporarilyDisabled"

### Optional
- "LastConnected"
- "SystemMode"

Dig in with:
> open /Library/Preferences/SystemConfiguration/com.apple.airport.preferences.plist