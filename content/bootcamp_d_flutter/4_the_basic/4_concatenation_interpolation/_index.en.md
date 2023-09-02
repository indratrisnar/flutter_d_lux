---
title: "4. Concatenation & Interpolation"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  ["dart", "flutter", "bootcamp", "basic", "concatenation", "interpolation"]
---

How to combine or arrange a value or variable, then the results of the combination are displayed in the form or as string data. There are 2 ways, namely Concatenation and Interpolation.

1. Concatenation

Combining or arranging string-valued data. How to combine using the plus operator (+). If there is data/variables that have values other than Strings, they must be converted first to String form so they can be combined.

```dart
String name = "Flutter D Lux";
int age = 20;

print('1. Name: ' + 'Flutter D Lux' + ', ' + 'Age: ' + '20');
print('2. Name: ' + name);
print('3. Name: ' + name + ', '+'Age: ' + age.toString());

String content = '4. Name: ' + name + ', ' + 'Age: ' + age.toString();
String content2 = '5. Name: ' + name + ', Age: ' + age.toString();
print(content);
print(content2);
```

Output above:

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

2. Interpolation

Merging or compiling data with a String value or not a String. The method for merging or arranging is using the dollar symbol ($) and if there is an operation or an action object etc. then after the dollar ($) the data is wrapped using curly braces ({}). Data other than strings will be automatically converted to strings.

```dart
String name = "Flutter D Lux";
int age = 20;

print('1. Name: $name');
print('2. Name: $name, Age: ${age.toString()}');

String content = '3. Name: $name, Age: ${10+10}';
print(content);
```

Output above:

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
