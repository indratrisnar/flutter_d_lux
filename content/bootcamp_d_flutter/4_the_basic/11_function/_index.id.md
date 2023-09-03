---
title: "11. Function"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords: ["dart", "flutter", "bootcamp", "function"]
---

Function merupakan block kode tertentu yang dibuat idalam sebuah class ataupun public/global yang dibuat/disimpan di suatu file. Hal ini mempengaruhi scope dari function tersebut. Secara umum scope dibagi 2, global dan local.

Jika berada didalam class, utamanya hanya dapat diakses didalam class tersebut, atau bisa diakses dari luar dengan cara tertentu. Jika berada di suatu file maka global, artinya dapat diakses dimana saja asalkan mengimport lokasi filenya. Namun dapat dan tidaknya diakses dari luar, perlu dicek modifier atau hak aksesnya apakah public atau private. Di Dart, jika ingin dijadikan private, maka harus ditambahkan underscore (\_) didepan nama function.

Jika block function hanya memiliki satu baris kode, maka bisa dipersingkat dengan menggunakan arrow function (=>). Arrow function bisa dijadikan juga sebagai return. Sehingga jika ingin membuat function return dan dipersingkat, gunakan arrow function tanpa keyword return. COntoh bisa check di Implement to Flutter.

- [Type](#1-type)
- [Parameter](#2-parameter)
- [Implement to Flutter](#3-implement-to-flutter)

<br>

#### 1. Type

Function type dibagi menjadi 2, function yang memiliki return dan tanpa (void). Dart mendukung dynamic type sehingga function dapat menjadi return dan void. Function return, mengharuskan ada nilai/data yang dikembalikan atau di return ke tempat dimana function tersebut dipanggil. Function return memiliki tipe nya lagi tergantung tipe dari nilai. Tipe dari nilai/data yang di return harus sama dengan tipe function.

Pemanggilan function void, cukup menuliskan namanya beserta kurung. Untuk pemnaggilan function return ada 2 cara, pertama dengan dipanggil langsung di output, kedua dengan dipanggil di proses inisialisasi object/variable.

```dart
void main() {
  // pemanggilan function
  print('---------------------------');

  printCity();
  printCountry();

  print('---------------------------');

  print(sum());
  int resultOfSum = sum();
  print(resultOfSum);

  print(area());
  double result = area() + 10;
  print(result);
}

// deklarasi fungsi void
void printCity() {
  print('City: Garut');
}

// deklarasi fungsi dinamis -> void (no return)
printCountry() {
  print('Country: Indonesia');
}

// deklarasi fungsi return -> int
// type: int
// value: 0
int sum() {
  return 0;
}

// deklarasi fungsi dinamis -> return -> double
area() {
  double resultOfArea = 5.2 * 2;
  return resultOfArea;
}
```

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 2. Parameter

Parameter disebut juga argument. Fungsinya untuk menampung data yang dikirim dari tempat pemanggilan, dimana data yang ditampung di parameter akan digunakan didalam function. Cara deklarasi parameter sama seperti deklarasi variable. Jika ingin dijadiken tipe parameter dynamic, cukup menuliskan namanya saja tanpa tipe.

Jika terdapat multiple parameter, cara memasukan nilai nya harus sesuai urutan dipisahkan dengan koma. Jangan sampai terbalik, jika sampai terbalik bisa terjadi error dengan salah satu alasannya adalah setiap parameter memiliki tipe data yang berbeda dan berbeda penggunaannya.

Dalam pembuatan parameter yang bisa dirubah posisinya, bisa menggunakan cara named parameter. Deklarasinya dibungkus mengunakan kurung kurawal. Contohnya bisa cek ke Implement to Flutter.

```dart
void main() {
  printCity('Garut');
  printCity('Bandung');
  printCity('Los Humans');

  num result = sum(1, 2);
  num result2 = sum(4.3, 6);
  print(result);
  print(result2);
}

void printCity(String cityName) {
  print('City: $cityName');
}


num sum(double number1, double number2) {
  return number1+number2;
}
```

Output:
{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 3. Implement to Flutter

Untuk implementasi callback seperti onPressed pada ElevatedButton, pemanggilan fungsi langsung bisa dilakukan tanpa menyertakan kurung.

```dart
save() {
  print('save');
}

whenClicked() {
  print('whenClicked');
}

void sum() {
  print('sum: 2');
}

int substraction(int n1, int n2) => n1 - n2;

ListView(
  padding: const EdgeInsets.all(16),
  children: [
    ElevatedButton(
      onPressed: () {
        save();
      },
      child: const Text('Save'),
    ),
    const SizedBox(height: 16),
    ElevatedButton(
      onPressed: () => whenClicked(),
      child: const Text('When Cliked'),
    ),
    const SizedBox(height: 16),
    ElevatedButton(
      onPressed: sum,
      child: const Text('Sum'),
    ),
    const SizedBox(height: 16),
    ElevatedButton(
      onPressed: () {
        int result = substraction(5, 3);
        print('Substraction: $result');
      },
      child: const Text('Substraction'),
    ),
    const SizedBox(height: 16),
  ],
),
```

{{< image src="3_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

```dart
addProfile({
  required String name,
  required int age,
  String? imageURL,
}) {
  print('Name: $name');
  print('Age: $age');
  if (imageURL != null) {
    print('imageURL: $imageURL');
  }
}

ElevatedButton(
  onPressed: () => addProfile(name: 'Indre', age: 20),
  child: const Text('Add profile 1'),
),
const SizedBox(height: 16),
ElevatedButton(
  onPressed: () => addProfile(age: 7, name: 'Flutter'),
  child: const Text('Add profile 2'),
),
const SizedBox(height: 16),
ElevatedButton(
  onPressed: () {
    print('---------------');
    addProfile(age: 7, imageURL: 'fdl.png', name: ' F D Lux');
  },
  child: const Text('Add profile 3'),
),
```

{{< image src="3_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="3_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
