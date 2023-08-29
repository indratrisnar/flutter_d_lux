---
title: "1. Descending Order"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
keywords: ["dart", "logic", "codewars", "descending", "order"]
---

Dari: [Codewars](https://www.codewars.com/kata/5467e4d82edf8bbf40000155/train/dart)

Tugas Anda adalah membuat fungsi yang dapat menggunakan bilangan bulat non-negatif apa pun sebagai argumen dan mengembalikannya dengan digitnya dalam urutan menurun. Intinya, atur ulang angka-angka tersebut untuk menghasilkan angka setinggi mungkin.

##### Examples

Input: `42145`, Output: `54421`

Input: `145263`, Output: `654321`

Input: `123456789`, Output: `987654321`

<br>

##### My Solution - [Other](https://www.codewars.com/kata/5467e4d82edf8bbf40000155/solutions/dart)

```dart
int descendingOrder(int n) {
  List<String> list = '$n'.split('');
  list.sort((a,b)=>b.compareTo(a));
  return int.parse(list.join(''));
}
```

<br>

##### Test

```dart
void main() {
  var input = 23787923;
  print(descendingOrder(input));
}

int descendingOrder(int n) {
  List<String> list = '$n'.split('');
  list.sort((a,b)=>b.compareTo(a));
  return int.parse(list.join(''));
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
