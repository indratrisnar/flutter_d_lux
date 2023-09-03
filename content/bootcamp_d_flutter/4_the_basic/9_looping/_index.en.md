---
title: "9. Looping"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  [
    "dart",
    "flutter",
    "bootcamp",
    "basic",
    "looping",
    "for",
    "for in",
    "for each",
    "while",
    "do-while",
  ]
---

To execute the same command multiple times, it is necessary to create/write the command as many times as desired. Example as below:

```dart
void main() {
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
  print('Halo, Selamat datang');
}
```

However, the code above is not efficient, especially if you want to display hundreds, thousands and so on. Looping is made for things like this. With looping, we create 1 instruction/statement then we set the number of repetitions. There are several ways to create a loop.

- [For](#1-for)
- [For In](#2-for-in)
- [For Each](#3-for-each)
- [While](#4-while)
- [Do-While](#5-do-while)
- [Implement to Flutter](#6-implement-to-flutter)

<br>

#### 1. For

<table>
<tr><th>The flow that occurs in for:</th></tr>
<tr><td>
Check conditions,<br>
If the condition is true, run everything in the {} for block, then return to Check condition<br>
If the condition is false, stop
</td></tr>
</table>

Contoh:

```dart
void main() {
  for (int index=0; index <= 9; index++) {
    print('$index. Halo, Selamat datang');
  }
}
```

explanation of block conditions: (initial, check, increment/decrement)<br>
**initial** : initial value for the nth looping / iteration position.<br>
**check** : check condition. If we want to loop 10 times, we can create a condition of index <= 9. This condition is created by paying attention to the initial and increment/decrement.<br>
**increment/decrement** : used to change the index value every time the condition evaluates to true. Increment means an upward change in the index value, decrement is the opposite. Changes from 1 to 1, or 2 levels, or others depending on the operator we use.

The output of the code above:
{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

For details, you can check the official documentation: [Loops | Dart](https://dart.dev/language/loops#for-loops)

<br>

#### 2. For In

<table>
<tr><th>The flow that occurs in for in:</th></tr>
<tr><td>
Take the nth element,<br>
Execute the command in the for in block.
</td></tr>
</table>

So by default, there is no limit to the number of repetitions performed. However, do as many repetitions as you have data. Data collection is required to perform for in.

Example:

```dart
void main() {
  List menu = ['Burger','Kebab','Nasgor','Martabak Telor'];
  for (String element in menu){
    print(element);
  }
}
```

Output:
{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

For details, you can check the official documentation: [Loops | Dart](https://dart.dev/language/loops#for-loops)

To customize the number of repetitions based on certain conditions, you can use break and continue [Loops | Dart](https://dart.dev/language/loops#break-and-continue)

<br>

#### 3. For Each

Same as for in. However, the syntax is different and it is more advisable to use for in rather than foreach.

Example:

```dart
void main() {
  List menu = ['Burger','Kebab','Nasgor','Martabak Telor'];
  menu.forEach((element){
    print(element);
  });
}
```

Output:
{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

For details, you can check the official documentation: [forEach method - Iterable class - dart:core library - Dart API](https://api.dart.dev/stable/3.0.0/dart-core/Iterable/forEach.html)

<br>

#### 4. While

The flow is the same as for. However, the syntax is different. The first time I checked, it turned out that the condition was false and immediately stopped. So nothing will appear in the console.

Example:

```dart
void main() {
  int index = 1;
  while(index<=3){
    print('Lup yu');
    index++;
  }
}
```

Output:
{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

For details, you can check the official documentation: [Loops | Dart](https://dart.dev/language/loops#while-and-do-while)

<br>

#### 5. Do-While

Similar to while but reversed flow. In While, check first then execute the {} block. Whereas in Do-While, first execute block {} then check. At the first time checking, it turns out that the condition is false immediately, then block {} will be executed first and then stopped. So it will appear at least 1 iteration / repetition.

Example:

```dart
void main() {
  int index = 1;
  do {
    print('Lup yu');
    index++;
  }while(index<=3);

  print('---------------');

  int i = 1;
  do {
    print('Lup yu');
    i++;
  }while(i<1);//false
}
```

Output:
{{< image src="5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

For details, you can check the official documentation: [Loops | Dart](https://dart.dev/language/loops#while-and-do-while)

<br>

#### 6. Implement to Flutter

It's time to implement it into Flutter by using several new functions to support the implementation into Flutter. However, the process flow until the UI appears uses a looping concept. For implementation into flutter, not all methods can be pasted.

<table>
<!-- 1 -->
<tr>
<td><div>

```dart
Column(
  children: [
    const Text('------------------'),
    for (int index = 1; index < 5; index++)
      Text('Ini ada pada Index $index'),
    const Text('------------------'),
  ],
),
```

</div></td>
<td>
{{< image src="6_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
</td>
</tr>
<!-- 2 -->
<tr>
<td><div>

```dart
List<String> animals = [
  'Cochroaces',
  'Simba',
  'Pikachu',
  'Salmon',
  'Turbo'
];

Column(
  children: [
    const Text('------------------'),
    for (String animal in animals) Text(animal),
    const Text('------------------'),
  ],
),
```

</div></td>
<td>
{{< image src="6_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
</td>
</tr>
</table>

And here are several ways to access, modify, and generate data lists that are directly carried out in the Flutter Code UI. Some are directly in the children/list property and some are using the help of the cascade operator.

<!-- 3 -->
<table>
<tr>
<td><div>

```dart
List<String> animals = [
  'Cochroaces',
  'Simba',
  'Pikachu',
  'Salmon',
  'Turbo'
];

Column(
  children: [
    const Text('------------------'),
    ...List.generate(animals.length, (index) {
      return Text(animals[index]);
    }),
    const Text('------------------'),
  ],
),

Column(
  children: List.generate(animals.length, (index) {
    return Text(
      '${index + 1}. ${animals[index]}',
    );
  }),
),
```

</div></td>
<td>
{{< image src="6_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
</td>
</tr>
</table>

With **List.generate** we can custom set the amount of data and get the index parameter, so there's no need to create a custom index yourself. The index function is also used to get the value/element of the list.

<!-- 4 -->
<table>
<tr>
<td><div>

```dart
List<String> animals = [
  'Cochroaces',
  'Simba',
  'Pikachu',
  'Salmon',
  'Turbo'
];

Column(
  children: [
    const Text('------------------'),
    ...animals.map((e) => Text(e)).toList(),
    const Text('------------------'),
  ],
),

Column(
  children: animals.map((e) {
    return Text(e);
  }).toList(),
),
```

</div></td>
<td>
{{< image src="6_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
</td>
</tr>
</table>

By using **.map()** and **toList()** we can access all the data and then modify its type. The flow is, every time in the nth iteration we take the value of element(e) then we enter it into the Text Widget and return it, then go to toList() (new list). What was originally **List\<String>** becomes **List\<Text>**.

<br>
