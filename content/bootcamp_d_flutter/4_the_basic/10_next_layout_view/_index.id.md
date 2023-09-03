---
title: "10. Next Layout View"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords: ["dart", "flutter", "bootcamp", "basic", "layout", "view"]
---

Setelah mempelajari basic layout, saatnya belajar layout lanjutannya.

- [SingleChildScrollView](#1-singlechildscrollview)
- [ListView](#2-listview)
- [GridView](#3-gridview)
- [Wrap](#4-wrap)
- [PageView](#5-pageview)

<br>

#### 1. SingleChildScrollView

Jika menggunakan layout Column atau Row kemudian data yang ditampungnya melebihi batas screen atau ruang yang tersedia maka akan terjadi error overflow. Untuk handlenya, bisa menggunakan SingleChildScrollView sebagai pembungkus Column atau Row. Setelah dibungkus SingleChildScrollView tidak akan terjadi error overflow dan column/Row sudah bisa di scroll.

Sebagai pembungkus Column, tidak ada tambahan lain karena property scrollDirection auto di set vertical. Namun jika dijadikan pembungkus Row maka property scrollDirection dijadikan horizontal.

Kembali ke fungsi utamanya untuk memberikan akses scroll ke widget yang dibungkusnya, tidak harus widget layout, single widget pun bisa.

Contoh:

```dart
SingleChildScrollView(
  child: Column(
    children: [
      Container(height: 200, width: 250, color: Colors.purple),
      Container(height: 200, width: 250, color: Colors.yellow),
      Container(height: 200, width: 250, color: Colors.blue),
      Container(height: 200, width: 250, color: Colors.orange),
      Container(height: 200, width: 250, color: Colors.green),
      Container(height: 200, width: 250, color: Colors.red),
    ],
  ),
),
```

{{< image src="1.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
SingleChildScrollView(
  scrollDirection: Axis.horizontal,
  child: Row(
    children: [
      Container(height: 100, width: 150, color: Colors.purple),
      Container(height: 100, width: 150, color: Colors.yellow),
      Container(height: 100, width: 150, color: Colors.blue),
      Container(height: 100, width: 150, color: Colors.orange),
      Container(height: 100, width: 150, color: Colors.green),
      Container(height: 100, width: 150, color: Colors.red),
    ],
  ),
),
```

{{< image src="1_2.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
String imageURL =
        'https://images.pexels.com/photos/14488109/pexels-photo-14488109.jpeg?auto=compress&cs=tinysrgb&w=1600&lazy=load';

SingleChildScrollView(
  scrollDirection: Axis.horizontal,
  child: Image.network(
    imageURL,
    width: 500,
    height: 300,
    fit: BoxFit.cover,
  ),
),
```

{{< image src="1_3.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya: [SingleChildScrollView class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/SingleChildScrollView-class.html)

<br>

#### 2. ListView

ListView merupakan gabungan widget Column/Row dan SingleChildScrollView dengan beberapa tambahan property tergantung tipe listview nya. Terdapat tipe basic ListView dan ada pula builder/generate nya.

Secara default untuk semua child, ukuran cross axisnya yaitu jika pada scrollDirection.vertical maka lebar dan scrollDirection.horizontal maka height nya akan di expand, meskipun setiap child memilki ukurannya masing-masing. Jika ukuran asli child ingin dipertahankan maka harus dibungkus menggunakan widget pembantu atur posisi seperti Align.

Untuk kasus ListView horizontal, perlu dibungkus menggunakan widget box yang memiliki size seperti Container atau SizedBox, jika listview berada didalam layout Column/Listview. Bentuknya seperti nested (didalam listview ada listview lagi).

```dart
ListView(
  padding: const EdgeInsets.all(16),
  children: [
    Align(
      alignment: Alignment.centerRight,
      child: Container(height: 100, width: 150, color: Colors.purple),
    ),
    Container(height: 100, width: 150, color: Colors.yellow),
    Center(
      child: Container(height: 100, width: 150, color: Colors.blue),
    ),
    Container(height: 100, width: 150, color: Colors.orange),
    Container(height: 100, width: 150, color: Colors.green),
    Container(height: 100, width: 150, color: Colors.red),
    Container(
      margin: const EdgeInsets.only(top: 30),
      height: 200,
      color: Colors.blue[200],
      child: ListView(
        scrollDirection: Axis.horizontal,
        children: [
          Container(height: 100, width: 150, color: Colors.purple),
          Container(height: 100, width: 150, color: Colors.yellow),
          Container(height: 100, width: 150, color: Colors.blue),
          Container(height: 100, width: 150, color: Colors.orange),
          Container(height: 100, width: 150, color: Colors.green),
          Container(height: 100, width: 150, color: Colors.red),
        ],
      ),
    ),
  ],
),
```

Output:
{{< image src="2_1.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Untuk versi builder dan generate bisa cek dibawah:

```dart
List colors = [
  Colors.blue,
  Colors.yellow,
  Colors.purple,
  Colors.green,
  Colors.red,
  Colors.orange,
];

ListView.builder(
  itemCount: colors.length,
  itemBuilder: (context, index) {
    Color itemColor = colors[index];
    return Container(
      margin: const EdgeInsets.only(bottom: 16),
      color: itemColor,
      height: 200,
    );
  },
),
```

Output:
{{< image src="2_2.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya: [ListView class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/ListView-class.html)

<br>

#### 3. GridView

Sama seperti listview dari penggunaanya untuk view list, namun ada pengaturan jumlah column seperti bentuk table / gabungan Row dan Column.

Ada property yang mencolok dan required yaitu gridDelegate. Ada 2 tipe yang bis akita gunakan untuk mengisi delegate ini selain custom.

- SliverGridDelegateWithFixedCrossAxisCount\

Unkuran grid fix berdasarkan jumlah crossAxisCount (jumlah grid)

- SliverGridDelegateWithMaxCrossAxisExtent\

Jumlah grid dynamic tergantung ukuran maximum dari child dan ruang yang tersedia. Jika sudah tidak ruang yang tersisa untuk width (axis direction vertikal), maka akan otomatis ke bawah.

```dart
List colors = [
  Colors.blue,
  Colors.yellow,
  Colors.purple,
  Colors.green,
  Colors.red,
  Colors.orange,
  Colors.cyan,
];

GridView(
  padding: const EdgeInsets.all(8),
  gridDelegate: const SliverGridDelegateWithFixedCrossAxisCount(
    crossAxisCount: 3,
    mainAxisSpacing: 16,
    crossAxisSpacing: 8,
    childAspectRatio: 0.8,
  ),
  children: List.generate(colors.length, (index) {
    return Container(color: colors[index]);
  }),
),

GridView.builder(
  itemCount: colors.length,
  padding: const EdgeInsets.all(8),
  gridDelegate: const SliverGridDelegateWithFixedCrossAxisCount(
    crossAxisCount: 3,
    mainAxisSpacing: 16,
    crossAxisSpacing: 8,
    childAspectRatio: 0.8,
  ),
  itemBuilder: (context, index) {
    return Container(color: colors[index]);
  },
),
```

Output:
{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya: [GridView class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/GridView-class.html)

<br>

#### 4. Wrap

Wrap adalah widget layout hasil gabungan dari Column dan Row. Prioritas penyusunannya adalah Row, jika tidak ada ruang lagi maka dibuat Row baru dibawahnya. Dimana setiap Row nya disusun vertical, itulah sebabnya widget ini disebut hasil gabungan Row dan Column.

Spacing di Wrap sama seperti menggunakan spacing di GridView terdapat space between item dan space between Row. Untuk widget child, biasa menggunakan Chip atau ActionChip.

```dart
List<String> animals = [
  'Spongebob',
  'Patrick',
  'Squidward',
  'Mr.Crab',
  'Krabby Patty',
];

Padding(
  padding: const EdgeInsets.all(8.0),
  child: Wrap(
    spacing: 8,
    runSpacing: 8,
    children: animals.map((e) {
      String firstCharacter = e.substring(0, 2);
      return Chip(
        avatar: CircleAvatar(
          child: Text(
            firstCharacter,
            style: const TextStyle(fontSize: 12, height: 1),
          ),
        ),
        label: Text(e),
      );
    }).toList(),
  ),
),
```

Output:
{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya: [Wrap class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/Wrap-class.html)

<br>

#### 5. PageView

Di pemrograman web, PageView sama seperti carousel. Kita bisa gunakan layout ini untuk menyisipkan fragment ui / child page, bisa juga untuk ui khusus seperti carousel image dan lainnya. Untuk size dari pageview mengikuti rule dari ListView.

Untuk direction horizontal, sebaiknya ditambahkan property physic dengan datanya BouncingScrollPhysics() untuk menghindari error bentrok nested scroll behavior. Untuk mengatur lebar child carouselnya bisa menggunakan viewportFraction di PageController.

Secara default, scroll behavior nya menggunakan aksi snapping. Jika ingin disamakan dengan scroll behavior list pada umumnya, bisa merubah nilai pageSnapping menjadi false.

```dart
List travels = [
  'https://images.pexels.com/photos/1271619/pexels-photo-1271619.jpeg?auto=compress&cs=tinysrgb&w=1600',
  'https://images.pexels.com/photos/2166559/pexels-photo-2166559.jpeg?auto=compress&cs=tinysrgb&w=1600',
  'https://images.pexels.com/photos/16762297/pexels-photo-16762297/free-photo-of-aerial-photo-of-the-coastline-in-the-city.jpeg?auto=compress&cs=tinysrgb&w=1600',
  'https://images.pexels.com/photos/1659438/pexels-photo-1659438.jpeg?auto=compress&cs=tinysrgb&w=1600',
];

AspectRatio(
  aspectRatio: 16 / 9,
  child: PageView.builder(
    controller: PageController(viewportFraction: 0.7),
    itemCount: travels.length,
    scrollDirection: Axis.horizontal,
    physics: const BouncingScrollPhysics(),
    itemBuilder: (context, index) {
      return Padding(
        padding: const EdgeInsets.symmetric(
          horizontal: 8,
        ),
        child: Image.network(
          travels[index],
          fit: BoxFit.cover,
        ),
      );
    },
  ),
),
```

Output:
{{< image src="5.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya: [PageView class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/PageView-class.html)

<br>
