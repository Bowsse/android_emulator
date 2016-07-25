# Android emulator

This repository contains a failed effort of running Appium tests with an android emulator in a single container.
The dockerfile and start script installs and starts android emulator and Appium server, and pulls latest version of Instapp and builds Instapp apk.

Appium was unable to control the emulator while running tests.

## Install Android SDK
```shell
cd /opt
wget https://dl.google.com/android/android-sdk_r24.4.1-linux.tgz
tar -xvzf android-sdk_r24.4.1-linux.tgz
rm android-sdk_r24.4.1-linux.tgz
ANDROID_HOME=/opt/android-sdk-linux
PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
echo y | android update sdk --no-ui --all --filter platform-tools,build-tools-23.0.2,tools,android-22,android-16,android-19,android-23,sys-img-armeabi-v7a-android-22 --force
echo | android create avd --force -n android -t android-22 --abi armeabi-v7a
```
