---
title: "5. Asset"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "project", "asset"]
---

Data - data yang akan digunakan diaplikasi didaftarkan terlebih dahulu dibagian identasi **assets** didalam `pubspec.yaml`. Yang didaftarkan di pubspec adalah lokasi file tersebut, bisa juga didaftarkan sebagai foldernya. Sedangkan untuk filenya langsung dimasukan ke project, biasanya dibungkus menggunakan folder asset.

Cara menambahkan file dan mendaftarkannya ke `pubspec.yaml`.

1. Klik di ruang kosong tepat di root project, kemudian klik new folder atau klik nanan-> new folder. Beri nama assets atau semisalnya.

{{< image src="1_1_project.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
{{< image src="1_2_folder.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

2. Klik kanan pada folder tersebut kemudian pilih **Reveal in File Explorer**. Maka akan otomatis membuka folder tersebut di file explorer.

{{< image src="2_reveal_file.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

3. Paste kan file.

{{< image src="3_paste.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

4. Kembali ke vscode, buka `pubspec.yaml`. dan daftarkan per-file ataupun daftarkan folder nya. Jika ada sub folder maka daftarkan juga subfoldernya. Untuk meringkas pendaftaran resource. Cukup daftarkan folder yang menampung file tersebut.

{{< image src="4_assets.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

5. Asset tinggal digunakan, cara penggunaannya tergantung tipe filenya. Namun untuk mengakses file tersebut cukup dengan menuliskan lokasi dan nama file nya dalam bentuk data string. Contohnya seperti dibawah untuk file image.

{{< image src="5_usage.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
