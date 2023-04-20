# Windows forensics

## OneDrive

It is critical to check the registry to confirm the local file storage location&#x20;

• Metadata files only exist if OneDrive is enabled&#x20;

• SyncDiagnostics.log can sometimes contain file metadata&#x20;

• Some files are only stored in the cloud and will not be stored locally&#x20;

• Deleted items are stored in an online recycle bin for up to 30 days (personal) or 93 days (business)&#x20;

• OneDrive for Business Unified Audit Logs in Microsoft 365 provide 90 days of user activity logging

```
%USERPROFILE%\OneDrive
```

File storage folder location

```
NTUSER\Software\Microsoft\OneDrive\Accounts\<Personal | Business1>
```

File data metadata

```
%USERPROFILE%\AppData\Local\Microsoft\OneDrive\logs\<Personal | Business1>
```

* SyncDiagnostics.log
* SyncEngine “odl” logs

```
%USERPROFILE%\AppData\Local\Microsoft\OneDrive\settings\<Personal | Business1> <UserCid>.dat
```

## Google Drive for Desktop

It uses a virtual FAT32 volume named “My Drive”, which is only accessible to the user when they are logged in.

The assigned drive letter can help tie file and folder access artefacts to Google Drive&#x20;

• Google Workspace Admin Reports provide 180 days of user activity logging&#x20;

• metadata\_sqlite\_db database uses protobuf format for many important fields

Local drive letter for the virtual volume and account ID

```
NTUSER\Software\Google\DriveFS\Share\
```

Default local file cache

```
%USERPROFILE%\AppData\Local\Google\DriveFS\<account
identifier>\content_cache
```

File metadata

```
%USERPROFILE%\AppData\Local\Google\DriveFS\<account
identifier>\metadata_sqlite_db
```

## Dropbox

Default local file storage

```
%USERPROFILE%\Dropbox
```

```
%USERPROFILE%\Dropbox\.dropbox.cache (up to 3 days of cached data)
```

File storage folder location

```
SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\SyncRootManager\Dropbox!<SID>!Personal\UserSyncRoots
```

File metadata and configuration data

```
%USERPROFILE%\AppData\Local\Dropbox\
```

* nucleus.sqlite3, sync\_history.db, and aggregation.dbx – usage and file

## File execution

### System resource usage monitor (SRUM)

Records 30 to 60 days of historical system performance. And what applications which ran during the time frame. This also included the account used for execution and bytes sent/received. This data is stored per hour for every application.

The location for the SRUM database:

```
C:\Windows\System32\SRU\SRUDB.dat
```

Tools Use tools such as srum-dump.exe can be used to cross-correlate the data between the registry keys and the SRUM ESE Database.

* Nirsoft
* Scrum-dump
* scrumMonkey

## Event log

Common event logs:

| Event ID           | log source                                         | description                                      |
| ------------------ | -------------------------------------------------- | ------------------------------------------------ |
| **Remote desktop** |                                                    |                                                  |
| 4778 & 4779        | Security                                           | Remote desktop                                   |
| **Kerberos**       |                                                    |                                                  |
| 4768               | Security                                           | Kerbous TGT was granted (successful logon)       |
| 4769               | Kerbous Service ticket requested                   |                                                  |
| 4771               | Security                                           | Kerbous Pre-authentication failed (failed logon) |
| **Network share**  |                                                    |                                                  |
| 5140               | Security                                           | Network share was accessed, off by default       |
| 5145               | Shared object accessed                             |                                                  |
| **Service**        |                                                    |                                                  |
| 7035               | Service                                            | Service sent a start or stop control             |
| 7036               | Service start or stop                              |                                                  |
| 7040               | Start type changed                                 |                                                  |
| 7045               | Service                                            | new service installed                            |
| **WLAN**           |                                                    |                                                  |
| 11000              | Microsoft-Windows-WLAN-AutoConfig Operational.evtx | wireless network association started             |
| 8001               | Microsoft-Windows-WLAN-AutoConfig Operational.evtx | Successful connection to wireless network        |
| 8002               | Microsoft-Windows-WLAN-AutoConfig Operational.evtx | Failed connection to wireless network            |
| 8003               | Microsoft-Windows-WLAN-AutoConfig Operational.evtx | Disconnect from wireless network                 |
| 6100               | Microsoft-Windows-WLAN-AutoConfig Operational.evtx | Network diagnostics                              |
| **Logon activity** |                                                    |                                                  |
| 4624               | security                                           | Successful logon                                 |
| 4625               | security                                           | Failed logon                                     |
| 4634               | security                                           | Successful logoff                                |
| 4648               | security                                           | logon using explicit cred (RunAs)                |
| 4672               | Account logon with superuser right (admin)         |                                                  |
| 4720               | security                                           | Account created                                  |
| **Plug and play**  |                                                    |                                                  |
| 200001             | System                                             | Plug and play driver install attempted           |
| **Scheduled task** |                                                    |                                                  |
| 4698               | Security                                           |                                                  |
| 106                | Task scheduler                                     |                                                  |
| 141                | Task scheduler                                     |                                                  |
| 200                | Task scheduler                                     |                                                  |

**AppCompatCache - Shimcache**

**With windows 10 it can no longer be used to identify file execution**

Windows application compatibility database is used by Windows to identify possible application compatibility challenges when executing PE files. Execution files get shimmed as soon as they hit the disk. If the executable is moved, rename or modified, the executable gets re-shimmed by the system, adding new entries into shimcache database. Any executable that has existed on the system can be found in this key. It should be noted that it does not get instantly get written to the register. It only gets written to the database when the system reboots, until that it only lives within memory. AppCompatCache also stores the timestamp for when the file was last modified. When it comes to malware it can be used to track any executable that has hit the disk. Even if deleted, renamed, etc. the entry will still be there.

With Windows XP there were at most 96 entries and LastUpdateTime is updated when the file was executed.\
As of Win 7+, the entries were increased to 1,024. _LastUpdateTime_ is replaced with an execution flag, This means it can no longer be used to determine the last execute time. Only if the exceptionable was run or not. When it comes to system files such as _cmd_, _regedit_, etc they first get shimmed at the time of execution.

Stored the following information on executable:

* File path
* Last modification date
* File size
* Executed

It possible to analysis the appcombatcache using Eric Zimmerman tool _AppCombatCacheParser_, it only need three parameters the source of the system file and the output type and directory.

```
AppCombatCacheParser --csv .\ -f .\SYSTEM
```

Tools:

* AppCompatCacheParser
* ShimCacheParser.py

Win7+:

```
HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache  
```
