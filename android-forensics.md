# Android forensics

#### Syncing artifacts

**Google Docs**

```
/data/com.google.android.apps.docs.editors.docs/databases/*
```

**Google sheets**

```
/data/com.google.android.apps.docs.editors.sheets/databases/*
```

**Google slides**

```
/data/com.google.android.apps.docs.editors.slides/databases/*
```

**Google Docs**

```
/data/com.google.android.apps.docs/databases/* 
```

**Sync activity**

```
/data/com.google.android.apps.genie.geniewidget/databases/newsweather.db
```

**Sync activity - contacts**

```
/data/com.google.android.gms/databases/peoplelog.db
```

**Sync Activity**

```
/data/com.google.android.gms/shared_prefs/com.google.android.gms.auth.authzen.cryptauth.SyncManager.proximity_features.xml
```

#### Multimedia

**Traces to SD card used in the device. This is stored on the phone.**

```
/data/com.android.providers.media,module/databases/external.db
```

**Camera Photos information**

```
/data/com.google.android.apps.photos/databases/gphotos0.db
```

**Camera Photo - Samsung Devices**

```
/data/com.samsung.cmh/databases/cmh.db
```

```
/data/com.samsung.storyservice/databases/dme.db
```

```
/data/com.samsung.visionprovider/databases/visionprovider.dbwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwww
```

#### Browser artifact

The location relative to the user browser activity,\
Because the user can install a wide array of browsers. Which all store their internet history inside their own database. The best approach is to see what is installed on the device and examine the databases for information.

**Internet History**

```
/data/com.android.browser/app_databases/*
```

```
/data/com.android.browser/app_geolocation/GeolocationPermissions.db
```

```
/data/com.android.browser/databases/Browser.db
```

```
/data/com.android.browser/databases/browser2.db
```

```
/data/com.android.browser/databases/webview.db
```

```
/data/com.android.browser/databases/webviewCache.db
```

**Call logs**

```
/data/com.sec.android.provider.logsprovider/databases/logs.db
```

**SMS/MMS**

```
/data/com.google.android.gms/databases/icing_mmssms.db
```

```
/data/com.google.android.gms/databases/ipa_mmssms.db
```

**Gmail snippets**

```
/data/com.google.android.gm/databases/<mail-name>.db
```

conversations and messages

**Google+ Contacts**

```
/data/com.google.android.gms/databases/pluscontacts.db
```

**Android Pay**

Activity that has happened on google

```
/data/com.google.android.gms/databases/android_pay
```

**Maps**

Contains destination history, the columns of interest are:

* Time - Stored in UNIX Epoch
* dest\_lat - Destination latitude
* dest\_lng - Destination longitude
* dest\_title - street name, point of interest, etc.
* dest\_address = Can be mapped to the address in search\_history.db

```
/data/com.google.android.apps.maps/databases/da_destination_history
```

**files for installed applications**

The .dex/.oat/.art files used for installation

```
/dalvik-cache
```

appstate

```
/data/com.android.vending/databases/localappstate.db
```

**Google App searches installed applications and more**

```
/data/com.google.android.googlequicksearchbox/*
```

**Activity on device related to installed SIM (ICCID and Google Account included)**

```
/data/com.google.android.gms/shared_prefs/Checkin.xml
```

**password policy**

Stores the password policy for the device, which describes the type of password that is active on the device.

```
Device\_policies.xml
```

Active-password quality tag:

* Gesture or pattern = 65536
* Simple 4 digit pin = 131072
* Complex pin = 196608
* Alphabetic password = 262144
* alphanumerical password = 327680
* Complex password 393216

**Google Account Information**

```
/data/com.google.android.googlequicksearchbox/databases/app_icons.db
```

```
/data/com.google.android.googlequicksearchbox/databases/launcher.db
```

```
/data/com.google.android.googlequicksearchbox/databases/opa_history
```

**Wi-Fi Password**

```
/misc/wifi/wpa_supplicant.conf
```

**Wireless network**

```
/misc/wifi/WifiConfigStore.xml
```

**Cellular and WiFi**

```
/data/com.google.android.locations/files/cache.cell
```

```
/data/com.google.android.locations/files/cache.wifi
```

**USB Bluetooth NFC and other connects**

Connection is tracked here

```
/data/com.android.connectivity.metrics/databases/events.db
```

**Wireless network and MAC addresses**

Can be used to determine when Wifi or cellular is being used

```
/data/com.google.android.gms/databases/herrevad
```

**Lock settings**

```
/data/com.android.providers.settings/databases/locksettings.db
```

**Recent Tasks**

```
/system_ce/0/recent_tasks/*.xml
```

**Email accounts (backup)**

This contain information about email accounts used for 3rd party app.

```
/data/com.android.email/databases/EmailProvider.db
```
