---
title: "3. Even Numbers in an Array"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
# search related keywords
keywords: ["dart", "logic", "codewars", "is even", "number", "array"]
---

Dari: [Codewars](https://www.codewars.com/kata/5a431c0de1ce0ec33a00000c/dart)

Diberikan array angka, kembalikan array baru dengan panjang angka yang berisi bilangan genap terakhir dari array asli (dalam urutan yang sama). Array asli tidak akan kosong dan akan berisi setidaknya "angka" bilangan genap.

##### Examples

([1, 2, 3, 4, 5, 6, 7, 8, 9], 3) => [4, 6, 8]\
([-22, 5, 3, 11, 26, -6, -7, -8, -9, -8, 26], 2) => [-8, 26]\
([6, -25, 3, 7, 5, 5, 7, -3, 23], 1) => [6]

<br>

##### My Solution - [Other](https://www.codewars.com/kata/5a431c0de1ce0ec33a00000c/solutions/dart)

```dart
List<int> evenNumbers(List<int> arr, int n) {
  List<int> list = [];
  for (int i = arr.length - 1; i >= 0; i--) {
    if (arr[i].isEven) list.add(arr[i]);
    if (list.length >= n) break;
  }
  return List.from(list.reversed);
}
```

<br>

##### Test

```dart
void main() {
  var array = [-22, 5, 3, 11, 26, -6, -7, -8, -9, -8, 26];
  int countEven = 2;
  print(evenNumbers(array, countEven));
}

List<int> evenNumbers(List<int> arr, int n) {
  List<int> list = [];
  for (int i = arr.length - 1; i >= 0; i--) {
    if (arr[i].isEven) list.add(arr[i]);
    if (list.length >= n) break;
  }
  return List.from(list.reversed);
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
