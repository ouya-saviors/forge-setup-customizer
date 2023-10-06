Razer Forge TV setup customization
==================================
System app that lets you skip Google sign-in during the initial
Razer Forge TV setup.


Installation
------------
1. Use ``fastboot`` to boot a fastboot-enabled twrp so we have unrestricted
   ``adb`` root access.
2. Mount the ``/system`` partition::

     $ adb shell
     $ mount -t ext4 /dev/block/platform/msm_sdcc.1/by-name/system /system

3. Create the app directory::

     $ mkdir /system/priv-app/ForgeSetupCustomizer
4. Install the setup customization::

     $ adb push ForgeSetupCustomizer.apk /system/priv-app/ForgeSetupCustomizer/
     $ adb reboot

Now the welcome message is "Welcome savior!" instead of "Welcome",
and Google Sign-In can be skipped.



Notes
-----
Based upon
https://android.googlesource.com/device/sample/+/android-6.0.1_r81/apps/SetupCustomizer/
