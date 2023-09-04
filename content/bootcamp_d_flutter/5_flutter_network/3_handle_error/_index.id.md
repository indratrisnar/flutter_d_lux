---
title: "3. Handle Error"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "api", "error"]
---

Untuk handle error di flutter network yang kaitannya dengan Future, bisa menggunakan 2 cara. Cara synchronous yaitu (**.then**, **catchError**/**onError**) dan cara asynchronous yaitu (**try**, **catch**). Untuk penerapannya bisa menggunakan source dari materi sebelumnya. Untuk cara synchronous kadang aman kadang masih terjadi freeze pada apliaksi yang running.

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Setelah di resume, app berjalan Kembali dan message error pindah ke console.

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Dengan cara asynchronous, semua kode yang berpotensi error dimasukkan di dalam block try, kemudian alternatif atau bisa solusi dimasukkan ke block catch. Dalam kode dibawah hanya menampilkan error saja ke console ketika terjadi error.

{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Dengan menggunakan block try-catch, terjadi error type int sebelumnya, app tidak freeze atau aman. Message error langsung ditampilkan ke console.

{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Handle respon status code:

Proses request yang sampai ke server nya bisa jadi request yang success, namun belum tentu dengan proses atau hasil response nya. Misal Ketika ingin update data, dan postId yang kita kirim sebagai kondisi index data post yang ingin diupdate ternyata tidak ditemukan di database sehingga response untuk updatenya gagal. Untuk cek hasil response, bisa menggunakan status code seperti dibawah.

{{< image src="5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="6.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="7.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Jika url nya salah, misal typo:

{{< image src="8.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="9.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="10.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
