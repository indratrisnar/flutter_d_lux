---
title: "2. Install Android Studio"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "installation", "android", "studio"]
---

Selengkapnya di Official documentation: [Windows install | Flutter](https://docs.flutter.dev/get-started/install/windows#android-setup)

1. Install Android Studio: [Download Android Studio & App Tools - Android Developers](https://developer.android.com/studio)

2. Setelah install, buka settings SDK manager.

{{< image src="2_sdk_manager.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

3. Install versi os yang dibutuhkan atau yang ingin diinginkan, untuk digunakan oleh emulator nantinya jika menggunakan emulator untuk running.

{{< image src="3_sdk_platform.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

4. Buka SDK Tools dan download/update seperti dibawah,SDK Platform Tools, Android SDK Build Tool dan Command Line wajib untuk developing Flutter for Android.

{{< image src="4_sdk_tools.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

5. Run `flutter doctor` untuk mengonfirmasi bahwa Flutter telah menemukan lokasi pemasangan Android Studio Anda. Jika Flutter tidak dapat menemukannya, run `flutter config --android-studio-dir=<directory>` untuk menyetel direktori tempat Android Studio diinstal.

6. Ikuti step selanjutnya, yang merupakan opsional. Khusus aggrement android license wajib, aka nada tips atau saran Ketika Flutter Doctor.

<br>
