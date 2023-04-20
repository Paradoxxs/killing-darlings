# Android RE

Every application is run in a virtual machine known as the Android runtime (ART).\
This is a modern translation layer from the application's bytecode to device instructions.\
Every app runs in its own sandbox.\
Likewise is the application file system, isolated by creating a new user unique for that application. The user is the owner of the application directory. And the UID of the user is between 10000 and 999999. Root user have system level accounts, there by access to all the application.

* /data/app/com.example.app - generic application data
* /data/data/com.example.app - runtime storage of data
* /mnt/sdcard/Android/data/com.example.app - externally stored location for runtime
* /data/data/com.example2.app - a different app requiring different user

This structure stop application from interacting with each other unless it explicitly granted, or a _Content provider/Broadcast receiver_ is exposed by the application.

### Android identity and access management

Profile separate app data from each profile. This can be very useful if the same phone is used for work and private.\
You can create two different profile that can not access each other application data.

Profiles types:

* Primary user is created the first time is booted, can only be removed by factory reset.
* Secondary user can be added to the device and be only be created and deleted by the primary user.
* Guest user only one is allowed at the time, it an fast way to have a guest access to an phone.

#### Java API layer

The view system is an utility for displaying the application UI and normalizing it the to the device screen.

The layer that allow the app to interact with the device and other application. How the application interact with other is defined in the AndroidManifest.xml.\
The method of sharing data between application is by exposing content provider.\ For other application to interact with the content service they must know the specific directory.

* content:///directory

Managers runs things like:

* Notification
* Telephon
* Package
* Location
