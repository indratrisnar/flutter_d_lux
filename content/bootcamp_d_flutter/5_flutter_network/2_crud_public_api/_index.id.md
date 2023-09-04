---
title: "2. CRUD Public API"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "api", "crud"]
---

Untuk implementasinya, akan menggunakan package http. Sebetulnya ada package lain, namun disini akan mengikuti dari package official flutter yaitu http. [http | Dart Package (pub.dev)](https://pub.dev/packages/http).

Sumber public API yang akan digunakan: \
[JSONPlaceholder - Free Fake REST API (typicode.com)](https://jsonplaceholder.typicode.com/)

Panduan cara akses API jsonplaceholder tersebut:\
[JSONPlaceholder - Guide (typicode.com)](https://jsonplaceholder.typicode.com/guide/)

Sebelum mulai, tambahkan dulu package http di dependencies dan package DMethod untuk keperluan tracking dan check response. Dan package DInput untuk concise input.

{{< image src="0.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

- [GET](#1-get)
- [POST](#2-post)
- [PUT](#3-put)
- [PATCH](#4-patch)
- [DELETE](#5-delete)

<br>

#### 1. GET

Untuk request dibuat didalam fungsi getPosts kemudian dipanggil/dieksekusi dibagian initState. Endpoint/url di parsing ke bentu Uri kemudian dimasukkan ke input param http dengan method get. Karena http.get bertipe Future, maka salah satu cara untuk akses data yang direturn bisa menggunakan .then. Cek response data menggunakan package DMethod dan akan Nampak pada bagian console.

Extrak data response body dari awalnya json yaitu bentuk data yang enkripsi kebentuk string. Bentuk root utama body nya adalah List, sehingga setelah di ekstrak langsung dimasukkan ke variable List. Kemudian auto casting menggunakan List.from dan dimasukkan ke variable global scope class yang Bernama posts. posts ini digunakan di view body screen/scaffold. Biar UI nya diupdate setelah selesai ambil data dari response, panggil setState.

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

Pertama buat objek input terlebih dahulu.

```dart
final edtTitle = TextEditingController();
final edtBody = TextEditingController();
```

Kemudian pasangkan di widget.

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

Untuk request dibuat didalam fungsi craetePost kemudian dipanggil/dieksekusi dibagian Ketika button di klik. Method yang digunakan adalah POST, karena tujuannya untuk input data baru dan kirim data lewat request body. Semua data di request body harus bertipe string semua. Title dan body diambil dari input yang diedit, sedangkan userId langsung aja karena ini test.

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

Step nya sama seperti POST, namun ada beberapa perbedaan sebagai berikut.\
\- Kita lakukan inisialisasi nilai awal input bahwa terdapat old value.\
\- Pada bagian url, ada tambahan data yaitu postId sebagai index data mana yang mau diupdate.\
\- postId ditambahkan juga ke request body, semua field mesti ada datanya karena menggunakan method PUT yang mengupdate seluruh field. Artinya jika value old field sama dengan value new field maka akan di replace dengan data yang sama (tetap diupdate).

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

Step nya sama seperti PUT namun ada perbedaan, pada bagian request body, hanya memasukkan data field yang ingin diupdate saja (sebagian).

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

Bisa sama seperti PUT atau GET. Namun biasanya tanpa ada request body. Untuk kondisi data yang ingin dihapus, dikirim melalui url. Untuk response delete biasa tanpa data. Only use check status code sebagai tanda berhasil/gagal delete.

```dart
int postId = 1;
String url = 'https://jsonplaceholder.typicode.com/posts/$postId';
http.delete(Uri.parse(url)).then((response) {
    DMethod.printResponse(response);
});
```

{{< image src="5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
