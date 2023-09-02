---
title: "1. Install Flutter"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "installation"]
---

Disini akan diperlihatkan instalasi untuk yang mengguankan OS Windows saja, selengkapnya dan instalasi di platfom lain bisa cek link ini: [Install | Flutter](https://docs.flutter.dev/get-started/install)

1. Download SDK Flutter channel stable, untuk saat ini (15/05/2023) versi new stable ada di v3.10 yang berbarengan dengan event Google I/O 2023.

{{< image src="1_download_sdk_flutter.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

2. Extrak dan pindahkan content atau folder flutter ke system.

{{< image src="2_extract_flutter.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

3. Copy location flutter bin ke environment variable. Bebas antara path user atau system. Disini saya gunakan path user.

{{< image src="3_flutter_path.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

{{< image src="3_edit_var.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

4. Run flutter doctor di terminal atau cmd. Untuk menjalankan perintah ini pertama kali bisa lama, jadi perlu tunggu namun jika dirasa terlalu lama misal lewat 10 menit tidak ada perubahan bisa coba restart cmd/terminal atau PC nya.

   Sebelumnya saya sudah pernah install Android Studio, VsCode, Visual Studio for windows platform sehingga banyak yang centang. Kecuali not for chrome karena saya tidak install Chrome. Untuk pertama kali install flutter, ada beberapa konfigurasi yang mesti di set untuk android toolchain & SDK android. Untuk aggrement terdapat informasi perintah apa yang perlu dijalankan.

   Selengkapnya tentang flutter doctor: [Windows install | Flutter](https://docs.flutter.dev/get-started/install/windows#run-flutter-doctor)

{{< image src="4_flutter_doctor.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

{{< image src="4_flutter_config_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

{{< image src="4_flutter_config_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

{{< image src="4_flutter_config_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

5. Cek version.

{{< image src="5_version.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
