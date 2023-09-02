---
title: "4. Concatenation & Interpolation"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  ["dart", "flutter", "bootcamp", "basic", "concatenation", "interpolation"]
---

Bagaimana cara menggabungkan atau menyusun suatu nilai atau variable, kemudian hasil penggabungannya di tampilkan dalam bentuk atau sebagai data string. Ada 2 cara, yaitu Concatenation dan Interpolation.

1. Concatenation

Penggabungan atau penyusunan data yang bernilai String. Cara penggabungan menggunakan operator plus (+). Jika terdapat data/variable yang bernilai selain String, maka harus diconvert terlebih dahulu ke bentuk String agar dapat digabungkan.

```dart
String name = "Flutter D Lux";
int age = 20;

print('1. Name: ' + 'Flutter D Lux' + ', ' + 'Age: ' + '20');
print('2. Name: ' + name);
print('3. Name: ' + name + ', '+'Age: ' + age.toString());

String content = '4. Name: ' + name + ', ' + 'Age: ' + age.toString();
String content2 = '5. Name: ' + name + ', Age: ' + age.toString();
print(content);
print(content2);
```

Output diatas:

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

2. Interpolation

Penggabungan atau penyusunan data yang bernilai String atau bukan String. Cara penggabungan atau penyusunannya menggunakan symbol dollar ($) dan jika terdapat suatu operasi atau ada action object dan lainnya maka setelah dollar ($) datanya dibungkus mengguankan kurung kurawal / curly braces ({}). Data selain string akan otamatis di convert ke bentuk String.

```dart
String name = "Flutter D Lux";
int age = 20;

print('1. Name: $name');
print('2. Name: $name, Age: ${age.toString()}');

String content = '3. Name: $name, Age: ${10+10}';
print(content);
```

Output diatas:

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
