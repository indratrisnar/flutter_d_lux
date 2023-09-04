---
title: "13. Basic Object Oriented programming"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords: ["dart", "flutter", "bootcamp", "oop"]
---

Object Oriented programming (OOP) adalah suatu paradigma dalam pemrograman yang merujuk kesuatu objek. Objek disini beragam macam. Dart merupakan salah satu pemrogramman yang menggunakan paradigma OOP selain paradigma functional. Semua variable yang dibuat di Dart adalah objek.

- [Class](#1-class)
- [Object](#2-object)
- [Constructor](#3-constructor)
- [Static](#4-static)

<br>

#### 1. Class

Class adalah suatu kerangka atau template yang memiliki attribute dan behavior. Attribute bisa kita katakan sebagai ciri-ciri, property, atau variable dalam kode program. Behavior adalah sesuatu yang bisa dilakukan oleh class tersebut, bisa kita katakan sebagai function atau method. Jika kita ingin menggunakan template class ini perlu membuat objectnya terlebih dulu, caranya sama seperti penggunaan variable. Karena sebetulnya variable itu adalah objek dari tipe data nya.

Contoh class:

```dart
class Cat {
  String color = 'white';
  double weight = 4.5;

  eat() {
    print('favorite food: fish');
  }
}
```

<br>

#### 2. Object

Analogi class dan object seperti Mobil dengan BMW, Koeniggseg, Bugatti atau seperti Burung dengan Elang, Bangau. Dari class Cat diatas kita bisa buat satu atau lebih objek. Kita juga dapat memodifikasi property dan method jika memungkinkan. Property maupun method tersebut kita beri modifier atau hak akses public, sehingga dapat diakses oleh semua objeknya.

Untuk property diatas bisa berperan sebagai getter yaitu cara mengambil value propertynya, dan sebagai setter untuk memodifikasi value propertynya namun khusus untuk objek tersebut saja. getter dan setter memilki nama yang sama dengan nama property.

```dart
void main() {
  Cat cat1 = Cat(); // object 1
  print(cat1.color);
  print(cat1.weight);
  cat1.eat();

  print('--------------');

  Cat cat2 = Cat(); // object 2
  print(cat2.color);
  print(cat2.weight);
  cat2.eat();

  print('--------------');

  Cat cat3 = Cat(); // object 3
  cat3.color = 'Brown';
  cat3.weight = 2.5;
  print(cat3.color);
  print(cat3.weight);
  cat3.eat();
}
```

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Berikut contoh untuk property yang private, tidak bisa diakses langsung oleh objeknya jika berada pada file yang berbeda. Jika berada pada file yang sama, masih bisa diakses meskipun kita jadikan propertynya sebagai private. Untuk menandai sebagai private, tambahkan underscore (\_) didepan nama object/variable.

<br>

```dart
class Cat {
  String _color = 'white';
  double _weight = 4.5;
}
```

Jika private dan ingin bisa diakses oleh objeknya, maka dibuat setter dan getter sendiri. Untuk setter, wajib ada 1 parameter sebagai data barunya. Cara penggunaannya sama seperti contoh pertama.

```dart
class Cat {
  String _color = 'white';
  double _weight = 4.5;

  String get color => _color;
  double get weight => _weight;

  set color(String newColor){
    _color = newColor;
  }
  set weight(String newWeight){
    _color = newWeight;
  }
}
```

<br>

#### 3. Constructor

Pembuatan object dan sekaligus inisialisasi property value bisa menggunakan constructor. Nama constructor sama dengan nama class nya. Untuk mengirim inisial data dari pembuatan object untuk dimasukkan ke property mengguankan argument. Penggunaan argument constructor sama seperti penggunaan parameter di method / function.

```dart
void main() {
  Bird bird = Bird(3, 'green');
  bird.show();
}

class Bird {
  int wings;
  String color;

  Bird(this.wings, this.color); // constructor

  show() {
    print('wings: $wings');
    print('color: $color');
  }
}
```

{{< image src="3_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Keyword this digunakan untuk mengakses apa saja yang ada di class Bird tersebut. Agar bisa mengisi argument tanpa memerhatikan posisi, bisa merubah syntax argument menjadi named argument.

```dart
void main() {
  Bird bird = Bird(
    color: 'red',
    wings: 2,
  );
  bird.show();
}

class Bird {
  int wings;
  String color;
  bool? hasTail;

  Bird({
    required this.wings,
    required this.color,
    this.hasTail,
  });

  show() {
    print('wings: $wings');
    print('color: $color');
    print('hasTail: $hasTail');
  }
}
```

{{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 4. Static

Jika ingin mengakses data di suatu class tanpa membuat objek nya terlebih dahulu, bisa menambahkan keyword static diawal property atau method.

```dart
void main() {
  int wings = Bird.wings;
  print(wings);

  print(Bird.color);

  Bird.eat();
}

class Bird {
  static int wings = 2;
  static String color = 'white';

  static eat() {
    print('Burung bisa makan mengguankan paruhnya');
  }
}
```

{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
