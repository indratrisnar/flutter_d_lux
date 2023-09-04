---
title: "2. CRUD Public API"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "api", "crud"]
---

For implementation, we will use the http package. Actually there are other packages, but here we will follow the official Flutter package, namely http. [http | Dart Package (pub.dev)](https://pub.dev/packages/http).

Source public API to use: \
[JSONPlaceholder - Free Fake REST API (typicode.com)](https://jsonplaceholder.typicode.com/)

Guide on how to access the jsonplaceholder API:\
[JSONPlaceholder - Guide (typicode.com)](https://jsonplaceholder.typicode.com/guide/)

Before starting, first add the http package in dependencies and the DMethod package for tracking and check response purposes. And the DInput package for concise input.

{{< image src="0.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

- [GET](#1-get)
- [POST](#2-post)
- [PUT](#3-put)
- [PATCH](#4-patch)
- [DELETE](#5-delete)

<br>

#### 1. GET

Requests made in the getPosts function are then called/executed in the initState section. The endpoint/url is parsed into the Uri form and then entered into the http param input with the get method. Because http.get is of type Future, one way to access the returned data is to use .then. Check the response data using the DMethod package and it will appear in the console section.

Extract the response body data from the initial json, which is the form of data that is encrypted in the form of a string. The main root form of the body is a List, so after extracting it it is directly inserted into the List variable. Then auto casting uses List.from and puts it in the global scope class variable named posts. These posts are used in the body screen/scaffold view. So that the UI is updated after getting the data from the response, call setState.

```dart
List<Map> posts = [];

getPosts() {
    String url = 'https://jsonplaceholder.typicode.com/posts';
    http.get(Uri.parse(url)).then((response) {
        DMethod.printResponse(response);

        List list = jsonDecode(response.body);
        posts = List.from(list);
        setState(() {});
    });
}

@override
void initState() {
    getPosts();
    super.initState();
}
```

{{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
ListView.builder(
    itemCount: posts.length,
    itemBuilder: (context, index) {
        Map item = posts[index];
        return ListTile(
            leading: CircleAvatar(
                child: Text('${index + 1}'),
            ),
            title: Text(
                item['title'],
                maxLines: 1,
                overflow: TextOverflow.ellipsis,
            ),
            subtitle: Text(
                item['body'],
                maxLines: 1,
                overflow: TextOverflow.ellipsis,
            ),
        );
    },
),
```

{{< image src="1_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 2. POST

First create an input object first.

```dart
final edtTitle = TextEditingController();
final edtBody = TextEditingController();
```

Then attach it to the widget.

```dart
DInput(controller: edtTitle),
const SizedBox(height: 16),
DInput(controller: edtBody),
const SizedBox(height: 16),
ElevatedButton(
    onPressed: () {
        createPost(edtTitle.text, edtBody.text, 1);
    },
    child: const Text('Add Post'),
),
```

{{< image src="2_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

The request is made in the craetePost function and then called/executed in the section when the button is clicked. The method used is POST, because the aim is to input new data and send data via the request body. All data in the request body must be of type string. The title and body are taken from the edited input, while the userId is just straight away because this is a test.

```dart
createPost(String title, String body, int userId) async {
    String url = 'https://jsonplaceholder.typicode.com/posts';
    try {
        final response = await http.post(
            Uri.parse(url),
            body: {
                'title': title,
                'body': body,
                'userId': userId, // userId.toString()
            },
        );
        DMethod.printResponse(response);
    } catch (e) {
        DMethod.printTitle('createPost-error', e.toString());
    }
}
```

{{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="2_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 3. PUT

The steps are the same as POST, but there are several differences as follows.\
\- We initialize the initial value of the input so that there is an old value.\
\- In the url section, there is additional data, namely postId as the index of which data you want to update.\
\- postId is also added to the request body, all fields must have data because it uses the PUT method which updates all fields. This means that if the old field value is the same as the new field value, it will be replaced with the same data (still updated).

```dart
final edtTitle = TextEditingController();
final edtBody = TextEditingController();
// init
edtTitle.text = 'foo';
edtBody.text = 'bar';
```

```dart
DInput(controller: edtTitle),
const SizedBox(height: 16),
DInput(controller: edtBody),
const SizedBox(height: 16),
ElevatedButton(
    onPressed: () {
        updatePost(1, edtTitle.text, edtBody.text, 1);
    },
    child: const Text('Update Post'),
),
```

```dart
updatePost(int postId, String newTitle, String newBody, int userId) {
    String url = 'https://jsonplaceholder.typicode.com/posts/$postId';
    http.put(
        Uri.parse(url),
        body: {
            'id': postId.toString(),
            'title': newTitle,
            'body': newBody,
            'userId': userId.toString(),
        },
    ).then((response) {
        DMethod.printResponse(response);
    });
}
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="3_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

{{< image src="3_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 4. PATCH

The steps are the same as PUT but there is a difference, in the request body section, only enter the field data you want to update (partially).

```dart
final edtTitle = TextEditingController();
// init
edtTitle.text = 'foo';
```

```dart
DInput(controller: edtTitle),
const SizedBox(height: 16),
ElevatedButton(
    onPressed: () {
        updatePost(context, 1, edtTitle.text);
    },
    child: const Text('Update Post'),
),
```

```dart
updatePost(BuildContext ctx, int postId, String newTitle) async {
    String url = 'https://jsonplaceholder.typicode.com/pot/$postId';
    http.patch(
        Uri.parse(url),
        body: {
            'title': newTitle,
        },
    ).then((response){
        DMethod.printResponse(response);
    });
}
```

{{< image src="4_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="4_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 5. DELETE

It can be the same as PUT or GET. But usually without a request body. For data conditions that you want to delete, sent via url. For a normal delete response without data. Only use check status code as sign of success/fail delete.

```dart
int postId = 1;
String url = 'https://jsonplaceholder.typicode.com/posts/$postId';
http.delete(Uri.parse(url)).then((response) {
    DMethod.printResponse(response);
});
```

{{< image src="5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
