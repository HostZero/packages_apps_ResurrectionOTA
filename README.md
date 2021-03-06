RecoveryOTA
-------
A very simple OTA checker with Android Settings look and feel.

How it works
------------
It parses the OTA xml file that you put in your file hosting and compares the version number with the local one.
If the version is newer, it notifies the user for a new ROM update.

How to use
----------
* Prepare the OTA xml file. Use this [template](https://github.com/HostZero/android_device_google_sprout/blob/cm-13.0/ota/ota.xml).
* Upload it to your file hosting and create a hot link of it
* Copy the ota_conf to the root of recovery source, as a text file called "ota_conf" (without the quotes)
* Replace the "ota_url" in ota_conf with your OTA xml hot link
* Check the xml template, and make your own, on your github, and place the resultant link to the raw file in the ota_conf
* If using the given samples, ota_conf is all setup! Else you will have to setup the version checking, etc.


### Most guys can skip the below part

Define how RecoveryOTA should know about the "version". The version must be parseable to a date.
Usually, the version is a part of a build name. For example, the 3.0.2-0 in the twrp-3.0.2-0-sprout.
Adjust the OTA configuration according to your build name on how should RecoveryOTA parse the version
Set the delimiter in "version_delimiter" to "-"
Set the date format in "version_format" to "yyyyMMdd"
Set the position in "version_position" to "4" (zero based)
Find a key in build.prop that represents your device name and set it in the "device_name"
RecoveryOTA will search this device name in the OTA xml file


Credits
-------
* [SlimRoms team](http://Slimroms.net/)
  * For the original idea of the SlimCenter and app icon
* [CommonsWare Android Components](https://github.com/commonsguy/cwac-wakeful)
  * For the wakeful intent service that is used in this app
