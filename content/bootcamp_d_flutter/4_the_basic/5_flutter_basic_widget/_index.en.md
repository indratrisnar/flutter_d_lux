---
title: "5. Flutter Basic Widget"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "basic", "widget"]
---

Some basic widgets that are often used, including:

- [Container](#1-container)
- [Text](#2-text)
- [Icon](#3-icon)
- [Image](#4-image)
- [Button](#5-button)
- [Additional Widgets](#6-additional-widgets)

<br>

#### 1. Container

Container is a Box widget. Containers are often used as widget sizes because they have a size property. Containers can also position themselves based on the size of the child and the size of the root/wrapper.
The following is a simple example of a container shape that follows the root size, namely the body/main screen of the page/scaffold.
The image below also explains the code structure for the future in Flutter Basic Widget.

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Some of the Container properties that are often used as well as their application can be checked below:

```dart
Container(
  decoration: BoxDecoration(
    color: Colors.amber,
    borderRadius: BorderRadius.circular(16),
  ),
  width: 200,
  height: 100,
  margin: const EdgeInsets.only(
    left: 20,
    top: 20,
  ),
  padding: const EdgeInsets.all(20),
  child: const Text('Container'),
),
```

{{< image src="1_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| No  | Color  | Property | Use for                                            |
| :-: | ------ | -------- | -------------------------------------------------- |
|  1  | red    | margin   | Distance to the outside of the Container side      |
|  2  | blue   | padding  | Distance to the inside/child of the Container side |
|  3  | purple | radius   | Container corner arches.                           |

Note: There are 2 color properties for the main color and the color in the decoration. If we use a Container and there is a color, then use the color in the decoration. If you use the main color and there is a decoration, an error will occur.

<br>

#### 2. Text

Text is a typography widget. The data displayed or entered into this widget must be of the String data type. Equipped with properties for styling to make this widget more customizable.
Some frequently used Text properties and their applications can be checked below:

```dart
Text(
  'This is widget text',
  style: TextStyle(
    color: Colors.purple,
    fontWeight: FontWeight.bold,
    fontSize: 24,
  ),
),
```

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | Property                                | Use for                      |
| :------------------------------: | --------------------------------------- | ---------------------------- |
|                1                 | First parameter (‘This is widget text’) | Required data of type String |
|                2                 | style                                   | Modifikasi text              |
|                3                 | color                                   | Text modification            |
|                4                 | fontWeight                              | Text thickness               |
|                5                 | fontSize                                | Size text                    |

<br>

#### 3. Icon

Icons are image widgets but more specifically like symbols. Used as a label for certain simple information.

Some Icon properties that are often used as well as their application can be checked below:

```dart
Icon(
  Icons.location_on,
  color: Colors.red,
  size: 80,
),
```

{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | <div style="width:120px">Property</div> | Use for                                                                                                                     |
| :------------------------------: | --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
|                1                 | First parameter (Icons.location_on)     | Required data of type IconData. Where the default design follows Google's design guide. The newest design guide Material 3. |
|                2                 | color                                   | Provides a color, the type is color.                                                                                        |
|                3                 | size                                    | Icon size, type is double.                                                                                                  |

<br>

#### 4. Image

There are 4 supported resource images, namely from assets, network, memory, and files. Calling the widget does not go directly to the Image class name, but via the ui method which is divided into 4 above. Even though there is a class whose name is Image, the way to use it is different.

For network images, memory, and files. The data source comes from the URL, imageBytes with type UInt8List/List\<int>, and the file itself with the required path data/location of the image file in storage. Meanwhile, for image.asset, the asset location must be registered first in pubspeck.yaml and then the asset location data can be used as shown in the image below.

{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Some of the Image properties that are often used as well as their application can be checked below:

```dart
Image.network(
  imageURL,
  width: 150,
  height: 180,
  fit: BoxFit.cover,
),
```

{{< image src="4_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | <div style="width:120px">Property</div>                                                              | Use for                                                                  |
| :------------------------------: | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
|                1                 | First parameter ( <br>URL as String,<br>Asset as String,<br>Bytes as Uint8List,<br>File as File<br>) | Required data with the type depending on the type of image               |
|                2                 | width                                                                                                | Image width                                                              |
|                3                 | height                                                                                               | Image height                                                             |
|                4                 | fit                                                                                                  | How to insert an image into the available space/size of the image widget |

<br>

#### 5. Button

Widgets that provide certain actions, one of which is onPressed. The types of buttons that are often used and follow the design guide are divided into 3, namely ElevatedButton, OutlinedButton, and TextButton.

Some frequently used Button properties and their applications can be checked below:

```dart
ElevatedButton(
  onPressed: () {},
  child: const Text('Publish'),
),
OutlinedButton(
  onPressed: () {},
  child: const Text('Publish'),
),
TextButton(
  onPressed: () {},
  child: const Text('Publish'),
),
```

{{< image src="5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | <div style="width:120px">Property</div> | Use for                                                       |
| :------------------------------: | --------------------------------------- | ------------------------------------------------------------- |
|                1                 | onPressed                               | The required callback is used for the press action.           |
|                2                 | child                                   | Its child widgets can include general widgets, not just text. |

<br>

#### 6. Additional Widgets

Widgets additional widgets that are used as complements, tools, parts, positioning and others. However, here only a few are used.

```dart
Center(
  child: Text('Center'),
),
```

{{< image src="6.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
Material(
  child: Padding(
    padding: EdgeInsets.all(20),
    child: Text('Padding - all.20'),
  ),
),
```

{{< image src="6_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
Align(
  alignment: Alignment.bottomRight,
  child: Text('Align - bottom right'),
),
```

{{< image src="6_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
SizedBox(
  width: 100,
  height: 100,
  child: Container(
    color: Colors.amber,
  ),
),
```

{{< image src="6_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:30px">No</div> | <div style="width:120px">Widget</div> | Use for                                                                                                                                                             |
| :------------------------------: | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                1                 | Center                                | Make the widget a child so that it is in the middle.                                                                                                                |
|                2                 | Align                                 | Make the widget a child for a custom position.                                                                                                                      |
|                3                 | Padding                               | Wrapping child widgets, so that there is distance/space from the outermost line of the child to the wrapping widget. Same as the padding property in the Container. |
|                4                 | SizedBox                              | As a root box or other widget wrappers that don't have a fixed size. Can also be used as a space / distance between child-1 with other children in the layout.      |

<br>
