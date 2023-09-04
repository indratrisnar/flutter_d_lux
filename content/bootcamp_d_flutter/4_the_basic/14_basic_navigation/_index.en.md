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

Navigation here is moving pages, using the Navigator class. The intention of moving here is not purely to change the page, there are rules. There are rules that apply the concept of a stack or stacks.

The meaning of stack here is, for example, there is a home page, then it is stacked with page 2 so that what is visible in the application now is page 2. This does not mean moving by replacing it, but stacking it. If page 2 is closed or the code means it is destroyed, the Home page will appear again.

In addition to being stacked, there are also those that are completely replaced. This page replacement flow means destroying the old page, then loading the new page.

Not only moving pages, but can also carry data. Can from old page to new page or vice versa. There are two ways to navigate or move pages. Need while looking into the source code for further understanding. Before entering the Imperative/Declarative Page, there is a HomePage as the root app page.

- [Imperative](#1-imperative) - ([Push](#11-push), [Replace](#12-replace), [Send](#13-push-with-data), [Get](#14-push-then-get-data))
- [Declarative](#2-declarative) - ([Push](#21-push), [Replace](#22-replace), [Send](#23-push-with-data), [Get](#24-push-then-get-data))

{{< image src="home.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 1. Imperative

{{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

###### 1.1. Push

Recall the page is then stacked on top of the current page.

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

Destroying the current page then calls a new page to replace the destroyed page.

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

How to move pages along with sending data to the destination page using the Constructor argument.

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

After returning to the current page, receive data sent from the new page.

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

When click back button on appBar, it will return null.

<br>

#### 2. Declarative

To implement declarative routing, you need to first declare the route name that will be used in the MaterialApp.

{{< image src="2_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

###### 2.1. Push

Recall the page is then stacked on top of the current page.

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

Destroying the current page then calls a new page to replace the destroyed page.

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

How to move pages and send data to the destination page using arguments from route settings.

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

After returning to the current page, receive data sent from the new page.

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

When click back button on appBar, it will return null.

<br>
