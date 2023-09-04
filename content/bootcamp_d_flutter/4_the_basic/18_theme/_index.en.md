---
title: "18. Theme"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords: ["dart", "flutter", "bootcamp", "theme", "mode"]
---

The theme is setup in the MaterialApp section or the main design rule guide, you can also use Cupertino but here we apply it to the Material version. The theme that will be implemented, only a few of the main ones including:

- [Mode](#1-mode)
- [Color](#2-color)
- [Text](#3-text)
- [Button](#4-button)
- [Material 3](#5-material-3)

<br>

#### 1. Mode

This mode is important for users who pay attention to dark colors which are set to Dark Mode. We simply setup theme rules for each mode, in the properties provided, namely theme for Light and darkTheme for dark. If you don't want to use both, just use one of the modes and the fixed theme, then just use the theme properties and set the brightness or you can copy & modify the default settings for light/dark only.

{{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="1_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="1_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 2. Color

The main color setup is divided into 3 or what is usually called a color palette, namely primary, secondary and tertiary (ascent). Apart from the main color, you can also set colors for each widget such as background, dialog, button, text, etc.

```dart
theme: ThemeData(
  brightness: Brightness.light,
  primaryColor: Colors.purple,
  scaffoldBackgroundColor: Colors.white,
  colorScheme: const ColorScheme.light(
    primary: Colors.purple,
    secondary: Colors.amber,
    tertiary: Colors.cyan,
  ),
),
darkTheme: ThemeData(
  brightness: Brightness.dark,
  primaryColor: Colors.purple,
  scaffoldBackgroundColor: Colors.black,
  colorScheme: const ColorScheme.dark(
    primary: Colors.purple,
    secondary: Colors.amber,
    tertiary: Colors.cyan,
  ),
),
```

How to use it using the Theme class.

```dart
Center(
  child: Container(
    height: 100,
    width: 100,
    color: Theme.of(context).primaryColor,
  ),
),
Center(
  child: Container(
    height: 100,
    width: 100,
    color: Theme.of(context).colorScheme.secondary,
  ),
),
Center(
  child: Container(
    height: 100,
    width: 100,
    color: Theme.of(context).colorScheme.onBackground,
  ),
),
Center(
  child: Container(
    height: 100,
    width: 100,
    color: Theme.of(context).colorScheme.tertiary,
  ),
),
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="2_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

#### 3. Text

You can customize it yourself by registering the text style in the theme.

```dart
textTheme: const TextTheme(
  labelSmall: TextStyle(
    fontSize: 30,
    color: Colors.green,
    fontWeight: FontWeight.bold,
  ),
),
```

```dart
Text(
  'Display Small',
  style: Theme.of(context).textTheme.displaySmall,
),
Text(
  'Headline Large',
  style: Theme.of(context).textTheme.titleLarge,
),
Text(
  'Copy Style',
  style: Theme.of(context).textTheme.labelLarge!.copyWith(
        color: Colors.amber,
      ),
),
Text(
  'Mix Style',
  style: TextStyle(
    fontSize: Theme.of(context).textTheme.titleLarge!.fontSize,
    color: Theme.of(context).colorScheme.tertiary,
  ),
),
Text(
  'My Own Style on labelSmall',
  style: Theme.of(context).textTheme.labelSmall,
),
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="3_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

#### 4. Button

```dart
elevatedButtonTheme: ElevatedButtonThemeData(
  style: ButtonStyle(
    backgroundColor: const MaterialStatePropertyAll(Colors.green),
    foregroundColor: const MaterialStatePropertyAll(Colors.white),
    minimumSize: const MaterialStatePropertyAll(
      Size.fromHeight(60),
    ),
    shape: MaterialStatePropertyAll(
      BeveledRectangleBorder(
        borderRadius: BorderRadius.circular(10),
      ),
    ),
  ),
),
```

```dart
ElevatedButton(
  onPressed: () {},
  child: const Text('Click Me'),
),
const SizedBox(height: 30),
// without custom theme / follow default
OutlinedButton(
  onPressed: () {},
  child: const Text('Click Me'),
),
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="4_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="4_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

#### 5. Material 3

Just use the useMaterial3 property and set it to true.

{{< image src="m3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

There are changes in the default settings for button styles and others. For example, a button that was originally a small corner so that the angle was clearly sharp, has now changed to a semi-circle at the end of the button.

```dart
OutlinedButton(
  onPressed: () {},
  child: const Text('Click Me'),
),
const SizedBox(height: 20),
Switch(
  value: true,
  onChanged: (value) {},
),
```

| Material 2                                                                                                                                                                                                                                                                                                                        | Material 3                                                                                                                                                                                                                                                                                                                        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="5_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} {{< image src="5_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="5_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} {{< image src="5_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>
