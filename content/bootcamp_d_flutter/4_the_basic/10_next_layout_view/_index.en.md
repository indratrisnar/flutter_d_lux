---
title: "10. Next Layout View"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords: ["dart", "flutter", "bootcamp", "basic", "layout", "view"]
---

After learning basic layouts, it's time to learn advanced layouts.

- [SingleChildScrollView](#1-singlechildscrollview)
- [ListView](#2-listview)
- [GridView](#3-gridview)
- [Wrap](#4-wrap)
- [PageView](#5-pageview)

<br>

#### 1. SingleChildScrollView

If you use a Column or Row layout and the data it holds exceeds the screen limit or available space, an overflow error will occur. For the handle, you can use SingleChildScrollView as a Column or Row wrapper. After wrapping SingleChildScrollView there will be no overflow error and column/Row can be scrolled.

As a Column wrapper, there is no other addition because the scrollDirection auto property is set to vertical. However, if it is used as a Row wrapper, the scrollDirection property is made horizontal.

Return to its main function to provide scroll access to the widget it's wrapped in, it doesn't have to be a layout widget, a single widget can.

```dart
SingleChildScrollView(
  child: Column(
    children: [
      Container(height: 200, width: 250, color: Colors.purple),
      Container(height: 200, width: 250, color: Colors.yellow),
      Container(height: 200, width: 250, color: Colors.blue),
      Container(height: 200, width: 250, color: Colors.orange),
      Container(height: 200, width: 250, color: Colors.green),
      Container(height: 200, width: 250, color: Colors.red),
    ],
  ),
),
```

{{< image src="1.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
SingleChildScrollView(
  scrollDirection: Axis.horizontal,
  child: Row(
    children: [
      Container(height: 100, width: 150, color: Colors.purple),
      Container(height: 100, width: 150, color: Colors.yellow),
      Container(height: 100, width: 150, color: Colors.blue),
      Container(height: 100, width: 150, color: Colors.orange),
      Container(height: 100, width: 150, color: Colors.green),
      Container(height: 100, width: 150, color: Colors.red),
    ],
  ),
),
```

{{< image src="1_2.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
String imageURL =
        'https://images.pexels.com/photos/14488109/pexels-photo-14488109.jpeg?auto=compress&cs=tinysrgb&w=1600&lazy=load';

SingleChildScrollView(
  scrollDirection: Axis.horizontal,
  child: Image.network(
    imageURL,
    width: 500,
    height: 300,
    fit: BoxFit.cover,
  ),
),
```

{{< image src="1_3.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

More: [SingleChildScrollView class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/SingleChildScrollView-class.html)

<br>

#### 2. ListView

ListView is a combination of Column/Row and SingleChildScrollView widgets with several additional properties depending on the type of listview. There is a basic ListView type and there is also a builder/generate.

By default for all children, the cross axis size is if it is scrollDirection.vertical then the width and scrollDirection.horizontal then the height will be expanded, even though each child has its own size. If the child's original size is to be maintained then it must be wrapped using a positioning helper widget such as Align.

In the case of a horizontal ListView, it needs to be wrapped using a widget box that has a size such as a Container or SizedBox, if the listview is in a Column/Listview layout. The shape is nested (inside the listview there is another listview).

```dart
ListView(
  padding: const EdgeInsets.all(16),
  children: [
    Align(
      alignment: Alignment.centerRight,
      child: Container(height: 100, width: 150, color: Colors.purple),
    ),
    Container(height: 100, width: 150, color: Colors.yellow),
    Center(
      child: Container(height: 100, width: 150, color: Colors.blue),
    ),
    Container(height: 100, width: 150, color: Colors.orange),
    Container(height: 100, width: 150, color: Colors.green),
    Container(height: 100, width: 150, color: Colors.red),
    Container(
      margin: const EdgeInsets.only(top: 30),
      height: 200,
      color: Colors.blue[200],
      child: ListView(
        scrollDirection: Axis.horizontal,
        children: [
          Container(height: 100, width: 150, color: Colors.purple),
          Container(height: 100, width: 150, color: Colors.yellow),
          Container(height: 100, width: 150, color: Colors.blue),
          Container(height: 100, width: 150, color: Colors.orange),
          Container(height: 100, width: 150, color: Colors.green),
          Container(height: 100, width: 150, color: Colors.red),
        ],
      ),
    ),
  ],
),
```

Output:
{{< image src="2_1.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

For the builder and generate versions, you can check below:

```dart
List colors = [
  Colors.blue,
  Colors.yellow,
  Colors.purple,
  Colors.green,
  Colors.red,
  Colors.orange,
];

ListView.builder(
  itemCount: colors.length,
  itemBuilder: (context, index) {
    Color itemColor = colors[index];
    return Container(
      margin: const EdgeInsets.only(bottom: 16),
      color: itemColor,
      height: 200,
    );
  },
),
```

Output:
{{< image src="2_2.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

More: [ListView class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/ListView-class.html)

<br>

#### 3. GridView

The same as listview in terms of its use to view lists, but there are settings for the number of columns such as a table form / combination of Rows and Columns.

There is a prominent and required property, namely gridDelegate. There are 2 types that we can use to fill this delegate apart from custom.

- SliverGridDelegateWithFixedCrossAxisCount\

Fixed grid size based on the number of crossAxisCount (number of grids)

- SliverGridDelegateWithMaxCrossAxisExtent\

The number of dynamic grids depends on the maximum size of the children and the available space. If there is no space left for width (vertical axis direction), it will automatically go down.

```dart
List colors = [
  Colors.blue,
  Colors.yellow,
  Colors.purple,
  Colors.green,
  Colors.red,
  Colors.orange,
  Colors.cyan,
];

GridView(
  padding: const EdgeInsets.all(8),
  gridDelegate: const SliverGridDelegateWithFixedCrossAxisCount(
    crossAxisCount: 3,
    mainAxisSpacing: 16,
    crossAxisSpacing: 8,
    childAspectRatio: 0.8,
  ),
  children: List.generate(colors.length, (index) {
    return Container(color: colors[index]);
  }),
),

GridView.builder(
  itemCount: colors.length,
  padding: const EdgeInsets.all(8),
  gridDelegate: const SliverGridDelegateWithFixedCrossAxisCount(
    crossAxisCount: 3,
    mainAxisSpacing: 16,
    crossAxisSpacing: 8,
    childAspectRatio: 0.8,
  ),
  itemBuilder: (context, index) {
    return Container(color: colors[index]);
  },
),
```

Output:
{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

More: [GridView class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/GridView-class.html)

<br>

#### 4. Wrap

Wrap is a layout widget that is a combination of Column and Row. The priority for the arrangement is Row, if there is no more space then create a new Row below it. Where each row is arranged vertically, that is why this widget is called the result of a combination of Row and Column.

Spacing in Wrap is the same as using spacing in GridView, there is space between items and space between Rows. For child widgets, usually use Chip or ActionChip.

```dart
List<String> animals = [
  'Spongebob',
  'Patrick',
  'Squidward',
  'Mr.Crab',
  'Krabby Patty',
];

Padding(
  padding: const EdgeInsets.all(8.0),
  child: Wrap(
    spacing: 8,
    runSpacing: 8,
    children: animals.map((e) {
      String firstCharacter = e.substring(0, 2);
      return Chip(
        avatar: CircleAvatar(
          child: Text(
            firstCharacter,
            style: const TextStyle(fontSize: 12, height: 1),
          ),
        ),
        label: Text(e),
      );
    }).toList(),
  ),
),
```

Output:
{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

More: [Wrap class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/Wrap-class.html)

<br>

#### 5. PageView

In web programming, PageView is the same as a carousel. We can use this layout to insert UI fragments / child pages, it can also be used for special UI such as image carousels and others. For the size of the pageview, follow the rules from ListView.

For the horizontal direction, it's best to add a physical property with the data for BouncingScrollPhysics() to avoid nested scroll behavior clashing errors. To set the width of the child carousel, you can use viewportFraction in the PageController.

By default, the scroll behavior uses the snapping action. If you want it to be the same as the scroll behavior of lists in general, you can change the pageSnapping value to false.

```dart
List travels = [
  'https://images.pexels.com/photos/1271619/pexels-photo-1271619.jpeg?auto=compress&cs=tinysrgb&w=1600',
  'https://images.pexels.com/photos/2166559/pexels-photo-2166559.jpeg?auto=compress&cs=tinysrgb&w=1600',
  'https://images.pexels.com/photos/16762297/pexels-photo-16762297/free-photo-of-aerial-photo-of-the-coastline-in-the-city.jpeg?auto=compress&cs=tinysrgb&w=1600',
  'https://images.pexels.com/photos/1659438/pexels-photo-1659438.jpeg?auto=compress&cs=tinysrgb&w=1600',
];

AspectRatio(
  aspectRatio: 16 / 9,
  child: PageView.builder(
    controller: PageController(viewportFraction: 0.7),
    itemCount: travels.length,
    scrollDirection: Axis.horizontal,
    physics: const BouncingScrollPhysics(),
    itemBuilder: (context, index) {
      return Padding(
        padding: const EdgeInsets.symmetric(
          horizontal: 8,
        ),
        child: Image.network(
          travels[index],
          fit: BoxFit.cover,
        ),
      );
    },
  ),
),
```

Output:
{{< image src="5.gif" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

More: [PageView class - widgets library - Dart API (flutter.dev)](https://api.flutter.dev/flutter/widgets/PageView-class.html)

<br>
