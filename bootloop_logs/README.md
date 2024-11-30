just connect your phone to your pc via adb
open cmd in adb folder
reboot to recovery
mount system in twrp gui

type

adb shell mount -o rw,remount /system_root
adb pull /system_root/system/build.prop

u need to edit these lines in the prop.default file which you pulled via adb
Change value of the following props:
ro.secure=0
ro.debuggable=1
ro.adb.secure=0
persist.sys.usb.config=adb
ro.build.type=eng

then push the prop file with command adb push build.prop /system_root/system/

reboot and let your phone loop for 10 seconds after passing splash logo  
then you will be able to take logs via adb, just type adb logcat > logs.txt