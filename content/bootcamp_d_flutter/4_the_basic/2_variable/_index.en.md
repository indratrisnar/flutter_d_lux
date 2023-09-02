---
title: "2. Variable"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "basic", "variable"]
---

A variable is a place or container that can hold a value. The values that can be stored vary depending on the type of variable. Variables in Dart can also be called objects where the class is a data type. Variable types will be discussed in the next material.

Before using variables, variables need to be registered first so that they are recognized by the compiler and can be run. Registering a variable or creating a variable is often called a variable declaration.

In the latest Dart programming language, it is necessary to specify in the variable declaration whether it is allowed to have no value or required to have a value. This is because there is an update that the programming already supports null safety. Variables that are allowed to be null are called nullable variables, while those that require a value are called non-nullable or required variables.

With null safety, it will further secure the application so there are no errors/bugs when it is released. However, it is not 100% full because it is possible that many sources are integrated with applications that are dynamic in nature. Null Safety is more emphasis on helping when coding, so that before the code is decompiled it will always be checked if there are required and nullable variables.

Variable declaration syntax.

```dart
tipeData number;
```

Syntax initialize variables and assign values to variables.

```dart
int number1 = 8;
int number2 = 6;

int? number3;
number3 = 23;

late int number4;
number4 = 50;
```

<br>
