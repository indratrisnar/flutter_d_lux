---
title: "4. Row Weights"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
# search related keywords
keywords: ["dart", "logic", "codewars", "row", "weight", "array"]
---

Dari: [Codewars](https://www.codewars.com/kata/5abd66a5ccfd1130b30000a9/dart)

##### Scenario

Beberapa orang berdiri berjajar dibagi menjadi dua tim.
Orang pertama masuk ke tim 1, orang kedua masuk ke tim 2, orang ketiga masuk ke tim 1, dan seterusnya.

<br>

##### Task

Diberikan array bilangan bulat positif (bobot orang), kembalikan array/tupel baru yang terdiri dari dua bilangan bulat, dengan yang pertama adalah bobot total tim 1, dan yang kedua adalah bobot total tim 2.

<br>

##### Notes

- Ukuran array minimal 1.
- Semua angka akan positif

<br>

##### Input >> Output Examples

```dart
rowWeights([13, 27, 49]) ==> return (62, 27)
```

Elemen pertama `62` adalah bobot total tim 1, dan elemen kedua `27` adalah bobot total tim 2.

<br>

```dart
rowWeights([50, 60, 70, 80])  ==>  return (120, 140)
```

Elemen pertama `120` adalah bobot total tim 1, dan elemen kedua `140` adalah bobot total tim 2.

<br>

```dart
rowWeights([80])  ==>  return (80, 0)
```

Elemen pertama `80` adalah bobot total tim 1, dan elemen kedua `0` adalah bobot total tim 2.

<br>

##### My Solution - [Other](https://www.codewars.com/kata/5abd66a5ccfd1130b30000a9/solutions/dart)

```dart
List<int> rowWeights(List<int> arr) {
  int team1 = 0, team2 = 0;
  for (var i = 0; i < arr.length; i++) {
    if (i.isEven) team1 += arr[i];
    if (i.isOdd) team2 += arr[i];
  }
  return [team1, team2];
}
```

<br>

##### Test

```dart
void main() {
  var array = [50, 60, 70, 80];
  print(rowWeights(array));
}

List<int> rowWeights(List<int> arr) {
  int team1 = 0, team2 = 0;
  for (var i = 0; i < arr.length; i++) {
    if (i.isEven) team1 += arr[i];
    if (i.isOdd) team2 += arr[i];
  }
  return [team1, team2];
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
