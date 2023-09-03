---
title: "11. Function"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords: ["dart", "flutter", "bootcamp", "function"]
---

Function is a certain block of code that is made in a class or public/global that is created/stored in a file. This affects the scope of the function. In general, the scope is divided into 2, global and local.

If it's inside a class, it's primarily accessible only within that class, or it can be accessed from the outside in some way. If it is in a file then it is global, meaning that it can be accessed anywhere as long as it imports the file location. However, whether or not it can be accessed from outside, you need to check whether the modifier or access rights are public or private. In Dart, if you want to make it private, you must add an underscore (\_) in front of the function name.

If the block function only has one line of code, it can be shortened by using the arrow function (=>). Arrow function can also be used as a return. So if you want to make a function return and shorten it, use the arrow function without the return keyword. For example, you can check in Implement to Flutter.

- [Type](#1-type)
- [Parameter](#2-parameter)
- [Implement to Flutter](#3-implement-to-flutter)

<br>

#### 1. Type

Function types are divided into 2, functions that have returns and without (voids). Dart supports dynamic types so that functions can be both returns and voids. Function return, requires that there is a value/data that is returned or returned to the place where the function was called. Function return has another type depending on the type of value. The type of the return value/data must be the same as the function type.

When calling the void function, it is enough to write its name along with brackets. There are 2 ways to call the function return, first by calling it directly in the output, second by calling it in the object/variable initialization process.

```dart
void main() {
  // function call
  print('---------------------------');

  printCity();
  printCountry();

  print('---------------------------');

  print(sum());
  int resultOfSum = sum();
  print(resultOfSum);

  print(area());
  double result = area() + 10;
  print(result);
}

// void function declaration
void printCity() {
  print('City: Garut');
}

// dynamic function declaration -> void (no return)
printCountry() {
  print('Country: Indonesia');
}

// return function declaration -> int
// type: int
// value: 0
int sum() {
  return 0;
}

// dynamic function declaration -> return -> double
area() {
  double resultOfArea = 5.2 * 2;
  return resultOfArea;
}
```

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 2. Parameter

Parameters are also called arguments. Its function is to hold data sent from the calling place, where the data stored in the parameter will be used in the function. Parameter declaration method is the same as variable declaration. If you want to make it a dynamic parameter type, just write the name without the type.

If there are multiple parameters, how to enter the value must be in the order separated by commas. Don't get it upside down, if it's upside down, an error can occur with one of the reasons being that each parameter has a different data type and has a different use.

In making parameters that can be changed, you can use named parameters. The declaration is wrapped in curly braces. For example, you can check Implement to Flutter.

```dart
void main() {
  printCity('Garut');
  printCity('Bandung');
  printCity('Los Humans');

  num result = sum(1, 2);
  num result2 = sum(4.3, 6);
  print(result);
  print(result2);
}

void printCity(String cityName) {
  print('City: $cityName');
}


num sum(double number1, double number2) {
  return number1+number2;
}
```

Output:
{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 3. Implement to Flutter

For callback implementations such as onPressed on ElevatedButton, direct function calls can be made without including brackets.

```dart
save() {
  print('save');
}

whenClicked() {
  print('whenClicked');
}

void sum() {
  print('sum: 2');
}

int substraction(int n1, int n2) => n1 - n2;

ListView(
  padding: const EdgeInsets.all(16),
  children: [
    ElevatedButton(
      onPressed: () {
        save();
      },
      child: const Text('Save'),
    ),
    const SizedBox(height: 16),
    ElevatedButton(
      onPressed: () => whenClicked(),
      child: const Text('When Cliked'),
    ),
    const SizedBox(height: 16),
    ElevatedButton(
      onPressed: sum,
      child: const Text('Sum'),
    ),
    const SizedBox(height: 16),
    ElevatedButton(
      onPressed: () {
        int result = substraction(5, 3);
        print('Substraction: $result');
      },
      child: const Text('Substraction'),
    ),
    const SizedBox(height: 16),
  ],
),
```

{{< image src="3_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

```dart
addProfile({
  required String name,
  required int age,
  String? imageURL,
}) {
  print('Name: $name');
  print('Age: $age');
  if (imageURL != null) {
    print('imageURL: $imageURL');
  }
}

ElevatedButton(
  onPressed: () => addProfile(name: 'Indre', age: 20),
  child: const Text('Add profile 1'),
),
const SizedBox(height: 16),
ElevatedButton(
  onPressed: () => addProfile(age: 7, name: 'Flutter'),
  child: const Text('Add profile 2'),
),
const SizedBox(height: 16),
ElevatedButton(
  onPressed: () {
    print('---------------');
    addProfile(age: 7, imageURL: 'fdl.png', name: ' F D Lux');
  },
  child: const Text('Add profile 3'),
),
```

{{< image src="3_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="3_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
