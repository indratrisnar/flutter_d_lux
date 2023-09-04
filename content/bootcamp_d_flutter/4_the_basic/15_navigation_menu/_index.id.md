---
title: "15. Navigation Menu"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords:
  [
    "dart",
    "flutter",
    "bootcamp",
    "navigation",
    "menu",
    "drawer",
    "tabbar",
    "bottomnavigationbar",
  ]
---

Navigation disini adalah berpindah halaman yang sebetulnya bukan Scaffold atau screen secara utuh, namun berpindah view atau Sebagian tampilan di screen. Misal terdapat Header/AppBar Dashboard, view yang berpindah atau diganti hanya bagian body nya atau konten utama. Jika dari teman-teman ada yang pernah develop android native menggunakan android studio kotlin/java, maksud view disini sama seperti fragment di android native. Untuk memindahkan/mengganti view, perlu menu. Pembuatan menu yang dikhususkan untuk navigation view ada beberapa.

- [Drawer](#1-drawer)
- [Tab Bar](#2-tab-bar)
- [Bottom Navigation Bar](#3-bottom-navigation-bar)

<br>

#### 1. Drawer

Menu navigation yang muncul dari sebelah kiri/kanan screen dengan cara di swipe atau menekan icon button menu di appBar. Di Scaffold, terdapat property drawer dan endDrawer untuk menempatkan view Drawer. Dan Secara otomatis akan di create icon button Menu di leading/action appBar. Drawer memiliki view Headernya dengan nama widget DrawerHeader.

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="1_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

```dart
import 'package:flutter/material.dart';

class DarwerPage extends StatefulWidget {
  const DarwerPage({super.key});

  @override
  State<DarwerPage> createState() => _DarwerPageState();
}

class _DarwerPageState extends State<DarwerPage> {
  int currentIndex = 0;
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Drawer'),
        centerTitle: true,
      ),
      drawer: Drawer(
        child: ListView(
          children: [
            const DrawerHeader(
              child: Row(
                children: [
                  FlutterLogo(size: 80),
                  Text('Username'),
                ],
              ),
            ),
            const Text('Menu'),
            ListTile(
              onTap: () {
                currentIndex = 0;
                setState(() {});
                Navigator.pop(context);
              },
              leading: const Icon(Icons.message),
              title: const Text('Message'),
              trailing: const Icon(Icons.navigate_next),
            ),
            ListTile(
              onTap: () {
                currentIndex = 1;
                setState(() {});
                Navigator.pop(context);
              },
              leading: const Icon(Icons.history),
              title: const Text('History'),
              trailing: const Icon(Icons.navigate_next),
            ),
            const Divider(),
            const ListTile(
              leading: Icon(Icons.logout),
              title: Text('Logout'),
              trailing: Icon(Icons.navigate_next),
            ),
          ],
        ),
      ),
      body: Center(
        child: currentIndex == 0
            ? const Text(
                'Message',
              )
            : const Text(
                'History',
              ),
      ),
    );
  }
}
```

Agar fragment atau body nya berubah sesuai menu yang kita klik di Drawer menu, maka perlu sesuatu sebagai tanda posisi widget dan untuk pengecekan juga. Kita bisa gunakan index. Kemudian implementasi ceknya bisa menggunakan if else atau menggunakan data array/List. Untuk mengupdate UI Ketika nilai index berubah, perlu memanggil setState((){}). Untuk menutup Draawer bisa menggunakan Navigator pop.

{{< image src="1_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 2. Tab Bar

Menu TabBar biasa disisipkan pada bagian bottom dari AppBar. Namun bisa juga custom di tempelkan di wilayah body Scaffold. Untuk menerapkan AppBar perlu tab controller atau mengguanakn widget DefaultTabController, sehingga kita tidak perlu memikirkan bagaimana penggunaan index nya untuk mengganti view. Cukup menambahkan TabBarView di wilayah body untuk mengganti view disesuaikan dengan urutan menu TabBar. DefaultTabBar dibuat di root atas yang membungkus TabBar dan TabBarView.

```dart
import 'package:flutter/material.dart';

class TabBarPage extends StatelessWidget {
  const TabBarPage({super.key});

  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
      length: 3,
      child: Scaffold(
        appBar: AppBar(
          title: const Text('TabBar'),
          centerTitle: true,
          bottom: const TabBar(
            tabs: [
              Tab(text: 'Message'),
              Tab(text: 'Story'),
              Tab(text: 'Activity'),
            ],
          ),
        ),
        body: const TabBarView(
          children: [
            Icon(Icons.message),
            Icon(Icons.rss_feed),
            Icon(Icons.history),
          ],
        ),
      ),
    );
  }
}
```

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

TabBarView sudah mengandung action swipe change view, jadi kita tidak perlu menerapkan animasi dan action lainnya. Jika di android native, disebut dengan view pager.

<br>

#### 3. Bottom Navigation Bar

Mirip seperti TabBar namun tidak disediakan controller default, kita mesti buat manual seperti pada Drawer untuk merubah view. Tampil dibagian bawah screen dengan elevation diatas body Scaffold. Untuk menerapkannya, sudah disediakan property bottomNavigationBar di Scaffold. Berdasarkan Material Design Guide, jumlah menu di bottom nav minimal 3 dan maksimal 5. Dengan item menunya cukup icon saja atau dengan label ditampilkan.

```dart
import 'package:flutter/material.dart';

class BottomNavigationPage extends StatefulWidget {
  const BottomNavigationPage({super.key});

  @override
  State<BottomNavigationPage> createState() => _BottomNavigationPageState();
}

class _BottomNavigationPageState extends State<BottomNavigationPage> {
  int currentIndex = 0;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Bottom Navigation Bar'),
        centerTitle: true,
      ),
      body: Center(
        child: currentIndex == 0
            ? const Text('Home')
            : currentIndex == 1
                ? const Text('History')
                : const Text('Account'),
      ),
      bottomNavigationBar: BottomNavigationBar(
        currentIndex: currentIndex,
        onTap: (value) {
          currentIndex = value;
          setState(() {});
        },
        type: BottomNavigationBarType.fixed,
        items: const [
          BottomNavigationBarItem(
            label: 'Home',
            icon: Icon(Icons.home),
          ),
          BottomNavigationBarItem(
            label: 'History',
            icon: Icon(Icons.history),
          ),
          BottomNavigationBarItem(
            label: 'Account',
            icon: Icon(Icons.account_circle),
          ),
        ],
      ),
    );
  }
}
```

{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
