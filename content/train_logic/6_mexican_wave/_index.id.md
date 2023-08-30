---
title: "6. Mexican Wave"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
# search related keywords
keywords: ["dart", "codewars", "array", "string", "fundamental"]
---

Dari: [Codewars](https://www.codewars.com/kata/58f5c63f1e26ecda7e000029/dart)

##### Introduction

Gelombang (dikenal sebagai gelombang Meksiko di dunia berbahasa Inggris di luar Amerika Utara) adalah contoh ritme metachronal yang dicapai di stadion yang penuh sesak ketika sekelompok penonton berdiri sebentar, berteriak, dan mengangkat tangan. Segera setelah melakukan peregangan hingga ketinggian penuh, penonton kembali ke posisi duduk biasanya.

Hasilnya adalah gelombang penonton berdiri yang melintasi kerumunan, meskipun penonton individu tidak pernah beranjak dari tempat duduknya. Di banyak arena besar, penonton duduk di sirkuit yang berdekatan di sekeliling lapangan olah raga, sehingga gelombang dapat terus bergerak mengelilingi arena; dalam pengaturan tempat duduk yang tidak bersebelahan, gelombang malah dapat memantul ke depan dan ke belakang melalui kerumunan. Jika jarak tempat duduk sempit, gelombang terkadang dapat melewatinya. Biasanya hanya satu puncak gelombang yang akan muncul pada waktu tertentu di sebuah arena, meskipun gelombang-gelombang yang berputar balik secara simultan telah dihasilkan. (Sumber [Wikipedia](<https://en.wikipedia.org/wiki/Wave_(audience)>))

<br>

##### Tasks

Dalam Kata sederhana ini, tugas Anda adalah membuat fungsi yang mengubah string menjadi Gelombang Meksiko. Anda akan diberikan sebuah string dan Anda harus mengembalikan string tersebut dalam array yang huruf besarnya adalah orang yang berdiri.

<br>

##### Rules

1. String input akan selalu menggunakan huruf kecil tetapi mungkin kosong.
2. Jika karakter dalam string adalah spasi, lewati karakter tersebut seolah-olah itu adalah kursi kosong

<br>

##### Example

```dart
wave("hello") => {"Hello", "hEllo", "heLlo", "helLo", "hellO"}
```

<br>

##### My Solution - [Other](https://www.codewars.com/kata/58f5c63f1e26ecda7e000029/solutions/dart)

```dart
List<String> wave(String str) {
  List<String> list = [];
  for (var i = 0; i < str.length; i++) {
    if (str[i] == ' ') continue;
    list.add(str.replaceRange(i, i + 1, str[i].toUpperCase()));
  }
  return list;
}
```

<br>

##### Test

```dart
void main() {
  String str = 'hello';
  print(wave(str));
}

List<String> wave(String str) {
  List<String> list = [];
  for (var i = 0; i < str.length; i++) {
    if (str[i] == ' ') continue;
    list.add(str.replaceRange(i, i + 1, str[i].toUpperCase()));
  }
  return list;
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
