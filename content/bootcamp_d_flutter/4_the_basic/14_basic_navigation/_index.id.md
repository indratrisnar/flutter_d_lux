---
title: "14. Basic Navigation"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords:
  [
    "dart",
    "flutter",
    "bootcamp",
    "navigation",
    "navigator",
    "imperative",
    "declarative",
  ]
---

Navigation disini adalah pindah halaman, menggunakan class Navigator. Maksud pindah disini bukan murni halamannya diganti, ada aturannya. Aturannya ada yang menerapkan konsep Stack atau tumpukan.

Maksud tumpukan disini contohnya ada halaman home, kemudian ditumpuk dengan halaman 2 sehingga yang terlihat di aplikasi sekarang adalah halaman 2. Hal ini bukan berarti pindah dengan cara diganti, tapi ditumpuk. Jika halaman 2 di close atau dalam kode artinya dihancurkan, maka halaman Home akan terlihat kembali.

Selain ditumpuk, ada juga yang benar-benar diganti. Alur penggantian halaman ini maksudnya menghancurkan halaman lama, kemudian memanggil halaman baru.

Tidak hanya pindah halaman, namun bisa sambil membawa data. Bisa dari halman lama ke halaman baru atau sebaliknya. Ada dua cara untuk melakukan navigasi atau perpindahan halaman. Perlu sambil melihat ke source code untuk pemahaman lebih lanjut. Sebelum masuk ke Imperative/Declarative Page, terdapat HomePage sebagai root app page.

- [Imperative](#1-imperative) - ([Push](#11-push), [Replace](#12-replace), [Send](#13-push-with-data), [Get](#14-push-then-get-data))
- [Declarative](#2-declarative) - ([Push](#21-push), [Replace](#22-replace), [Send](#23-push-with-data), [Get](#24-push-then-get-data))

{{< image src="home.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 1. Imperative

{{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

###### 1.1. Push

Memanggil halaman kemudian ditumpuk diatas halaman saat ini.

- Current Page: ImperativePage
- New Page: Page1
- When back: show ImperativePage

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => const Page1(),
  ),
);

class Page1 extends StatelessWidget {
  const Page1({super.key});

  @override
  Widget build(BuildContext context) {
    print('Page 1');
    ...
  }
}
```

|                                                                                                                                                                  |                                               |                                                                                                                                                                                                                                                                                                                                   |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | <div style="margin:auto;width: 50%;">=></div> | {{< image src="1_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} {{< image src="1_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

###### 1.2. Replace

Menghancurkan halaman saat ini kemudian memanggil halaman baru untuk menggantikan halaman yang dihancurkan.

- Current Page: ImperativePage
- New Page: Page2
- When back: show HomePage

```dart
Navigator.pushReplacement(
  context,
  MaterialPageRoute(
    builder: (context) => const Page2(),
  ),
);

class Page2 extends StatelessWidget {
  const Page2({super.key});

  @override
  Widget build(BuildContext context) {
    print('Page 2');
    ...
  }
}
```

|                                                                                                                                                                  |     |                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | =>  | {{< image src="1_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}{{< image src="1_5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

###### 1.3. Push with Data

Cara pindah halaman beserta mengirim data ke halaman tujuan menggunakan Constructor argument.

- Current Page: ImperativePage
- New Page: Page3 (with Data)
- When back: show ImperativePage

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => const Page3(name: 'Flutter D Lux'),
  ),
);

class Page3 extends StatelessWidget {
  const Page3({super.key, required this.name});
  final String name;

  @override
  Widget build(BuildContext context) {
    // if StetFullWidget access by `widget', example: `widget.name`
    String nameText = name;
    print('Page 3');
    ...
  }
}
```

|                                                                                                                                                                  |     |                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | =>  | {{< image src="1_6.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}{{< image src="1_7.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

###### 1.4. Push then Get Data

Setelah kembali ke halaman saat ini, menerima data yang dikirim dari halaman baru.

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => const Page4(),
  ),
).then((value) {
  print('Data from Page 4: $value');
});

// in page 4
Navigator.pop(context, 'Zehahaha');
```

|                                                                                                                                                                  |     |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | =>  | {{< image src="1_8.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |
| {{< image src="1_9.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | <=  |                                                                                                                                                                  |

Ketika klick back button di appBar, akan me return null.

<br>

#### 2. Declarative

Untuk implementasi declarative routing perlu mendeklarasikan terlebih dahulu route name yang akan digunakan pada MaterialApp.

{{< image src="2_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

###### 2.1. Push

Memanggil halaman kemudian ditumpuk diatas halaman saat ini.

- Current Page: DeclarativePage
- New Page: Page5
- When back: show DeclarativePage

```dart
Navigator.pushNamed(context, '/page5');

class Page5 extends StatelessWidget {
  const Page5({super.key});

  @override
  Widget build(BuildContext context) {
    print('Page 5');
    ...
  }
}
```

|                                                                                                                                                                  |     |                                                                                                                                                                                                                                                                                                                                   |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | =>  | {{< image src="2_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} {{< image src="2_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

###### 2.2. Replace

Menghancurkan halaman saat ini kemudian memanggil halaman baru untuk menggantikan halaman yang dihancurkan.

- Current Page: DeclarativePage
- New Page: Page6
- When back: show HomePage

```dart
Navigator.pushReplacementNamed(context, '/page6');

class Page6 extends StatelessWidget {
  const Page6({super.key});

  @override
  Widget build(BuildContext context) {
    print('Page 6');
    ...
  }
}
```

|                                                                                                                                                                  |     |                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | =>  | {{< image src="2_5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}{{< image src="2_6.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

###### 2.3. Push with Data

Cara pindah halaman beserta mengirim data ke halaman tujuan menggunakan argument dari route settings.

- Current Page: DeclarativePage
- New Page: Page7 (with Data)
- When back: show DeclarativePage

```dart
Navigator.pushNamed(
  context,
  '/page7',
  arguments: 'Flutter D Lux',
);

class Page7 extends StatelessWidget {
  const Page7({super.key});

  @override
  Widget build(BuildContext context) {
    print('Page 7');
    // as String because data was send is 'Flutter D Lux'
    String name = ModalRoute.of(context)!.settings.arguments as String;
    ...Text(name)...
  }
}
```

|                                                                                                                                                                  |     |                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | =>  | {{< image src="2_7.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}{{< image src="2_8.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

###### 2.4. Push then Get Data

Setelah kembali ke halaman saat ini, menerima data yang dikirim dari halaman baru.

```dart
Navigator.pushNamed(context, '/page8').then((value) {
  print('Data from Page 8: $value');
});

class Page8 extends StatelessWidget {
  const Page8({super.key});

  @override
  Widget build(BuildContext context) {
    print('Page 8');
    ...
    Navigator.pop(context, 'Yohohoho');
    ...
  }
}
```

|                                                                                                                                                                   |     |                                                                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| {{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}  | =>  | {{< image src="2_9.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}  |
| {{< image src="2_11.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | <=  | {{< image src="2_10.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |     |

Ketika klick back button di appBar, akan me return null.

<br>
