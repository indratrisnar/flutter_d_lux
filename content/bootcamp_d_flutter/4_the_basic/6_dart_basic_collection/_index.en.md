---
title: "6. Dart Basic Collection"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  ["dart", "flutter", "bootcamp", "basic", "collection", "list", "map", "set"]
---

Collection is a collection of data with certain characteristics, properties, types. It can also be referred to as a variable type that can hold more than 1 data where the data must be of the same type or may be different. Collection in Dart is divided into 3 namely List, Set, and Map.

- [List](#1-list)
- [Set](#2-set)
- [Map](#3-map)

<br>

#### 1. List

List is a data type that can accommodate a lot of data. The data that is stored or entered into it is called an element. Elements can be of the same or different types depending on how we declare the List type. All list elements are wrapped using the square bracket symbol “[]”.

By default it can accommodate elements of various types because the automatic system is dynamic. However, if we narrow it down or specialize it to only accommodate integer data, then the elements that can be entered or accommodated must be of the integer type.

The following is an example of declaration, initialization and combination.

| No  | Declaration        | Initialization             | Combined                        |
| :-: | ------------------ | -------------------------- | ------------------------------- |
|  1  | List menu          | menu = [1,"Apel",true];    | List menu = [1,"Apel",true];    |
|  2  | List\<String> menu | menu = ["Burger","Pizza"]; | List\<String> menu = ["A",'c']; |

List is like the arrangement of hotel rooms. The hotel room here is an element. How to differentiate hotel room 1 from the others using the room number. In the List there is an **index** for numbering where the elements are located. So the way to access the element we want is by using index. The index number always starts with the value **0**. So the first element is at index 0. However, if we access an index that is not in the list, an error will occur **Uncaught Error: RangeError (index): Index out of range**.

For example, there is a memory list, if we want to get a Pizza element, we must use index 0 and if we want to get a true element, we use index 2. This example can be seen in the code below.

```dart
void main() {
  List ingatan = ['Pizza', 9, true, 3.14, 'A', "Go"];

  String firstElement = ingatan[0];

  print(firstElement);
  print(ingatan[2]);
}
```

Note: for this test code, you can go through [DartPad](https://dartpad.dev/?)

Output:
{{< image src="pizza_true.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Because each variable is an object of a class, the **memory** above is an **object** and **List** is the **class**. So the object, namely the menu, can access and use the attributes and methods of the **List** class. Likewise, the data/elements follow the type of the element.

Some attributes/properties and methods that are often used for Lists:

```dart
void main() {
  List ingatan = ['Pizza',9,true,3.14,'A',"Go"];

  print(ingatan);
  ingatan.add('Emplod');
  print(ingatan);

  print('\n-------------------');
  print(ingatan);
  print('isEmpty: ${ingatan.isEmpty}');
  ingatan.clear();
  print(ingatan);
  print('isEmpty: ${ingatan.isEmpty}');

  print('\n-------------------');
  ingatan = ['Pizza',9,true,3.14];
  print(ingatan);
  ingatan[1] = 'Burger';
  print(ingatan);
  ingatan.removeAt(3);
  print(ingatan);
  print(ingatan.length);
}
```

Note: for this test code, you can go through [DartPad](https://dartpad.dev/?)

Output:
{{< image src="list.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width:25px">No</div> | <div style="width:150px">Property/method</div> | Use for                                                                                                           |
| :------------------------------: | ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
|                1                 | add()                                          | Adding new data after the last index                                                                              |
|                2                 | isEmpty                                        | Check if the list is empty?                                                                                       |
|                3                 | clear()                                        | Delete/Empty list                                                                                                 |
|                4                 | list[index]=n;                                 | How to update elements based on index where list is the name of the object/variable and n is the new data/element |
|                5                 | removeAt                                       | Menghapus berdasarkan posisi index                                                                                |
|                6                 | length                                         | Count the number of data / elements in the list                                                                   |

More about list: [Collections | Dart](https://dart.dev/language/collections#lists)

<br>

#### 2. Set

Almost exactly like **List** but the elements that are accommodated are only unique elements that are different from other elements. If we add new data but there is already the same data in it, then the new data is not entered. If the initial data contains the same data, then when calculating, using, retrieving the data list it will only bring the data in the first order. The same data/elements in the last position will not be carried over. To wrap data, use curly braces.

```dart
void main() {
  Set ingatan = {'Pizza',9,true,3.14,'A',"Go",true};
  print(ingatan);
}
```

Note: for this test code, you can go through [DartPad](https://dartpad.dev/?)

Output:
{{< image src="set.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

From the output results above, the **true** value at the back is not carried over because there is already a **true** value at the front.

To access elements based on index, you can use the function: memory.**elementAt(5)**.

More about the set: [Collections | Dart](https://dart.dev/language/collections#sets)

<br>

#### 3. Map

From a data collection perspective, it is the same as List and Set. However, element numbering is more flexible. We can determine the element/data room position numbers ourselves because the elements in the Map are structured based on **key** and **value**. **Key** is the position of the room, the book can determine what type it is and what its value is. Likewise, what type of **Value** is it and what is its value. The data wrapper is like Set.

For data access, it is similar to **List** but adjusted again to the data type of the **key**. If you just declare **Map** then it means it has the types **key** dynamic and **value** dynamic. If you want to be specific, you can make it like **Map\<String,int>**, meaning it has a String key type and an integer value. If you access a key that is not listed in the map, it will return **null**.

Example of using map:

```dart
void main() {
  Map<int,String> fruits = {
    1:'Mangga',
    2:'Apel',
    5:'Pepaya',
    10:'rambutan'
  };
  Map<String,dynamic> country = {
    'Tokyo':'Japan',
    'Jakarta':'Indonesia',
    'Seoul':'Korea Selatan',
  };
  print(fruits);
  print(country);
  print('------------------');
  print(fruits[5]);
  print(country['Seoul']);
  print(country.length);
}
```

Note: for this test code, you can go through [DartPad](https://dartpad.dev/?)

Output:
{{< image src="map.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

More about the map: [Collections | Dart](https://dart.dev/language/collections#maps)

<br>
