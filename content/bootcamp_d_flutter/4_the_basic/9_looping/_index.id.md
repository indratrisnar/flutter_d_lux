---
title: "9. Looping"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  [
    "dart",
    "flutter",
    "bootcamp",
    "basic",
    "looping",
    "for",
    "for in",
    "for each",
    "while",
    "do-while",
  ]
---

Untuk mengeksekusi perintah yang sama beberapa kali, diperlukan membuat/menulis perintah tersebut sebanyak yang diinginkan. Contoh seperti dibawah:

```dart
void main() {
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
}
```

Namun kode diatas tidak efisien, apalagi jika ingin menampilkan ratusan, ribuan dan selanjutnya. Looping dibuat untuk hal seperti ini. Dengan looping, kita buat 1 intruksi/statement kemudian kita set jumlah pengulangannya. Untuk membuat looping ada beberapa cara.

- [For](#1-for)
- [For In](#2-for-in)
- [For Each](#3-for-each)
- [While](#4-while)
- [Do-While](#5-do-while)
- [Implement to Flutter](#6-implement-to-flutter)

<br>

#### 1. For

<table>
<tr><th>Alur yang terjadi pada for:</th></tr>
<tr><td>
Check kondisi,<br>
Jika kondisi true, jalankan semua yang ada dalam block {} for, kemudian Kembali ke Check kondisi<br>
Jika kondisi false, berhenti
</td></tr>
</table>

Contoh:

```dart
void main() {
  for (int index=0; index <= 9; index++) {
    print('$index. Halo, Selamat datang');
  }
}
```

penjelasan block kondisi: (initial, check, increment/decrement)<br>
**initial** : nilai awal untuk posisi looping / iterasi ke-n.<br>
**check** : pengecekan kondisi. Jika kita ingin melakukan looping sebanyak 10 kali, maka bisa dibuat kondisi index <= 9. Kondisi ini dibuat dengan memperhatikan initial dan increment/decrement.<br>
**increment/decrement** : digunakan untuk merubah nilai index setiap kali kondisi bernilai true. Increment berarti perubahan nilai index naik, decrement sebaliknya. Perubahan 1 ke 1, atau 2 tingkat, atau lainnya tergantung kita menggunakan operatornya.

Hasil output kode diatas:
{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya bisa check ke official documentation: [Loops | Dart](https://dart.dev/language/loops#for-loops)

<br>

#### 2. For In

<table>
<tr><th>Alur yang terjadi pada for in:</th></tr>
<tr><td>
Ambil element ke-n,<br>
Lakukan perintah yang ada pada block for in.
</td></tr>
</table>

Sehingga secara default, tidak ada batas berapa kali pengulangan dilakukan. Namun melakukan pengulangan sebanyak data yang dimiliki. Diperlukan data collection untuk melakukan for in.

Contoh:

```dart
void main() {
  List menu = ['Burger','Kebab','Nasgor','Martabak Telor'];
  for (String element in menu){
    print(element);
  }
}
```

Output:
{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya bisa check ke official documentation: [Loops | Dart](https://dart.dev/language/loops#for-loops)

Untuk custom jumlah pengulangan berdasarkan kondisi tertentu bisa menggunakan break dan continue [Loops | Dart](https://dart.dev/language/loops#break-and-continue)

<br>

#### 3. For Each

Sama seperti for in. Namun beda syntax dan lebih disarankan menggunakan for in dibanding foreach.

Example:

```dart
void main() {
  List menu = ['Burger','Kebab','Nasgor','Martabak Telor'];
  menu.forEach((element){
    print(element);
  });
}
```

Output:
{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya bisa check ke official documentation: [forEach method - Iterable class - dart:core library - Dart API](https://api.dart.dev/stable/3.0.0/dart-core/Iterable/forEach.html)

<br>

#### 4. While

Alurnya sama seperti for. Namun beda syntax. Pada saat pertama kali pengecekan, ternyata kondisinya false langsung di stop. Sehingga tidak akan tampil apa-apa di console.

Example:

```dart
void main() {
  int index = 1;
  while(index<=3){
    print('Lup yu');
    index++;
  }
}
```

Output:
{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya bisa check ke official documentation: [Loops | Dart](https://dart.dev/language/loops#while-and-do-while)

<br>

#### 5. Do-While

Mirip dengan while namun alur terbalik. Di While, check terlebih dahulu kemudian eksekusi block {} nya. Sedangkan di Do-While, eksekusi dulu block {} kemudian check. Pada saat pertama kali pengecekan, ternyata kondisinya false langsung maka akan dieksukusi block {} dulu baru di stop. Sehingga akan tampil minimal 1 iterasi/perulangan.

Example:

```dart
void main() {
  int index = 1;
  do {
    print('Lup yu');
    index++;
  }while(index<=3);

  print('---------------');

  int i = 1;
  do {
    print('Lup yu');
    i++;
  }while(i<1);//false
}
```

Output:
{{< image src="5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya bisa check ke official documentation: [Loops | Dart](https://dart.dev/language/loops#while-and-do-while)

<br>

#### 6. Implement to Flutter

Saatnya implementasi ke Flutter dengan menggunakan beberapa fungsi baru sebagai pendukung implementasi ke flutter. Namun alur proses sampai tampil UI ini menggunakan konsep looping. Untuk implementasi ke flutter, tidak semua cara bisa ditempel.

<table>
<!-- 1 -->
<tr>
<td><div>

```dart
Column(
  children: [
    const Text('------------------'),
    for (int index = 1; index < 5; index++)
      Text('Ini ada pada Index $index'),
    const Text('------------------'),
  ],
),
```

</div></td>
<td>
{{< image src="6_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
</td>
</tr>
<!-- 2 -->
<tr>
<td><div>

```dart
List<String> animals = [
  'Cochroaces',
  'Simba',
  'Pikachu',
  'Salmon',
  'Turbo'
];

Column(
  children: [
    const Text('------------------'),
    for (String animal in animals) Text(animal),
    const Text('------------------'),
  ],
),
```

</div></td>
<td>
{{< image src="6_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
</td>
</tr>
</table>

Dan berikut beberapa cara pengaksesan, modifikasi, dan generate dari data list yang langsung dilakukan di flutter code ui. Ada yang langsung di property children/list dan ada pula menggunakan bantuan cascade operator.

<!-- 3 -->
<table>
<tr>
<td><div>

```dart
List<String> animals = [
  'Cochroaces',
  'Simba',
  'Pikachu',
  'Salmon',
  'Turbo'
];

Column(
  children: [
    const Text('------------------'),
    ...List.generate(animals.length, (index) {
      return Text(animals[index]);
    }),
    const Text('------------------'),
  ],
),

Column(
  children: List.generate(animals.length, (index) {
    return Text(
      '${index + 1}. ${animals[index]}',
    );
  }),
),
```

</div></td>
<td>
{{< image src="6_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
</td>
</tr>
</table>

Dengan **List.generate** kita bisa custom set jumlah data dan mendapatkan parameter index, jadi tidak perlu custom buat index sendiri. Fungsi index juga untuk mendapatkan value/element dari list tersebut.

<!-- 4 -->
<table>
<tr>
<td><div>

```dart
List<String> animals = [
  'Cochroaces',
  'Simba',
  'Pikachu',
  'Salmon',
  'Turbo'
];

Column(
  children: [
    const Text('------------------'),
    ...animals.map((e) => Text(e)).toList(),
    const Text('------------------'),
  ],
),

Column(
  children: animals.map((e) {
    return Text(e);
  }).toList(),
),
```

</div></td>
<td>
{{< image src="6_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
</td>
</tr>
</table>

Dengan menggunakan **.map()** dan **toList()** kitab isa mengakses seluruh data kemudian memodifikasi tipenya nya. Alurnya, setiap kali pada iterasi ke-n kita ambil nilai element(e) kemudian kita masukkan ke Widget Text dan di return, selannjutnya masuk ke toList() (list baru). Yang awalnya **List\<String>** menjadi **List\<Text>**.

<br>
