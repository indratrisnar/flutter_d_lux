---
title: "8. Decision"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  [
    "dart",
    "flutter",
    "bootcamp",
    "basic",
    "decision",
    "if",
    "else",
    "switch",
    "case",
  ]
---

Decision making in dart programming is the same as decisions in other programming. Where conditions always have to have a Boolean value, true or false.

- [If Else](#1-if-else)
- [Switch Case](#2-switch-case)
- [Ternary If Else](#3-ternary-if-else)
- [Implement to Flutter](#4-implement-to-flutter)

<br>

#### 1. If Else

<table>
<tr><th>The flow that occurs in if-else:</th></tr>
<tr><td>
Check condition,
If the condition is true, execute everything in the {} if block, and ignore/skip the {} else and else if blocks (if any).
If the condition is false, execute everything in the {} else or else if block (if any).
</td></tr>
</table>

The use of else if and else is not mandatory, so if there is only an if block, that's okay.

Example:

```dart
void main() {
  bool isRain = true;

  if(isRain) {
    print('The water is falling');
   }else{
     print('It\'s sunny today');
  }
}
```

Output: **The water is falling**, because isRain is true.

Another example for comparison.

```dart
void main() {
  int number1 = 10;
  int number2 = 30;

  String comparison = '';
  if(number1 > number2) {
    comparison = 'bigger than';
  }else if(number1 == number2){
    comparison = 'equal to';
  }else{
    comparison = 'smaller than';
  }
  print('number1 is $comparison number2');
}
```

Output: **number1 is smaller than number2**, because if=false and else_if=false.

In the use of If else can occur nested, if else beget.

Example:

```dart
void main() {
  bool isRain = true;
  bool isDrop = true;
  bool isSunny = false;

  if(isRain){
     print('Yes, it\'s raining today');
     if(isDrop){
       print('and it\'s raining');
     }
   }else{
     print('No, it\'s not raining today');
     if(isSunny){
       print('and today is sunny');
     }
   }
}
```

Output:
{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

For further details, you can check the official documentation: [Branches | Dart](https://dart.dev/language/branches#if)

<br>

#### 2. Switch Case

It's the same as using an if else statement, there is a data condition check but with certain options and there needs to be a break to stop the scope of execute. If you don't use a break at the end of the case block, the next case will be executed too. Here there is also an automatic block that is executed if there is no suitable option/case, namely default.

Example:

```dart
void main() {
  String status = '';

  status = 'loading';
  switch(status) {
    case '':
        print('initial status');
        break;
    case 'loading':
        print('when loading');
        break;
    case 'success':
        print('when success');
        break;
    default:
        print('when failed');
        break;
  }
}
```

Output:
{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

For further details, you can check the official documentation: [Branches | Dart](https://dart.dev/language/branches#switch-statements)

<br>

#### 3. Ternary If Else

Inline form of if else. Block if marked symbol (?) and else marked (:).
Syntax: condition ? expression1 : expression2

Example:

```dart
void main() {
bool isRain = true;
  String sentences = isRain ? "today is raining" : 'today is sunny';
  print(sentence);

  num number1 = 63;
  num number2 = 50;
  String result = number1 > number2
    ? "number1 is bigger than number2"
    : 'number1 is smaller than or equal to number2';
  print(result);
}
```

Output:
{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 4. Implement to Flutter

```dart
bool isChecked = true;
bool isPicked = false;
bool isLoading = false;

Column(
  children: [
    const Text('1'),
    if (isChecked) const Text('Accepted Aggrement'),
    const Divider(),
    const Text('2'),
    if (isChecked)
      const Column(
        children: [
          Text('Accepted Aggrement'),
          Text('Accepted Regulation'),
        ],
      ),
    const Divider(),
    const Text('3'),
    isPicked
        ? const Text('You have picked image')
        : const Icon(Icons.add_a_photo),
    const Divider(),
    const Text('4'),
    Text(isPicked ? 'You have picked image' : 'Please pick image'),
    const Divider(),
    const Text('5'),
    isLoading ? CircularProgressIndicator() : const SizedBox(),
  ],
),
```

{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
