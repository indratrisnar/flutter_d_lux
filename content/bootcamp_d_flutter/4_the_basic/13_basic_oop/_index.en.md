---
title: "13. Basic Object Oriented programming"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords: ["dart", "flutter", "bootcamp", "oop"]
---

Object Oriented programming (OOP) is a paradigm in programming that refers to an object. There are various kinds of objects here. Dart is a programming that uses the OOP paradigm in addition to the functional paradigm. All variables created in Dart are objects.

- [Class](#1-class)
- [Object](#2-object)
- [Constructor](#3-constructor)
- [Static](#4-static)

<br>

#### 1. Class

A class is a framework or template that has attributes and behavior. We can say that attributes are characteristics, properties, or variables in program code. Behavior is something that the class can do, we can say it is a function or method. If we want to use this class template, we need to create the object first, the method is the same as using variables. Because actually the variable is an object of its data type.

Example classes:

```dart
class Cat {
  String color = 'white';
  double weight = 4.5;

  eat() {
    print('favorite food: fish');
  }
}
```

<br>

#### 2. Object

Class and object analogies such as Car with BMW, Koeniggseg, Bugatti or like Bird with Eagle, Stork. From the Cat class above we can create one or more objects. We can also modify properties and methods if possible. We give these properties and methods modifiers or public access rights, so that all objects can access them.

For the property above, it can act as a getter, which is a way to retrieve the property value, and as a setter to modify the property value, but specifically for that object. getters and setters have the same name as the property name.

```dart
void main() {
  Cat cat1 = Cat(); // object 1
  print(cat1.color);
  print(cat1.weight);
  cat1.eat();

  print('--------------');

  Cat cat2 = Cat(); // object 2
  print(cat2.color);
  print(cat2.weight);
  cat2.eat();

  print('--------------');

  Cat cat3 = Cat(); // object 3
  cat3.color = 'Brown';
  cat3.weight = 2.5;
  print(cat3.color);
  print(cat3.weight);
  cat3.eat();
}
```

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

The following is an example of a private property, which cannot be accessed directly by the object if it is in a different file. If it is in the same file, it can still be accessed even if we make the properties private. To mark it as private, add an underscore (\_) in front of the object/variable name.

<br>

```dart
class Cat {
  String _color = 'white';
  double _weight = 4.5;
}
```

If it is private and you want it to be accessible to the object, then create your own setters and getters. For setters, there must be 1 parameter as new data. The way to use it is the same as the first example.

```dart
class Cat {
  String _color = 'white';
  double _weight = 4.5;

  String get color => _color;
  double get weight => _weight;

  set color(String newColor){
    _color = newColor;
  }
  set weight(String newWeight){
    _color = newWeight;
  }
}
```

<br>

#### 3. Constructor

Creating objects and at the same time initializing property values can use constructors. The constructor name is the same as the class name. To send initial data from object creation to be entered into properties using arguments. The use of constructor arguments is the same as the use of parameters in methods / functions.

```dart
void main() {
  Bird bird = Bird(3, 'green');
  bird.show();
}

class Bird {
  int wings;
  String color;

  Bird(this.wings, this.color); // constructor

  show() {
    print('wings: $wings');
    print('color: $color');
  }
}
```

{{< image src="3_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

This keyword is used to access anything in the Bird class. In order to be able to fill in arguments without paying attention to position, you can change the argument syntax to named arguments.

```dart
void main() {
  Bird bird = Bird(
    color: 'red',
    wings: 2,
  );
  bird.show();
}

class Bird {
  int wings;
  String color;
  bool? hasTail;

  Bird({
    required this.wings,
    required this.color,
    this.hasTail,
  });

  show() {
    print('wings: $wings');
    print('color: $color');
    print('hasTail: $hasTail');
  }
}
```

{{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 4. Static

If you want to access data in a class without creating the object first, you can add the static keyword at the beginning of the property or method.

```dart
void main() {
  int wings = Bird.wings;
  print(wings);

  print(Bird.color);

  Bird.eat();
}

class Bird {
  static int wings = 2;
  static String color = 'white';

  static eat() {
    print('Birds can eat using their beaks');
  }
}
```

{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
