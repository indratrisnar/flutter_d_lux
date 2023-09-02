---
title: "3. Dart Basic Type"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "basic", "data type"]
---

| <div style="width: 30px">No</div> | <div style="width:80px">Type</div> | <div style="width:80px">Syntax</div> | Description                                                                                                                                                                               |
| :-------------------------------: | ---------------------------------- | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                 1                 | Integer                            | int                                  | Can accommodate integer data.                                                                                                                                                             |
|                 2                 | Double                             | double                               | Can accommodate whole number data, fractional numbers and decimal numbers. If the value received is an integer, it will be converted into a fraction or decimal which has the same value. |
|                 3                 | Number                             | num                                  | Combine int and double.                                                                                                                                                                   |
|                 4                 | String                             | String                               | Can accommodate single or multiple character data in the form of words/sentences.                                                                                                         |
|                 5                 | Boolean                            | bool                                 | Can only hold Boolean data i.e. true and false.                                                                                                                                           |

<br>

1. Integer

```dart
int number1 = 8;
int number2 = 6;

int? number3;
number3 = 23;

late int number4;
number4 = 50;
```

<br>

2. Double

```dart
double number1 = 8.0;
double number2 = 6.4;
double number2 = 6;

double? number3;
number3 = 23.0;

late double number4;
number4 = 50;
```

<br>

3. Number

```dart
num number1 = 8;
num number2 = 6.0;

num? number3;
number3 = 23;

late num number4;
number4 = 50.3;
```

<br>

4. String

```dart
String character1 = ‘A’;
String character2 = “A”;
String word1 = “Flutter”;
String word1 = ‘dart’;
String sentences1 = ‘I\’m is Flutter’;
String sentences2 = “I’m is Flutter”;

String? character3;
character3 = ‘23’;

late String character4;
character4 = “50.3”;
```

<br>

5. Boolean

```dart
bool isRain = true;
bool isEmpty = false;

bool? isBigger;
isBigger = 23 > 20; // true

late bool isSame;
isSame = 50 == 49; // false
```

<br>
