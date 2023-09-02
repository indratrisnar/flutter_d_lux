---
title: "7. Build Apk"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "project", "apk"]
---

Untuk export atau build app bisa menggunakan IDEA os bersangkutan seperti Android Studio untuk android app (.apk) dan Xcode untuk ios app (.ipa). Khusus android bisa menggunakan vscode dan terminal.

Build apk release maupun dengan yang versi compressnya bisa menggunakan terminal. Dengan menjalankan perintah

`flutter build apk --split-per-abi` untuk create apk versi release dan dicompress. Hasilnya disimpan di build folder.

{{< image src="build.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

`flutter build apk –release` untuk create apk versi release tanpa dicompress.

Versi lengkap build apk ada di web official Flutter bagian Deployment. Sedangkan versi lengkap build android ada di:
[https://docs.flutter.dev/deployment/android](https://docs.flutter.dev/deployment/android)

<br>
