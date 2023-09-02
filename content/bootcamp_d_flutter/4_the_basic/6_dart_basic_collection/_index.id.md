---
title: "6. Dart Basic Collection"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  ["dart", "flutter", "bootcamp", "basic", "collection", "list", "map", "set"]
---

Collection adalah kumpulan data-data dengan ciri, sifat, jenis tertentu. Bisa juga disebut sebagai tipe variable yang dapat menampung data lebih dari 1 dimana datanya harus dengan tipe yang sama atau boleh berbeda. Collection di Dart dibagi menjadi 3 yaitu List, Set, dan Map.

- [List](#1-list)
- [Set](#2-set)
- [Map](#3-map)

<br>

#### 1. List

List merupakan tipe data yang dapat menampung banyak data. Data yang ditampung atau dimasukkan kedalamnya disebut dengan element. Element dapat bertipe sama atau berbeda tergantung bagaimana kita mendeklarasikan tipe List nya. Semua element list dibungkus menggunakan symbol kurung siku “[]”.

Secara default dapat menampung element yang bermacam tipe kaarena otomastis bertipe dynamic. Namun jika kita persempit atau dikhususkan hanya untuk menampung data integer saja, maka element yang bisa dimasukkan atau ditampung harus bertipe integer.

Berikut contoh deklarasi, inisialisasi dan gabungannya.

| No  | Deklarasi          | Inisialisasi               | Gabungan                        |
| :-: | ------------------ | -------------------------- | ------------------------------- |
|  1  | List menu          | menu = [1,"Apel",true];    | List menu = [1,"Apel",true];    |
|  2  | List\<String> menu | menu = ["Burger","Pizza"]; | List\<String> menu = ["A",'c']; |

List ibarat susunan kamar hotel. Kamar hotel disini adalah element. Cara membedakan kamr hotel 1 dengan yang lain menggunakan nomor kamar. Di List terdapat **index** untuk penomoran tempat element berada. Sehingga cara mengakses element yang kita inginkan, dengan menggunakan index. Nomor index selalu diawali dari nilai **0**. Sehingga element pertama berada pada index 0. Namun jika kita mengakses index yang tidak terdapat pada list tersebut maka akan terjadi error **Uncaught Error: RangeError (index): Index out of range**.

Misal terdapat list ingatan, jika kita ingin mendapatkan element Pizza maka harus menggunakan index 0 dan jika ingin mendapatkan element true maka menggunakan index 2. Contoh tersebut dapat dilihat pada code dibawah.

```dart
void main() {
  List ingatan = ['Pizza', 9, true, 3.14, 'A', "Go"];

  String firstElement = ingatan[0];

  print(firstElement);
  print(ingatan[2]);
}
```

Note: untuk test code ini bisa melalui [DartPad](https://dartpad.dev/?)

Output:
{{< image src="pizza_true.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Karena setiap variable adalah object dari suatu class maka **ingatan** diatas adalah **objek** dan **List** adalah **class** nya. Sehingga objeknya yaitu menu dapat mengakases dan menggunakan attribute dan method yang dimiliki class **List**. Begitu pula dengan data/element nya mengikuti tipe dari element tersebut.

Beberapa attribute/property dan method yang sering digunakan untuk List:

```dart
void main() {
  List ingatan = ['Pizza',9,true,3.14,'A',"Go"];

  print(ingatan);
  ingatan.add('Emplod');
  print(ingatan);

  print('\n-------------------');
  print(ingatan);
  print('isEmpty: ${ingatan.isEmpty}');
  ingatan.clear();
  print(ingatan);
  print('isEmpty: ${ingatan.isEmpty}');

  print('\n-------------------');
  ingatan = ['Pizza',9,true,3.14];
  print(ingatan);
  ingatan[1] = 'Burger';
  print(ingatan);
  ingatan.removeAt(3);
  print(ingatan);
  print(ingatan.length);
}
```

Note: untuk test code ini bisa melalui [DartPad](https://dartpad.dev/?)

Output:
{{< image src="list.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:25px">No</div> | <div style="width:150px">Property/method</div> | Use for                                                                                                         |
| :------------------------------: | ---------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
|                1                 | add()                                          | Menambahkan data baru setelah index terakhir                                                                    |
|                2                 | isEmpty                                        | Mengecek apakah list tersebut kosong?                                                                           |
|                3                 | clear()                                        | Menghapus/Mengosongkan list                                                                                     |
|                4                 | list[index]=n;                                 | Cara mengupdate element berdasarkan index dimana list adalah nama objek/variable dan n adalah data/element baru |
|                5                 | removeAt                                       | Menghapus berdasarkan posisi index                                                                              |
|                6                 | length                                         | Menghitung jumlah data/element yang ada pada list tersebut                                                      |

Selengkapnya tentang list: [Collections | Dart](https://dart.dev/language/collections#lists)

<br>

#### 2. Set

Hampir persis seperti **List** namun element yang ditampung hanya element unik berbeda dengan element yang lain. Jika kita menambahkan data baru namun sudah ada data yang sama didalamnya, maka data baru tidak dimasukkan. Jika pada inisial data terdapat data yang sama, maka ketika menghitung, menggunakan, mengambil data list tersebut hanya akan membawa data yang urutan pertamanya saja. Data/element yang sama di posisi terbelakang tidak akan dibawa. Untuk pembungkus data menggunakan kurung kurawal.

```dart
void main() {
  Set ingatan = {'Pizza',9,true,3.14,'A',"Go",true};
  print(ingatan);
}
```

Note: untuk test code ini bisa melalui [DartPad](https://dartpad.dev/?)

Output:
{{< image src="set.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Dari hasil output diatas, nilai **true** yang ada dibelakang tidak dibawa karena di depannya sudah ada nilai **true**.

Untuk mengakses element berdasarkan index bisa menggunakan fungsi: ingatan.**elementAt(5)**.

Selengkapnya tentang set: [Collections | Dart](https://dart.dev/language/collections#sets)

<br>

#### 3. Map

Dari sisi data collection sama halnya dengan List dan Set. Namun untuk penomoran element lebih leluasa. Kita bisa tentukan sendiri nomor posisi kamar element/data karena element di Map terstruktur berdasarkan **key** dan **value**. **Key** adalah posisi kamar, kitab isa tentukan dia bertipe apa dan nilainya apa. Begitu pula **Value** tipe nya apa dan nilainya apa. Pembungkus datanya seperti Set.

Untuk akases data mirip seperti **List** namun disesuaikan Kembali dengan tipe data dari **key** nya. Jika di deklarasikan **Map** saja maka artinya memiliki tipe **key** dynamic dan **value** dynamic. Jika ingin spesifik bisa dibuat seperti **Map\<String,int>**, artinya memiliki tipe key String dan value integer. Jika mengakses key yang tidak terdaftar di map, maka akan me-return **null**.

Contoh penggunaan map:

```dart
void main() {
  Map<int,String> fruits = {
    1:'Mangga',
    2:'Apel',
    5:'Pepaya',
    10:'rambutan'
  };
  Map<String,dynamic> country = {
    'Tokyo':'Japan',
    'Jakarta':'Indonesia',
    'Seoul':'Korea Selatan',
  };
  print(fruits);
  print(country);
  print('------------------');
  print(fruits[5]);
  print(country['Seoul']);
  print(country.length);
}
```

Note: untuk test code ini bisa melalui [DartPad](https://dartpad.dev/?)

Output:
{{< image src="map.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya tentang map: [Collections | Dart](https://dart.dev/language/collections#maps)

<br>
