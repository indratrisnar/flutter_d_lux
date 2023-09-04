---
title: "1. API"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "api"]
---

API or abbreviation for Application Programming Interface. How do we interact between different platforms, for example Android with the web, Android with desktop or vice versa. API is a bridge between the two and between other platforms. API is also known as a web service that serves a request to a server, therefore API is on the web but can be on the same server or on a different server.

The data sent or received from the API has a certain type, currently the data exchanged via the API used is in JSON or XML format. The data format that is often used is JSON or Javascript Object Notation.

To access the API, several things need to be set and prepared, including:

1. Endpoint/URL

This endpoint/url is the location where the API is located. Example:\
[https://jsonplaceholder.typicode.com/posts](https://jsonplaceholder.typicode.com/posts)

2. Method

The methods required or allowed to access the API are based on the URL provided. Commonly used methods include.

- **GET** to request data
- **POST** to input/create data
- **PUT** to update the entire data
- **PATCH** for partial data updates
- **DELETE** to delete data

On the other hand, the POST method can also be used to access the update, delete, and other APIs. Most importantly, just follow the API access rules created by the backend developer.

3. Authentication

This Auth is optional, if the API is public then it's okay without using Authentication. Authentication created or stored in the request header. But back to the API rules that were made, whether Auth is required or not.

4. Request Header

The schema for how to access the API, for example, explains that the URL you want to access requires data in the request body of this type, or that it must also have auth.

5. Request Body

If you want to send data to the API for input, update delete data, it can be sent through the body of the API request. The data sent in the body of the request is hidden and does not appear in the URL.

6. Parameter

Its use is the same as the data in the request body but it is public, the parameters will appear in the URL you want to access because their placement must be in the URL/endpoint. Usually used when requesting data using the GET method but with some filter or other, where the data that becomes the filter is sent from the client making the request.

<br>

The naming of the types of API that developers are currently discussing is divided into 2, Rest API and RestFull API. Rest API or API is usually referred to as an API whose endpoint is only used for the needs of 1 action/API. Meanwhile, for the RestFull API, the same 1 endpoint can be used for several APIs, with what method is used as a differentiator between APIs.

Example of a typical Rest API:

https://domain-name/api/note/create.php

This endpoint is only used for 1 API, namely creating a new data note using the POST method.

RestFull API example:

https://domain-name/api/note/

the endpoint can be used for multiple APIs.

- GET: fetch list note data
- POST: added a new data note
- PUT: update certain note data
- DELETE: delete certain note data

After the client request reaches the server, the client will get a response. The response varies, can be successful, failed and others. The most common and recommended way to check whether a client request is successful, failed, etc., is using the response status code. One of the references can be checked here: [List of HTTP status codes - Wikipedia](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

The data returned from the API is in the response body, in JSON format. If the API request fails, the response body can be in another format, for example html.

The following is an overview of how clients interact with servers using API/Web Services.

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

API implementation does not always access endpoints/urls, but some have created a certain schema. For example the Firebase API, from the Flutter side, all you have to do is use the classes and methods provided. But the rules are still there, you need to follow the rules from Firebase.

<br>
