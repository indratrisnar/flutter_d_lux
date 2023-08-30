---
title: "8. Consecutive Strings"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
keywords: ["dart", "codewars", "array", "fundamental"]
---

Dari: [Codewars](https://www.codewars.com/kata/56a5d994ac971f1ac500003e/dart)

Anda diberi array(daftar) strarr string dan bilangan bulat k. Tugas Anda adalah mengembalikan string terpanjang pertama yang terdiri dari k string berurutan yang diambil dalam array.

##### Example

```dart
strarr = ["tree", "foling", "trashy", "blue", "abcdef", "uvwxyz"], k = 2

Gabungkan string strarr yang berurutan dengan 2, kita mendapatkan:

treefoling    (panjang 10) rangkaian strarr[0] dan strarr[1]
folingtrashy  ("       12) rangkaian strarr[1] dan strarr[2]
Trashyblue    ("       10) rangkaian strarr[2] dan strarr[3]
blueabcdef    ("       10) rangkaian strarr[3] dan strarr[4]
abcdefuvwxyz  ("       12) rangkaian strarr[4] dan strarr[5]

Dua string yang terpanjang: "folingtrashy" dan "abcdefuvwxyz".
Yang pertama datang adalah "folingtrashy" begitu
terpanjang_consec(strarr, 2) harus mengembalikan "folingtrashy".

Di jalan yang sama:
longest_consec(["zone", "abigail", "theta", "form", "libe", "zas", "theta", "abigail"], 2) --> "abigailtheta"
```

n adalah panjang array string, jika `n = 0` atau `k > n` atau `k <= 0` return `""` (mengembalikan Nothing di Elm, "nothing" di Erlang).

<br>

##### My Solution - [Other](https://www.codewars.com/kata/56a5d994ac971f1ac500003e/solutions/dart)

```dart
String longestConsec(List strarr, k) {
  if (strarr.isEmpty || k > strarr.length || k <= 0) return "";
  String longest = '';
  for (int i = 0; i <= strarr.length - k; i++) {
    String currentS = List.generate(k, (ki) => strarr[ki + i]).join();
    longest = currentS.length > longest.length ? currentS : longest;
  }
  return longest;
}
```

<br>

##### Test

```dart
void main() {
  print(
    longestConsec(["tree", "foling", "trashy", "blue", "abcdef", "uvwxyz"], 2),
  );
}

String longestConsec(List strarr, k) {
  if (strarr.isEmpty || k > strarr.length || k <= 0) return "";
  String longest = '';
  for (int i = 0; i <= strarr.length - k; i++) {
    String currentS = List.generate(k, (ki) => strarr[ki + i]).join();
    longest = currentS.length > longest.length ? currentS : longest;
  }
  return longest;
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
