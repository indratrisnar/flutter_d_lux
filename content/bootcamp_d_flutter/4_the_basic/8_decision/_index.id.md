---
title: "8. Decision"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  [
    "dart",
    "flutter",
    "bootcamp",
    "basic",
    "decision",
    "if",
    "else",
    "switch",
    "case",
  ]
---

Pengambilan keputusan di dart programming sama halnya dengan decision di programming lain. Dimana kondisi selalu harus bernilai Boolean, true atau false.

- [If Else](#1-if-else)
- [Switch Case](#2-switch-case)
- [Ternary If Else](#3-ternary-if-else)
- [Implement to Flutter](#4-implement-to-flutter)

<br>

#### 1. If Else

<table>
<tr><th>Alur yang terjadi pada if-else:</th></tr>
<tr><td>
Check kondisi,
Jika kondisi true, jalankan semua yang ada dalam block {} if, dan mengabaikan/melewati block {} else dan else if (jika ada).
Jika kondisi false, jalankan semua yang ada dalam block {} else atau else if (jika ada).
</td></tr>
</table>

Penggunaan else if dan else tidak wajib, jadi jika hanya ada block if saja tidak apa-apa.

Contoh:

```dart
void main() {
  bool isHujan = true;

  if(isHujan) {
    print('Airnya turun');
  }else{
    print('hari ini cerah ya');
  }
}
```

Output: **Airnya turun**, karena isHujan bernilai true.

Contoh lain untuk perbandingan.

```dart
void main() {
  int number1 = 10;
  int number2 = 30;

  String comparison = '';
  if(number1 > number2) {
    comparison = 'bigger than';
  }else if(number1 == number2){
    comparison = 'equal to';
  }else{
    comparison = 'smaller than';
  }
  print('number1 is $comparison number2');
}
```

Output: **number1 is smaller than number2**, because if=false and else_if=false.

Dalam penggunaan If else dapat terjadi nested, if else beranak.

Contoh:

```dart
void main() {
  bool isHujan = true;
  bool isRintik = true;
  bool isCerah = false;

  if(isHujan){
    print('Ya, hari ini hujan');
    if(isRintik){
      print('dan hujannya rintik');
    }
  }else{
    print('Tidak, hari ini tidak hujan');
    if(isCerah){
      print('dan hari ini cerah');
    }
  }
}
```

Output:
{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya bisa check ke official documentation: [Branches | Dart](https://dart.dev/language/branches#if)

<br>

#### 2. Switch Case

Sama halnya dengan penggunaan if else statement, terdapat pengecekan kondisi data namun dengan adanya opsi-opsi tertentu dan perlu ada break untuk menghentikan scope execute. Jika tidak menggunakan break diakhir block case, maka case selanjutnya akan dieksekusi juga. Disini juga terdapat block otomatis yang dieksekusi jika tidak terdapat pilihan/case yang sesuai yaitu default.

Contoh:

```dart
void main() {
  String status = '';

  status = 'loading';
  switch(status) {
    case '':
        print('initial status');
        break;
    case 'loading':
        print('when loading');
        break;
    case 'success':
        print('when success');
        break;
    default:
        print('when failed');
        break;
  }
}
```

Output:
{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Selengkapnya bisa check ke official documentation: [Branches | Dart](https://dart.dev/language/branches#switch-statements)

<br>

#### 3. Ternary If Else

Bentuk inline dari if else. Block if ditandai symbol (?) dan else ditandai (:).
Syntax: condition ? expression1 : expression2

Contoh:

```dart
void main() {
  bool isHujan = true;
  String sentences = isHujan ? "hari ini hujan" : 'hari ini cerah';
  print(sentences);

  num number1 = 63;
  num number2 = 50;
  String result = number1 > number2
    ? "number1 is bigger than number2"
    : 'number1 is smaller than or equal to number2';
  print(result);
}
```

Output:
{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 4. Implement to Flutter

```dart
bool isChecked = true;
bool isPicked = false;
bool isLoading = false;

Column(
  children: [
    const Text('1'),
    if (isChecked) const Text('Accepted Aggrement'),
    const Divider(),
    const Text('2'),
    if (isChecked)
      const Column(
        children: [
          Text('Accepted Aggrement'),
          Text('Accepted Regulation'),
        ],
      ),
    const Divider(),
    const Text('3'),
    isPicked
        ? const Text('You have picked image')
        : const Icon(Icons.add_a_photo),
    const Divider(),
    const Text('4'),
    Text(isPicked ? 'You have picked image' : 'Please pick image'),
    const Divider(),
    const Text('5'),
    isLoading ? CircularProgressIndicator() : const SizedBox(),
  ],
),
```

{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
