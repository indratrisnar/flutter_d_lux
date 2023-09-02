---
title: "7. Flutter Basic Layout"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "basic", "layout"]
---

Each UI has a main structure that makes a view can be arranged with one another to match what we or the user want. The most basic widget layout is divided into 3.

- [Column](#1-column)
- [Row](#2-row)
- [Stack](#3-stack)

#### 1. Column

Layout Column is used to accommodate widgets arranged vertically (top to bottom / bottom to top). Because it can hold a lot of data/widgets, the property name is children with type List\<Widget>.

Column height depends on the number of children contained or depending on the size of the Column wrapper widget. Column width depends on the size of the longest child or based on the size of the widget that wraps the Column. If there are too many children and cannot all be displayed in the body area, an overflow error will occur.

Properties that are often used:

```dart
Column(
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisAlignment: MainAxisAlignment.center,
  mainAxisSize: MainAxisSize.max,
  children: [
    Text('Child ke-1 ajaskka'),
    SizedBox(height: 20),
    Text('Child ke-3 as'),
    SizedBox(height: 20),
    Text('Child ke-5 asiijuuhsa asjiajsa'),
    SizedBox(height: 20),
    Text('Child ke-7 asasas'),
    Text('Child ke-8'),
  ],
),
```

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:25px">No</div> | <div style="width:150px">Property</div> | Use for                                                                                                                                        |
| :------------------------------: | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
|                1                 | crossAxisAlignment (Red)                | Set the position of the children so that they are evenly matched based on the width of the Column. Example aligned left.                       |
|                2                 | mainAxisAlignment (Orange)              | Positioning children based on column height.                                                                                                   |
|                3                 | mainAxisSize (Blue)                     | Set the Column height size, whether it is prioritized according to the size of the widget wrapper or according to the number of children data. |

<br>

#### 2. Row

Same as Column, but different direction. Row Arranges children horizontally. The size is also reversed based on the Column size.

Properties that are often used:

```dart
Row(
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisAlignment: MainAxisAlignment.center,
  mainAxisSize: MainAxisSize.min,
  children: [
    Text('Child 1'),
    SizedBox(width: 10),
    Container(
      height: 80,
      width: 60,
      color: Colors.green,
    ),
    SizedBox(width: 10),
    Text('Child 5'),
  ],
),
```

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:25px">No</div> | <div style="width:150px">Property</div> | Use for                                                                                                                                    |
| :------------------------------: | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
|                1                 | crossAxisAlignment (Red)                | Set the position of the children so that they are evenly matched based on the height of the Row. Top level example (start).                |
|                2                 | mainAxisAlignment (Orange)              | Positions children based on Row width.                                                                                                     |
|                3                 | mainAxisSize (Blue)                     | Set the Row width size, whether it is prioritized according to the size of the wrapper widget or according to the number of data children. |

<br>

#### 3. Stack

Stack arranges children by stacking them. The stacking will show if the child is a different size because the stacking direction is back-to-front. The position behind is written first in children, while the last data in List children will be positioned at the top/front. This buildup is also affected by elevation, we just have to be smart to set this position where it is.

The size of the Stack follows the size of the widest child or the size of the wrapper widget. For certain cases it is recommended that the size follow the size of a wrapper widget such as SizedBox/Container so that UI errors do not occur such as implementing Expandable child widgets.

Properties that are often used:

```dart
Stack(
  alignment: Alignment.bottomRight,
  children: [
    Container(
      height: 180,
      width: 160,
      color: Colors.green,
    ),
    Container(
      height: 100,
      width: 100,
      color: Colors.yellow,
    ),
    Container(
      height: 80,
      width: 60,
      color: Colors.purple,
    ),
  ],
),
```

{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:25px">No</div> | <div style="width:150px">Property</div> | Use for                                                                                                                                           |
| :------------------------------: | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
|                1                 | alignment (Red)                         | Set the position of children relative to which direction. Example: bottomRight, all children will be positioned at the bottom right of the Stack. |

If you want the children to be positioned differently, each child is wrapped using a positioning widget such as Align. Example below:

```dart
Stack(
  alignment: Alignment.bottomRight,
  children: [
    Container(
      height: 180,
      width: 160,
      color: Colors.green,
    ),
    Container(
      height: 100,
      width: 100,
      color: Colors.yellow,
    ),
    Align(
      alignment: Alignment.topLeft,
      child: Container(
        height: 80,
        width: 60,
        color: Colors.purple,
      ),
    ),
  ],
),
```

{{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
