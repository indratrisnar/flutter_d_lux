---
title: "7. Josephus Permutation"
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
    "mathematic",
    "permutation",
    "algorithm",
    "combinatoric",
  ]
---

Dari: [Codewars](https://www.codewars.com/kata/5550d638a99ddb113e0000a2/dart)

Masalah ini mengambil namanya dari peristiwa paling penting dalam kehidupan sejarawan kuno Josephus: menurut kisahnya, dia dan 40 prajuritnya terjebak di sebuah gua oleh tentara Romawi selama pengepungan.

Menolak untuk menyerah kepada musuh, mereka malah memilih untuk bunuh diri massal, dengan sebuah perubahan: mereka membentuk lingkaran dan terus membunuh satu orang setiap tiga orang, sampai satu orang terakhir yang tersisa (dan mereka seharusnya bunuh diri untuk mengakhiri tindakan tersebut. ).

Ya, Josephus dan pria lain adalah dua orang terakhir dan, seperti yang kita ketahui sekarang setiap detail ceritanya, Anda mungkin sudah menebak dengan tepat bahwa mereka tidak benar-benar mengikuti ide aslinya.

Anda sekarang membuat fungsi yang mengembalikan permutasi Josephus, dengan mengambil parameter array/daftar item awal yang akan diijinkan seolah-olah berada dalam lingkaran dan menghitung setiap k tempat hingga tidak ada yang tersisa.

Kiat dan catatan: akan membantu jika Anda mulai menghitung dari 1 hingga n, bukan dari rentang biasa 0 hingga n-1; k akan selalu >=1.

Misalnya, dengan array=`[1,2,3,4,5,6,7]` dan k=`3`, fungsinya harus bertindak seperti ini.

```dart
[1,2,3,4,5,6,7] - initial sequence
[1,2,4,5,6,7] => 3 is counted out and goes into the result [3]
[1,2,4,5,7] => 6 is counted out and goes into the result [3,6]
[1,4,5,7] => 2 is counted out and goes into the result [3,6,2]
[1,4,5] => 7 is counted out and goes into the result [3,6,2,7]
[1,4] => 5 is counted out and goes into the result [3,6,2,7,5]
[4] => 1 is counted out and goes into the result [3,6,2,7,5,1]
[] => 4 is counted out and goes into the result [3,6,2,7,5,1,4]
```

Jadi hasil akhir kami adalah:

```dart
[3,6,2,7,5,1,4]
```

<br>

##### My Solution - [Other](https://www.codewars.com/kata/5550d638a99ddb113e0000a2/solutions/dart)

```dart
List josephus(final List items, final int k) {
  List list = [];
  int i = 0;
  while (items.isNotEmpty) {
    i += k - 1;
    i = i < items.length ? i : i % items.length;
    list.add(items.removeAt(i));
  }
  return list;
}
```

<br>

##### Test

```dart
void main() {
  List items = [1, 2, 3, 4, 5, 6, 7];
  int k = 3;
  print(josephus(items, k));
}

List josephus(final List items, final int k) {
  List list = [];
  int i = 0;
  while (items.isNotEmpty) {
    i += k - 1;
    i = i < items.length ? i : i % items.length;
    list.add(items.removeAt(i));
  }
  return list;
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
