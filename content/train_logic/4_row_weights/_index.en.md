---
title: "4. Row Weights"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
# search related keywords
keywords: ["dart", "logic", "codewars", "row", "weight", "array"]
---

From: [Codewars](https://www.codewars.com/kata/5abd66a5ccfd1130b30000a9/dart)

##### Scenario

Several people are standing in a row divided into two teams.
The first person goes into team 1, the second goes into team 2, the third goes into team 1, and so on.

<br>

##### Task

Given an array of positive integers (the weights of the people), return a new array/tuple of two integers, where the first one is the total weight of team 1, and the second one is the total weight of team 2.

<br>

##### Notes

- Array size is at least 1.
- All numbers will be positive

<br>

##### Input >> Output Examples

```dart
rowWeights([13, 27, 49]) ==> return (62, 27)
```

The first element `62` is the total weight of team 1, and the second element `27` is the total weight of team 2.

<br>

```dart
rowWeights([50, 60, 70, 80])  ==>  return (120, 140)
```

The first element `120` is the total weight of team 1, and the second element `140` is the total weight of team 2.

<br>

```dart
rowWeights([80])  ==>  return (80, 0)
```

The first element `80` is the total weight of team 1, and the second element `0` is the total weight of team 2.

<br>

##### My Solution - [Other](https://www.codewars.com/kata/5abd66a5ccfd1130b30000a9/solutions/dart)

```dart
List<int> rowWeights(List<int> arr) {
  int team1 = 0, team2 = 0;
  for (var i = 0; i < arr.length; i++) {
    if (i.isEven) team1 += arr[i];
    if (i.isOdd) team2 += arr[i];
  }
  return [team1, team2];
}
```

<br>

##### Test

```dart
void main() {
  var array = [50, 60, 70, 80];
  print(rowWeights(array));
}

List<int> rowWeights(List<int> arr) {
  int team1 = 0, team2 = 0;
  for (var i = 0; i < arr.length; i++) {
    if (i.isEven) team1 += arr[i];
    if (i.isOdd) team2 += arr[i];
  }
  return [team1, team2];
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
