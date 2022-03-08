---
title: "Storing Data in the Browser With LocalStorage"
date: 2022-03-08T17:12:16Z
draft: false
---

LocalStorage is a way to save data in the browser through javascript for each domain/website.

* key-value pairs.
* The key values are always of type string, so if you want to save an object or an array one way is to use ``JSON.stringify()``.
* No expiration date, unless the client cleans the browser data. 
* Max size: 5MB per domain/website.
* If you use incognito mode the data will not persist, this is, data will be cleared when the browser is closed.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage" target="_blank">LocalStorage Docs</a>

### Useful code

| Method                               | Description             |
| -----------------------------------  | ----------------------- |
| ``localStorage.setItem(key, value)``     | Add key-value           |
| ``localStorage.getItem(key)``            | Get value by its key    |
| ``localStorage.removeItem(key)``         | Remove key-value        |
| ``localStorage.clear()``                 | Removes all data        |

| Other                                | Description               |
| -----------------------------------  | ------------------------- |
| ``localStorage``                         | Get all items/properties  |
| ``localStorage.length``                  | Get length of items       |

### Save data - setItem()

**1. Simple string:**

```
// localStorage.setItem(key, value);
localStorage.setItem("fname", "Miles");
```
or
```
// localStorage[key] = value;
localStorage["fname"] = "Miles";
```

**Result:**

DevTools --> Console
<img src="/images/localStorage/1.png#center" width="600px" alt="DevTools console">

DevTools --> Application --> Storage --> Local Storage --> Domain
<img src="/images/localStorage/2.png#center" width="600px" alt="DevTools application">

**2. Object, array or array of objects:**

```
let data = {
  fname: "Miles",
  lname: "MM" 
}
// localStorage.setItem(key, value);
localStorage.setItem("myInfo", JSON.stringify(data));
```
or
``` 
let data = {
  fname: "Miles",
  lname: "MM" 
}
// localStorage[key] = value;
localStorage["myInfo"] = JSON.stringify(data);
```

**Result:**

DevTools --> Console
<img src="/images/localStorage/3.png#center" width="600px" alt="DevTools console">

DevTools --> Application --> Storage --> Local Storage --> Domain
<img src="/images/localStorage/4.png#center" width="600px" alt="DevTools application">

### Get data - getItem()

**1. Simple string:**

```
// localStorage.getItem(key);
localStorage.getItem("fname");
```
or
```
// localStorage[key]
localStorage["fname"];
```
or
```
// localStorage.key
localStorage.fname;
```

**Result:**

DevTools --> Console
<img src="/images/localStorage/5.png#center" width="600px" alt="DevTools console">

**2. Object, array or array of objects:**

```
// localStorage.getItem(key);
JSON.parse(localStorage.getItem("myInfo"));
```
or
```
// localStorage[key]
JSON.parse(localStorage["myInfo"]);
```
or
```
// localStorage.key
JSON.parse(localStorage.myInfo);
```

**Result:**

DevTools --> Console
<img src="/images/localStorage/6.png#center" width="600px" alt="DevTools console">

### Remove Item - removeItem()

```
// localStorage.removeItem(key);
localStorage.removeItem("fname");
```
or
```
// localStorage[key]
delete localStorage["fname"];
```
or
```
// localStorage.key
delete localStorage.fname;
```

### Clear all data - clear()

```
localStorage.clear();
```
or

DevTools --> Application --> Storage --> Local Storage --> Domain
<img src="/images/localStorage/7.png#center" width="600px" alt="DevTools application">

### Get all items - localStorage

```
localStorage
```

**Result:**

DevTools --> Console
<img src="/images/localStorage/3.png#center" width="600px" alt="DevTools console">

### Get length of items - length

```
localStorage.length
```

**Result:**

DevTools --> Console
<img src="/images/localStorage/8.png#center" width="600px" alt="DevTools console">

{{<endMessage>}}Have fun 😄{{</endMessage>}}