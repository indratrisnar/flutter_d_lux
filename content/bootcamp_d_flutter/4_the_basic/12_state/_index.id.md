---
title: "12. State"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords: ["dart", "flutter", "bootcamp", "state"]
---

State adalah keadan pada saat kapan. Kapan disini merujuk ke posisi flow, kita sekarang ada di keaddan posisi mana. Lebih detail maksudnya akan lebih paham sambil praktek. Namun detail informasi tentang state, bisa akses di: [State class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/State-class.html)

- [Lifecycle](#1-lifecycle)
- [Basic State Management](#2-basic-state-management)

<br>

#### 1. Lifecycle

Alur hidup aplikasi di flutter yang akan dibahas, akan difokuskan ke lifecycle page/halaman Statefull. Dan hanya yang versi sederhananya saja agar cepat inti lifecycle cepat dipahami. Yang sering digunakan: initState, build, dispose.

| <div style="width:30px">No</div> | <div style="width:220px">Lifecycle</div> | Deskripsi                                                                                                            |
| :------------------------------: | ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
|                1                 | createState                              | State yang wajib dibuat, otomatis di create Ketika kita membuat Statefull Widget dengan menggunakan shortcut stf.    |
|                2                 | initState                                | State awal, biasa digunakan untuk melakukan inisialisasi object, data dan lainnya.                                   |
|                3                 | didChangeDependencies                    | Keadaan yang mengikuti step initState, di sarankan tidak melkukan aksi seperti inisialisasi, request ke backend dll. |
|                4                 | build                                    | Tempat UI dibangun. Diusahakan data sudah siap, sebelum ditempelkan ke UI.                                           |
|                5                 | deactivate                               | Keadaan yang mengikuti dispose, namun lebih dulu dipanggil sebelum dispose.                                          |
|                6                 | dispose                                  | Keadaan ketika page di close/dihancurkan.                                                                            |

```dart
import 'package:flutter/material.dart';

class HomePage extends StatefulWidget {
  const HomePage({super.key});

  @override
  State<HomePage> createState() {
    print('-------------- createState()');
    return _HomePageState();
  }
}

class _HomePageState extends State<HomePage> {
  late int number;
  @override
  void initState() {
    print('-------------- initState()');
    super.initState();
  }

  @override
  void didChangeDependencies() {
    print('-------------- didChangeDependencies()');
    super.didChangeDependencies();
  }

  @override
  Widget build(BuildContext context) {
    print('-------------- build()');
    return Scaffold(
      appBar: AppBar(
        title: const Text('Home Page'),
        centerTitle: true,
      ),
    );
  }

  @override
  void deactivate() {
    print('-------------- deactivate()');
    super.deactivate();
  }

  @override
  void dispose() {
    print('-------------- dispose()');
    super.dispose();
  }
}
```

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 2. Basic State Management

Untuk implementasi basic state management, kita perlu menggunakan **StatefullWidget** dan **setState((){})**. Fungsi setState adalah untuk mentrigger update UI. setState ini dipanggil Ketika kita ingin menampilkan data terbaru ke UI. Karena UI tidak bisa mengupdate nilai/data secara otomatis.

Jika dilihat dari flow state, ketika kita memanggil setState, lifecycle build() akan dieksekusi kembali. Artinya, UI pada state build ke-1 akan dihancurkan, kemudian di buid kembali. Kemudian state ada pada keadaan build ke-2 dan seterusnya jika dipanggil lagi setState.

```dart
import 'package:flutter/material.dart';

class UpdateStatePage extends StatefulWidget {
  const UpdateStatePage({super.key});

  @override
  State<UpdateStatePage> createState() => _UpdateStatePageState();
}

class _UpdateStatePageState extends State<UpdateStatePage> {
  String name = 'Flutter';

  @override
  Widget build(BuildContext context) {
    print('build()');
    print('name: $name');
    return Scaffold(
      appBar: AppBar(
        title: const Text('Update State'),
        centerTitle: true,
      ),
      body: ListView(
        padding: const EdgeInsets.all(16),
        children: [
          Text(
            name,
            style: Theme.of(context).textTheme.displaySmall,
          ),
          const SizedBox(height: 16),
          ElevatedButton(
            onPressed: () {
              name = 'D Lux';
              setState(() {});
            },
            child: const Text('Change'),
          ),
        ],
      ),
    );
  }
}
```

{{< image src="2_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="2_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

```dart
import 'package:flutter/material.dart';

class FavoritePage extends StatefulWidget {
  const FavoritePage({super.key});

  @override
  State<FavoritePage> createState() => _FavoritePageState();
}

class _FavoritePageState extends State<FavoritePage> {
  bool isFavorite = false;

  clickFavorite() {
    isFavorite = !isFavorite; // flip
    setState(() {});
  }

  @override
  Widget build(BuildContext context) {
    print('isFavorite: $isFavorite');
    return Scaffold(
      appBar: AppBar(
        title: const Text('Favorite'),
        centerTitle: true,
      ),
      body: Center(
        child: IconButton(
          onPressed: () => clickFavorite(),
          icon: Icon(
            isFavorite ? Icons.favorite : Icons.favorite_border,
            color: Colors.red,
          ),
        ),
      ),
    );
  }
}
```

{{< image src="2_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| first state (1)                                                                                                                                                  | state change (2)                                                                                                                                                 | state change (3)                                                                                                                                                 |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="2_5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="2_6.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="2_7.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>
