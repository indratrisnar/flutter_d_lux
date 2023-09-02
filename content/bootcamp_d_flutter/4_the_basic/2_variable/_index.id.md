---
title: "2. Variable"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "basic", "variable"]
---

Variable adalah tempat atau wadah yang mampu menampung suatu nilai. Nilai yang dapat ditampung beragam macam tergantung tipe variable tersebut. Variable di Dart bisa juga disebut objek dimana class nya adalah tipe data. Tipe variable akan dibahas di materi selanjutnya.

Sebelum menggunakan variable, variable perlu didaftarkan terlebih dahulu agar dikenali oleh compiler dan bisa di running. Mendaftarkan variable atau membuat variable sering disebut deklarasi variable.

Di bahasa pemrograman Dart terbaru, deklarai variable perlu didetail kan apakah ia dibolehkan tidak memiliki nilai atau wajib memiliki nilai. Hal ini karena terdapat update bahwa pemrograman sudah support null safety. Variable yang dibolehkan null disebut variable nullable, sedangkan yang wajib ada nilai disebut variable non-nullable atau required.

Dengan adanya null safety akan lebih mengamankan aplikasi tidak terjadi error/bug saat di release. Namun tidak full 100% karena kemungkinan banyak sumber yang terintegrasi dengan aplikasi yang sifatnya dynamic. Null Safety ini lebih ditekankan membantu pada saat ngoding, sehingga sebelum code decompile akan selalu dicek jika ada variable yang required dan nullable.

Syntax deklarasi variable.

```dart
tipeData number;
```

Syntax initialization variable dan memasukan nilai ke variable.

```dart
int number1 = 8;
int number2 = 6;

int? number3;
number3 = 23;

late int number4;
number4 = 50;
```

<br>
