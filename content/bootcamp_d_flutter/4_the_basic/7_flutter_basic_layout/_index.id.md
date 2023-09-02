---
title: "7. Flutter Basic Layout"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "basic", "layout"]
---

Setiap UI memiliki struktur utama yang menjadikan suatu view dapat disusun satu dengan yang lainnya agar sesuai dengan yang kita atau user inginkan. Widget layout paling basic dibagi 3.

- [Column](#1-column)
- [Row](#2-row)
- [Stack](#3-stack)

#### 1. Column

Layout Column digunakan untuk menampung widgets yang disusun secara vertical (top to bottom / bottom to top). Karena dapat menampung banyak data/widget maka nama property nya children dengan tipe List\<Widget>.

Tinggi Column tergantung jumlah children yang ditampung atau tergantung ukuran widget pembungkus Column. Lebar Column tergantung ukuran child terpanjang atau berdasarkan ukuran widget yang ngebungkus/nge-wrap Column. Jika children terlalu banyak dan tidak bisa ditampilkan semua ke wilayah body maka akan terjadi error overflow.

Property yangs sering dipakai:

```dart
Column(
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisAlignment: MainAxisAlignment.center,
  mainAxisSize: MainAxisSize.max,
  children: [
    Text('Child ke-1 ajaskka'),
    SizedBox(height: 20),
    Text('Child ke-3 as'),
    SizedBox(height: 20),
    Text('Child ke-5 asiijuuhsa asjiajsa'),
    SizedBox(height: 20),
    Text('Child ke-7 asasas'),
    Text('Child ke-8'),
  ],
),
```

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:25px">No</div> | <div style="width:150px">Property</div> | Use for                                                                                                                          |
| :------------------------------: | --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
|                1                 | crossAxisAlignment (Red)                | Mengatur posisi children agar sama rata berdasarkan ukuran lebar Column. Contoh rata kiri.                                       |
|                2                 | mainAxisAlignment (Orange)              | Memposisikan child berdasarkan ukuran tinggi Colum.                                                                              |
|                3                 | mainAxisSize (Blue)                     | Mengatur ukuran tinggi Column, apakah di prioritaskan mengikuti ukuran widget pembungkusnya atau mengikuti jumlah data children. |

<br>

#### 2. Row

Sama seperti Column, namun beda direction. Row Menyusun children secara horizontal. Untuk ukurannya pun dibalik berdasarkan ukuran Column.

Property yangs sering dipakai:

```dart
Row(
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisAlignment: MainAxisAlignment.center,
  mainAxisSize: MainAxisSize.min,
  children: [
    Text('Child 1'),
    SizedBox(width: 10),
    Container(
      height: 80,
      width: 60,
      color: Colors.green,
    ),
    SizedBox(width: 10),
    Text('Child 5'),
  ],
),
```

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:25px">No</div> | <div style="width:150px">Property</div> | Use for                                                                                                                      |
| :------------------------------: | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
|                1                 | crossAxisAlignment (Red)                | Mengatur posisi children agar sama rata berdasarkan ukuran tinggi Row. Contoh rata atas (start).                             |
|                2                 | mainAxisAlignment (Orange)              | Memposisikan child berdasarkan ukuran lebar Row.                                                                             |
|                3                 | mainAxisSize (Blue)                     | Mengatur ukuran lebar Row, apakah di prioritaskan mengikuti ukuran widget pembungkusnya atau mengikuti jumlah data children. |

<br>

#### 3. Stack

Stack menyusun children dengan ditumpuk. Penumpukan akan terlihat jika child memiliki ukuran yang berbeda karena arah penumpukannya belakang-depan. Posisi dibelakang ditulis pertama dalam children, sedangkan data terakhir di List children akan diposisikan paling atas/depan. Penumpukan ini dipengaruhi juga oleh elevation, tinggal kita pintar-pintar mengatur posisi ini dimana itu dimana.

Ukuran Stack mengikuti ukuran child terluas atau mengikuti ukuran widget pembungkusnya. Untuk kasus tertentu disarankan ukurannya mengikuti ukuran widget pembungkus seperi SizedBox/Container agar tidak terjadi error UI seperti implementasi Expandable widget child.

Property yangs sering dipakai:

```dart
Stack(
  alignment: Alignment.bottomRight,
  children: [
    Container(
      height: 180,
      width: 160,
      color: Colors.green,
    ),
    Container(
      height: 100,
      width: 100,
      color: Colors.yellow,
    ),
    Container(
      height: 80,
      width: 60,
      color: Colors.purple,
    ),
  ],
),
```

{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:25px">No</div> | <div style="width:150px">Property</div> | Use for                                                                                                                      |
| :------------------------------: | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
|                1                 | alignment (Red)                         | Mengatur posisi children relative kearah mana. Contoh: bottomRight, semua child akan diposisikan dibagian bawah kanan Stack. |

Jika ingin child nya diposisikan berbeda, setiap child dibungkus menggunakan widget positioning seperti Align. Contoh dibawah:

```dart
Stack(
  alignment: Alignment.bottomRight,
  children: [
    Container(
      height: 180,
      width: 160,
      color: Colors.green,
    ),
    Container(
      height: 100,
      width: 100,
      color: Colors.yellow,
    ),
    Align(
      alignment: Alignment.topLeft,
      child: Container(
        height: 80,
        width: 60,
        color: Colors.purple,
      ),
    ),
  ],
),
```

{{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
