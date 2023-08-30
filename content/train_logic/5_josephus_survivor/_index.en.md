---
title: "5. Josephus Survivor"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
# search related keywords
keywords:
  [
    "dart",
    "codewars",
    "array",
    "list",
    "mathematics",
    "combinatorics",
    "algorithms",
  ]
---

From: [Codewars](https://www.codewars.com/kata/555624b601231dc7a400017a/dart)

In this kata you have to correctly return who is the "survivor", ie: the last element of a [Josephus permutation](http://www.codewars.com/kata/josephus-permutation/).

Basically you have to assume that n people are put into a circle and that they are eliminated in steps of k elements, like this:

```dart
n=7, k=3 => means 7 people in a circle
one every 3 is eliminated until one remains
[1,2,3,4,5,6,7] - initial sequence
[1,2,4,5,6,7] => 3 is counted out
[1,2,4,5,7] => 6 is counted out
[1,4,5,7] => 2 is counted out
[1,4,5] => 7 is counted out
[1,4] => 5 is counted out
[4] => 1 counted out, 4 is the last element - the survivor!
```

The above link about the "base" kata description will give you a more thorough insight about the origin of this kind of permutation, but basically that's all that there is to know to solve this kata.

Notes and tips: using the solution to the other kata to check your function may be helpful, but as much larger numbers will be used, using an array/list to compute the number of the survivor may be too slow; you may assume that both n and k will always be >=1.

<br>

##### My Solution - [Other](https://www.codewars.com/kata/555624b601231dc7a400017a/solutions/dart)

```dart
int josephusSurvivor(int n, int k) {
  List arr = List.generate(n, (i) => i + 1);
  int i = 0;
  while (arr.length > 1) {
    i += k - 1;
    i = i < arr.length ? i : i % arr.length;
    arr.removeAt(i);
  }
  return arr.first;
}
```

<br>

##### Test

```dart
void main() {
  int n = 7;
  int k = 3;
  print(josephusSurvivor(n, k));
}

int josephusSurvivor(int n, int k) {
  List arr = List.generate(n, (i) => i + 1);
  int i = 0;
  while (arr.length > 1) {
    i += k - 1;
    i = i < arr.length ? i : i % arr.length;
    arr.removeAt(i);
  }
  return arr.first;
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
