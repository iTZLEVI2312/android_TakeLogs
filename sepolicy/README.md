Make sure you're permissive.

1) adb logcat &> adb.log

2) Try to use things on your device such as the camera, FP sensor, and etc and press CTRL+C when you're done. If your device doesn't boot, then just let the command run for about 30 seconds and then press CTRL+C

3) grep -i "avc" adb.log &> selinux.log
