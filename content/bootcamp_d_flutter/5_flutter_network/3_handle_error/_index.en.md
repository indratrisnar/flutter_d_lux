---
title: "3. Handle Error"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "api", "error"]
---

To handle errors on the Flutter network that are related to Future, you can use 2 ways. The synchronous method is (**.then**, **catchError**/**onError**) and the asynchronous method is (**try**, **catch**). For its application, you can use the source of the previous material. For the synchronous method, sometimes it's safe, sometimes it still freezes in running applications.

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Once resumed, the app runs again and the error message moves to the console.

{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

In an asynchronous manner, all code that has the potential for errors is included in the try block, then alternatives or possible solutions are entered into the catch block. The code below only displays errors to the console when an error occurs.

{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

By using the try-catch block, an int type error occurs beforehand, the app does not freeze or is safe. Error messages are displayed directly to the console.

{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Handle response status code:

The request process that reaches the server can be a successful request, but not necessarily the process or the result of the response. For example, when we want to update data, and the postId that we send as a condition for the index data post that we want to update is not found in the database, so the response for the update fails. To check the response results, you can use the status code as below.

{{< image src="5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="6.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="7.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

If the url is wrong, for example typo:

{{< image src="8.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="9.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="10.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
