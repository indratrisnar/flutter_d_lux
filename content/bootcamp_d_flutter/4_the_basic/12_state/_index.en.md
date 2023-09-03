---
title: "12. State"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords: ["dart", "flutter", "bootcamp", "state"]
---

State is the state at the time when. When here refers to the flow position, what position are we now in? The more detailed the meaning, the more you will understand as you practice. However, detailed information about the state can be accessed at: [State class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/State-class.html)

- [Lifecycle](#1-lifecycle)
- [Basic State Management](#2-basic-state-management)

<br>

#### 1. Lifecycle

The application life flow in Flutter which will be discussed, will be focused on Statefull lifecycle pages. And only the simple version so that the core lifecycle is quickly understood. Frequently used: initState, build, dispose.

| <div style="width:30px">No</div> | <div style="width:220px">Lifecycle</div> | Description                                                                                                                                 |
| :------------------------------: | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
|                1                 | createState                              | The state that must be created is automatically created when we create a Statefull Widget using the stf shortcut.                           |
|                2                 | initState                                | Initial state, usually used to initialize objects, data and others.                                                                         |
|                3                 | didChangeDependencies                    | Conditions that follow the initState step, it is recommended not to carry out actions such as initialization, requests to the backend, etc. |
|                4                 | build                                    | Where UI is built. Make sure the data is ready before being pasted into the UI.                                                             |
|                5                 | deactivate                               | Circumstances that follow dispose, but are called before dispose.                                                                           |
|                6                 | dispose                                  | The state when the page is closed/destroyed.                                                                                                |

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

To implement basic state management, we need to use **StatefullWidget** and **setState((){})**. The setState function is to trigger UI updates. setState is called When we want to display the latest data to the UI. Because the UI cannot update values/data automatically.

If we look at the flow state, when we call setState, the build() lifecycle will be executed again. This means that the UI in the 1st build state will be destroyed, then rebuilt. Then the state is in the 2nd build state and so on if setState is called again.

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
