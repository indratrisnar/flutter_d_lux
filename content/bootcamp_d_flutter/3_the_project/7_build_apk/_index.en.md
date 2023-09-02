---
title: "7. Build Apk"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "project", "apk"]
---

To export or build an app, you can use the IDEA of the relevant OS, such as Android Studio for Android apps (.apk) and Xcode for iOS apps (.ipa). Specifically for Android, you can use vscode and the terminal.

The build apk release or the compressed version can use the terminal. By running the command

`flutter build apk --split-per-abi` to create a compressed and released version of the apk. The results are stored in the build folder.

{{< image src="build.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

`flutter build apk –release` to create a release version apk without compressing it.

The full version of the build apk is on the Deployment section of the Flutter official website. While the full version of the Android build is at:
[https://docs.flutter.dev/deployment/android](https://docs.flutter.dev/deployment/android)

<br>
