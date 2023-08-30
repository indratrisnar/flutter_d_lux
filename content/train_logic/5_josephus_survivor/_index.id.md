---
title: "5. Josephus Survivor"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
# search related keywords
keywords:
  [
    "dart",
    "codewars",
    "array",
    "list",
    "mathematics",
    "combinatorics",
    "algorithms",
  ]
---

Dari: [Codewars](https://www.codewars.com/kata/555624b601231dc7a400017a/dart)

Dalam kata ini Anda harus mengembalikan dengan benar siapa yang "selamat", yaitu: elemen terakhir dari [Josephus permutation](http://www.codewars.com/kata/josephus-permutation/).

Pada dasarnya Anda harus berasumsi bahwa n orang dimasukkan ke dalam lingkaran dan mereka tersingkir dalam langkah k elemen, seperti ini:

```dart
n=7, k=3 => means 7 people in a circle
one every 3 is eliminated until one remains
[1,2,3,4,5,6,7] - initial sequence
[1,2,4,5,6,7] => 3 is counted out
[1,2,4,5,7] => 6 is counted out
[1,4,5,7] => 2 is counted out
[1,4,5] => 7 is counted out
[1,4] => 5 is counted out
[4] => 1 counted out, 4 is the last element - the survivor!
```

Tautan di atas tentang deskripsi kata "dasar" akan memberi Anda wawasan yang lebih menyeluruh tentang asal mula permutasi semacam ini, tetapi pada dasarnya hanya itu yang perlu diketahui untuk menyelesaikan kata ini.

Catatan dan tip: menggunakan solusi kata lain untuk memeriksa fungsi Anda mungkin membantu, tetapi karena angka yang digunakan jauh lebih besar, menggunakan array/daftar untuk menghitung jumlah orang yang selamat mungkin terlalu lambat; Anda mungkin berasumsi bahwa n dan k akan selalu >=1.

<br>

##### My Solution - [Other](https://www.codewars.com/kata/555624b601231dc7a400017a/solutions/dart)

```dart
int josephusSurvivor(int n, int k) {
  List arr = List.generate(n, (i) => i + 1);
  int i = 0;
  while (arr.length > 1) {
    i += k - 1;
    i = i < arr.length ? i : i % arr.length;
    arr.removeAt(i);
  }
  return arr.first;
}
```

<br>

##### Test

```dart
void main() {
  int n = 7;
  int k = 3;
  print(josephusSurvivor(n, k));
}

int josephusSurvivor(int n, int k) {
  List arr = List.generate(n, (i) => i + 1);
  int i = 0;
  while (arr.length > 1) {
    i += k - 1;
    i = i < arr.length ? i : i % arr.length;
    arr.removeAt(i);
  }
  return arr.first;
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
