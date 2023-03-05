## 🛠️ Git and Github

### 🧑‍🎓 HTML tags

1.  unordered list `<ul> </ul>`
2.  Ordered list `<ol> </ol>`
3.  List tag `<li> </li>`    

### 🧭 HTML attributes

1.  key-value pair
2.  extra info about the elements to the browser


### 🖥️ Ammet tag

1.  Shortcut to create nested tags

```
ol>li*5
 
<ol>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ol>
```

### 🛹 Types of Tags

1.  code and pre(pre-formatted texts) tag
2.  anchor tag
3.  input tag
    1.  different types text, password, email, file choose etc
    2.  label can be used to label text with input tag
4.  label tag
5.  select tag
6.  textarea tag
7.  form tag

### 🎿 Types of HTTP Requests

1.  GET → Fetch data from server
2.  POST → Server side changes (DB)
3.  PUT
4.  PATCH
5.  DELETE
6.  HEAD

### A URL contains
[https://abc.com/user?username=shivam&password=12345](https://abc.com/user?username=shivam&password=12345)

`https://` is a protocol

`abc.com/uses` is a resource

`username=shivam&password=12345` are query string parameter

### ⚽ Form tags

```html
    <form action="http://www.youtube.com/results" method="get" target="_blank">
        <label for="youtube">Search Youtube</label>
        <input type="text" name="search_query" id="youtube">
        <button>Submit</button>
    </form>
```

> **id** is used to _uniquely_ identify an HTML element. Ideally, an id should only identify one (and only one) HTML element across your entire document.
> 
> **class** is (mostly) used to specify what CSS class(es) an element should have.
> 
> **name** is (mostly) used to identify elements in a form.