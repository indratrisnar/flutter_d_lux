---
title: "5. Flutter Basic Widget"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "basic", "widget"]
---

Beberapa basic widget yang sering digunakan, diantaranya:

- [Container](#1-container)
- [Text](#2-text)
- [Icon](#3-icon)
- [Image](#4-image)
- [Button](#5-button)
- [Additional Widgets](#6-additional-widgets)

#### 1. Container

Container merupakan widget Box. Container sering digunakan sebagai widget size karena memiliki property ukuran. Container juga dapat memposisikan ukuran dirinya berdasarkan ukuran child maupun ukuran root/ pembungkusnya. Berikut contoh sederhana bentuk Container yang mengikuti size root nya yaitu body/screen utama dari page/Scaffold. Gambar dibawah juga menjelaskan bagaimana structure code untuk kedepannya di Flutter Basic Widget.

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Beberapa property Container yang sering digunakan sekaligus penerapannya bisa dicek dibawah:

```dart
Container(
  decoration: BoxDecoration(
    color: Colors.amber,
    borderRadius: BorderRadius.circular(16),
  ),
  width: 200,
  height: 100,
  margin: const EdgeInsets.only(
    left: 20,
    top: 20,
  ),
  padding: const EdgeInsets.all(20),
  child: const Text('Container'),
),
```

{{< image src="1_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| No  | Color  | Property | Use for                                  |
| :-: | ------ | -------- | ---------------------------------------- |
|  1  | red    | margin   | Jarak ke luar dari sisi Container        |
|  2  | blue   | padding  | Jarak ke dalam/child dari sisi Container |
|  3  | purple | radius   | Lengkungan sudut Container.              |

Note: Untuk property warna ada 2. color utama dan color di dalam decoration. Jika kita menggunakan Container dan terdapat color, maka gunakan color yang ada didalam decoration. Jika menggunakan color utama dan terdapat decoration maka akan terjadi error.

<br>

#### 2. Text

Text merupakan widget typography. Data yang ditampilkan atau dimasukan ke widget ini harus bertipe data String. Dilengkapi property untuk styling membuat widget ini lebih customize.
Beberapa property Text yang sering digunakan sekaligus penerapannya bisa dicek dibawah:

```dart
Text(
  'This is widget text',
  style: TextStyle(
    color: Colors.purple,
    fontWeight: FontWeight.bold,
    fontSize: 24,
  ),
),
```

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | Property                                | Use for                           |
| :------------------------------: | --------------------------------------- | --------------------------------- |
|                1                 | First parameter (‘This is widget text’) | Required data yang bertipe String |
|                2                 | style                                   | Modifikasi text                   |
|                3                 | color                                   | warna text                        |
|                4                 | fontWeight                              | ketebalan text                    |
|                5                 | fontSize                                | Ukuran text                       |

<br>

#### 3. Icon

Icon merupakan widget image tapi lebih khusus seperti symbol. Digunakan sebagai label informasi tertentu yangs sederhana.

Beberapa property Icon yang sering digunakan sekaligus penerapannya bisa dicek dibawah:

```dart
Icon(
  Icons.location_on,
  color: Colors.red,
  size: 80,
),
```

{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | <div style="width:120px">Property</div> | Use for                                                                                                                                  |
| :------------------------------: | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
|                1                 | First parameter (Icons.location_on)     | Required data yang bertipe IconData. Dimana default design mengikuti design guide Google. Yang terbaru saat ini design guide Material 3. |
|                2                 | color                                   | Memberikan warna, tipenya color.                                                                                                         |
|                3                 | size                                    | Ukuran icon, tipenya double.                                                                                                             |

<br>

#### 4. Image

Resource image yang didukung ada 4 yaitu dari asset, network, memory, dan file. Pemanggilan widgetnya tidak langsung ke nama class Image nya, tapi melalui method ui yang dibagi 4 diatas. Meskipun terdapat class yang anmanya Image namun berbeda cara penggunaannya.

Untuk image network, memory, dan file. Sumber data berasal dari URL, imageBytes dengan tipe UInt8List/List\<int>, dan File itu sendiri dengan required data path/lokasi file image di storage. Sedangkan untuk image.asset, lokasi asset harus di daftarkan dulu di pubspeck.yaml baru bisa digunakan data lokasi assetnya seperti gambar dibawah.

{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Beberapa property Image yang sering digunakan sekaligus penerapannya bisa dicek dibawah:

```dart
Image.network(
  imageURL,
  width: 150,
  height: 180,
  fit: BoxFit.cover,
),
```

{{< image src="4_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | <div style="width:120px">Property</div>                                                              | Use for                                                          |
| :------------------------------: | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
|                1                 | First parameter ( <br>URL as String,<br>Asset as String,<br>Bytes as Uint8List,<br>File as File<br>) | Required data dengan tipenya tergantung dari jenis image         |
|                2                 | width                                                                                                | Lebar image                                                      |
|                3                 | height                                                                                               | Tinggi image                                                     |
|                4                 | fit                                                                                                  | Cara memasukan gambar ke ruang/ukuran widget image yang tersedia |

<br>

#### 5. Button

Widget yang menyediakan action tertentu, salah satunya onPressed. Jenis button yang sering digunakan dan mengikuti design guide dibagi 3 yaitu ElevatedButton, OutlinedButton, dan TextButton.

Beberapa property Button yang sering digunakan sekaligus penerapannya bisa dicek dibawah:

```dart
ElevatedButton(
  onPressed: () {},
  child: const Text('Publish'),
),
OutlinedButton(
  onPressed: () {},
  child: const Text('Publish'),
),
TextButton(
  onPressed: () {},
  child: const Text('Publish'),
),
```

{{< image src="5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | <div style="width:120px">Property</div> | Use for                                                            |
| :------------------------------: | --------------------------------------- | ------------------------------------------------------------------ |
|                1                 | onPressed                               | Required callback digunakan untuk press action.                    |
|                2                 | child                                   | Widget anaknya, dapat dimasukan widget umum tidak hanya Text saja. |

<br>

#### 6. Additional Widgets

Widget widget tambahan yang digunakan sebagai pelengkap, alat bantu, part, positioning dan lainnya. Namun disini hanya digunakan beberapa saja.

```dart
Center(
  child: Text('Center'),
),
```

{{< image src="6.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
Material(
  child: Padding(
    padding: EdgeInsets.all(20),
    child: Text('Padding - all.20'),
  ),
),
```

{{< image src="6_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
Align(
  alignment: Alignment.bottomRight,
  child: Text('Align - bottom right'),
),
```

{{< image src="6_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
SizedBox(
  width: 100,
  height: 100,
  child: Container(
    color: Colors.amber,
  ),
),
```

{{< image src="6_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | <div style="width:120px">Widget</div> | Use for                                                                                                                                                                   |
| :------------------------------: | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                1                 | Center                                | Jadikan widget child supaya di tengah.                                                                                                                                    |
|                2                 | Align                                 | Jadikan widget child untuk custom position.                                                                                                                               |
|                3                 | Padding                               | Pembungkus widget child, agar memiliki jarak/space dari garis terluar child ke-widget pembungkusnya. Sama seperti padding property di Container.                          |
|                4                 | SizedBox                              | Sebagai root box atau pembungkus widget lain yang tidak memiliki ukuran fixed. Bisa juga digunakan sebagai space/jarak antar child-1 dengan child-lainnya didalam layout. |

<br>
