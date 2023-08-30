---
title: "8. Consecutive Strings"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
keywords: ["dart", "codewars", "array", "fundamental"]
---

From: [Codewars](https://www.codewars.com/kata/56a5d994ac971f1ac500003e/dart)

You are given an array(list) strarr of strings and an integer k. Your task is to return the first longest string consisting of k consecutive strings taken in the array.

##### Example

```dart
strarr = ["tree", "foling", "trashy", "blue", "abcdef", "uvwxyz"], k = 2

Concatenate the consecutive strings of strarr by 2, we get:

treefoling   (length 10)  concatenation of strarr[0] and strarr[1]
folingtrashy ("      12)  concatenation of strarr[1] and strarr[2]
trashyblue   ("      10)  concatenation of strarr[2] and strarr[3]
blueabcdef   ("      10)  concatenation of strarr[3] and strarr[4]
abcdefuvwxyz ("      12)  concatenation of strarr[4] and strarr[5]

Two strings are the longest: "folingtrashy" and "abcdefuvwxyz".
The first that came is "folingtrashy" so
longest_consec(strarr, 2) should return "folingtrashy".

In the same way:
longest_consec(["zone", "abigail", "theta", "form", "libe", "zas", "theta", "abigail"], 2) --> "abigailtheta"
```

n being the length of the string array, if `n = 0` or `k > n` or `k <= 0` return `""` (return Nothing in Elm, "nothing" in Erlang).

<br>

##### My Solution - [Other](https://www.codewars.com/kata/56a5d994ac971f1ac500003e/solutions/dart)

```dart
String longestConsec(List strarr, k) {
  if (strarr.isEmpty || k > strarr.length || k <= 0) return "";
  String longest = '';
  for (int i = 0; i <= strarr.length - k; i++) {
    String currentS = List.generate(k, (ki) => strarr[ki + i]).join();
    longest = currentS.length > longest.length ? currentS : longest;
  }
  return longest;
}
```

<br>

##### Test

```dart
void main() {
  print(
    longestConsec(["tree", "foling", "trashy", "blue", "abcdef", "uvwxyz"], 2),
  );
}

String longestConsec(List strarr, k) {
  if (strarr.isEmpty || k > strarr.length || k <= 0) return "";
  String longest = '';
  for (int i = 0; i <= strarr.length - k; i++) {
    String currentS = List.generate(k, (ki) => strarr[ki + i]).join();
    longest = currentS.length > longest.length ? currentS : longest;
  }
  return longest;
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
