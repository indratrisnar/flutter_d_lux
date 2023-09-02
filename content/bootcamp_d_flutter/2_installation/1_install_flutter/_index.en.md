---
title: "1. Install Flutter"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "installation"]
---

Here will be shown the installation for those who use Windows OS only, complete and installation on other platforms can check this link: [Install | Flutter](https://docs.flutter.dev/get-started/install)

1. Download SDK Flutter channel stable, for now (15/05/2023) the new stable version is at v3.10 which coincides with the Google I/O 2023 event.

{{< image src="1_download_sdk_flutter.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

2. Extract and move the flutter content or folder to the system.

{{< image src="2_extract_flutter.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

3. Copy the flutter bin location to the environment variable. Free between user or system paths. Here I use the user path.

{{< image src="3_flutter_path.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

{{< image src="3_edit_var.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

4. Run flutter doctor in terminal or cmd. To run this command the first time it can take a long time, so you need to wait, but if it feels too long, for example after 10 minutes there is no change, you can try restarting cmd/terminal or the PC.

   Previously, I had installed Android Studio, VsCode, Visual Studio for the Windows platform so many people checked it. Except not for chrome because I don't have Chrome installed. For the first time installing Flutter, there are several configurations that must be set for the Android toolchain & Android SDK. For the agreement, there is information about what commands need to be executed.

   More about flutter doctor: [Windows install | Flutter](https://docs.flutter.dev/get-started/install/windows#run-flutter-doctor)

{{< image src="4_flutter_doctor.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

{{< image src="4_flutter_config_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

{{< image src="4_flutter_config_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

{{< image src="4_flutter_config_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

5. Check versions.

{{< image src="5_version.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
