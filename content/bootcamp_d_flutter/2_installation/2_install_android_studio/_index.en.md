---
title: "2. Install Android Studio"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "installation", "android", "studio"]
---

More in the Official documentation: [Windows install | Flutter](https://docs.flutter.dev/get-started/install/windows#android-setup)

1. Install Android Studio: [Download Android Studio & App Tools - Android Developers](https://developer.android.com/studio)

2. After installation, open the SDK settings manager.

{{< image src="2_sdk_manager.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

3. Install the OS version that is needed or desired, to be used by the emulator later if you use the emulator to run.

{{< image src="3_sdk_platform.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

4. Open SDK Tools and download/update as below,SDK Platform Tools, Android SDK Build Tool and Command Line are mandatory for developing Flutter for Android.

{{< image src="4_sdk_tools.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

5. Run `flutter doctor` to confirm that Flutter has located your installation of Android Studio. If Flutter cannot locate it, run `flutter config --android-studio-dir=<directory>` to set the directory that Android Studio is installed to.

6. Follow the next step, which is optional. Especially for the mandatory Android license agreement, there will be tips or suggestions from Flutter Doctor.

<br>
