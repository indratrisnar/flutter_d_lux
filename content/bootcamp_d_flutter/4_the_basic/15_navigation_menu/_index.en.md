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

Navigation here is moving pages which are not actually the entire scaffold or screen, but changing views or partial displays on the screen. For example, there is a Dashboard Header/AppBar, the view that is moved or replaced is only the body or main content. If any of your friends have ever developed native Android using Android Studio Kotlin/Java, the meaning of the view here is the same as the fragment in Android native. To move/change views, you need a menu. There are several menu creations specifically for navigation views.

- [Drawer](#1-drawer)
- [Tab Bar](#2-tab-bar)
- [Bottom Navigation Bar](#3-bottom-navigation-bar)

<br>

#### 1. Drawer

The navigation menu that appears from the left / right of the screen by swiping or pressing the menu button icon on the appBar. In Scaffold, there is a property drawer and endDrawer to place Drawer views. And it will automatically create the Menu button icon in the leading/action appBar. Drawer has its Header view with the widget name DrawerHeader.

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

In order for the fragment or body to change according to the menu we click on in the Drawer menu, we need something to mark the position of the widget and to check it too. We can use index. Then the check implementation can use if else or use array/List data. To update the UI when the index value changes, it is necessary to call setState((){}). To close Drawer, you can use Navigator pop.

{{< image src="1_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 2. Tab Bar

TabBar menu usually inserted at the bottom of the AppBar. But it can also be custom attached to the body scaffold area. To implement the AppBar, you need a tab controller or use the DefaultTabController widget, so you don't need to think about how to use its index to change views. Simply add a TabBarView in the body region to change the view according to the order of the TabBar menu. DefaultTabBar is created in the top root which wraps the TabBar and TabBarView.

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

TabBarView already contains the swipe change view action, so we don't need to apply animations and other actions. On native Android, it is called a view pager.

<br>

#### 3. Bottom Navigation Bar

Similar to TabBar but there is no default controller provided, we have to make it manually like in the Drawer to change the view. Appears at the bottom of the screen with elevation above the Scaffold body. To implement this, the bottomNavigationBar property has been provided in the Scaffold. Based on the Material Design Guide, the number of menus in the bottom nav is a minimum of 3 and a maximum of 5. With menu items, just an icon or a label is displayed.

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
