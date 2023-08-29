---
title: "2. Meeting"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
keywords: ["dart", "logic", "codewars", "meeting", "order", "array"]
---

From: [Codewars](https://www.codewars.com/kata/59df2f8f08c6cec835000012/dart)

John telah mengundang beberapa teman. Daftarnya adalah:

```dart
"Fred:Corwill;Wilfred:Corwill;Barney:Tornbull;Betty:Tornbull;Bjon:Tornbull;Raphael:Corwill;Alfred:Corwill";
```

<br>

Bisakah Anda membuat program yang:

- menjadikan string ini huruf besar
- memberikannya diurutkan berdasarkan abjad berdasarkan nama belakang.

Jika nama belakangnya sama, urutkan berdasarkan nama depan. Nama belakang dan nama depan tamu muncul di antara tanda kurung dan dipisahkan dengan koma.

Jadi hasil rapat fungsi adalah:

```dart
"(CORWILL, ALFRED)(CORWILL, FRED)(CORWILL, RAPHAEL)(CORWILL, WILFRED)(TORNBULL, BARNEY)(TORNBULL, BETTY)(TORNBULL, BJON)"
```

Bisa saja terjadi bahwa dalam dua keluarga berbeda dengan nama keluarga yang sama, dua orang juga mempunyai nama depan yang sama.

<br>

##### My Solution - [Other](https://www.codewars.com/kata/59df2f8f08c6cec835000012/solutions/dart)

```dart
String meeting(String s) {
  List list = s.toUpperCase().split(';').map((e) => e.split(':')).toList();
  list.sort((a, b) {
    if (a[1] == (b[1])) return a[0].compareTo(b[0]);
    return a[1].compareTo(b[1]);
  });
  return list.map((e) => '(${e[1]}, ${e[0]})').join();
}
```

<br>

##### Test

```dart
void main() {
  var input =
      "Fred:Corwill;Wilfred:Corwill;Barney:Tornbull;Betty:Tornbull;Bjon:Tornbull;Raphael:Corwill;Alfred:Corwill";
  print(meeting(input));
}

String meeting(String s) {
  List list = s.toUpperCase().split(';').map((e) => e.split(':')).toList();
  list.sort((a, b) {
    if (a[1] == (b[1])) return a[0].compareTo(b[0]);
    return a[1].compareTo(b[1]);
  });
  return list.map((e) => '(${e[1]}, ${e[0]})').join();
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
