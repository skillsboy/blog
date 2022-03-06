---
title: "Run Javascript Through Bookmark (Bookmarklet)"
date: 2022-03-06T12:19:47Z
draft: false
---

Bookmarklet is a browser bookmark that runs javascript on the current page. This is, whenever you press the bookmark it will execute javascript.

If you have to execute javascript everyday on a especific page this will be useful.

### Add page to bookmark bar

Add bookmark or drag the url to the bookmark bar.

![Add bookmark](/images/bookmarklet/1.png#center)

### Edit bookmark

1. Right click bookmark (1).
2. Edit (2).

![Edit bookmark](/images/bookmarklet/2.png#center)

### Create/edit bookmarklet

1. ``Name``: You can change the bookmark ``Name`` this appears on the bookmark bar.
2. ``URL``: This will be divided by two, the protocol and the code. The protocol will always be ``javascript:`` and be sure to put it otherwise it won't work. And the code is where you will add your javascript code.

In this example I will change the page title and use the javascript alert popup to display it.

![Create/edit bookmarklet](/images/bookmarklet/3.png#center)

### Result

Now on any page you click the bookmarklet it will execute the code that changes the title and create an alert.

![Result](/images/bookmarklet/4.png#center)

{{<endMessage>}}Have fun 😄{{</endMessage>}}