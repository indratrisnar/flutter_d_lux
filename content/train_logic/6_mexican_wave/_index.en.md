---
title: "6. Mexican Wave"
date: 2023-08-29T11:14:45+07:00
lastmod: 2023-08-29T11:14:45+07:00
weight: 1
draft: false
# search related keywords
keywords: ["dart", "codewars", "array", "string", "fundamental"]
---

From: [Codewars](https://www.codewars.com/kata/58f5c63f1e26ecda7e000029/dart)

##### Introduction

The wave (known as the Mexican wave in the English-speaking world outside North America) is an example of metachronal rhythm achieved in a packed stadium when successive groups of spectators briefly stand, yell, and raise their arms. Immediately upon stretching to full height, the spectator returns to the usual seated position.

The result is a wave of standing spectators that travels through the crowd, even though individual spectators never move away from their seats. In many large arenas the crowd is seated in a contiguous circuit all the way around the sport field, and so the wave is able to travel continuously around the arena; in discontiguous seating arrangements, the wave can instead reflect back and forth through the crowd. When the gap in seating is narrow, the wave can sometimes pass through it. Usually only one wave crest will be present at any given time in an arena, although simultaneous, counter-rotating waves have been produced. (Source [Wikipedia](<https://en.wikipedia.org/wiki/Wave_(audience)>))

<br>

##### Tasks

In this simple Kata your task is to create a function that turns a string into a Mexican Wave. You will be passed a string and you must return that string in an array where an uppercase letter is a person standing up.

<br>

##### Rules

1. The input string will always be lower case but maybe empty.
2. If the character in the string is whitespace then pass over it as if it was an empty seat

<br>

##### Example

```dart
wave("hello") => {"Hello", "hEllo", "heLlo", "helLo", "hellO"}
```

<br>

##### My Solution - [Other](https://www.codewars.com/kata/58f5c63f1e26ecda7e000029/solutions/dart)

```dart
List<String> wave(String str) {
  List<String> list = [];
  for (var i = 0; i < str.length; i++) {
    if (str[i] == ' ') continue;
    list.add(str.replaceRange(i, i + 1, str[i].toUpperCase()));
  }
  return list;
}
```

<br>

##### Test

```dart
void main() {
  String str = 'hello';
  print(wave(str));
}

List<String> wave(String str) {
  List<String> list = [];
  for (var i = 0; i < str.length; i++) {
    if (str[i] == ' ') continue;
    list.add(str.replaceRange(i, i + 1, str[i].toUpperCase()));
  }
  return list;
}
```

<br>

##### Output

{{< image src="output.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
