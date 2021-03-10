# You Chose JavaScript (or `js`)

## Intructions

Step 1: Include the TinyMCE script<br />
Include this line of code in the `<head>` of the HTML page and link to the `tinymce.min.js` source file.<br />

```html
<script src="https://cdn.tiny.cloud/1/afjr4b0jfzxrhryu2m26z97gl2h6acfw2739s51zhfed6nsk/tinymce/5/tinymce.min.js" referrerpolicy="origin"></script>
```

Step 2: Initialize TinyMCE as part of a web form<br />
With the script included, initialize TinyMCE 5.0 on any element (or elements) in the web page.<br />

Since TinyMCE enables identifying replaceable elements via a CSS selector, the only requirement is to pass an object that contains a selector to `tinymce.init()`.<br />

In this example, replace `<textarea id="mytextarea">` with a TinyMCE 5.0 editor instance by passing the selector `#mytextarea` to `tinymce.init()`.<br />

```html
<!DOCTYPE html>
<html>
<head>
  <script src='https://cdn.tiny.cloud/1/afjr4b0jfzxrhryu2m26z97gl2h6acfw2739s51zhfed6nsk/tinymce/5/tinymce.min.js' referrerpolicy="origin">
  </script>
  <script>
    tinymce.init({
      selector: '#mytextarea'
    });
  </script>
</head>

<body>
  <h1>TinyMCE Quick Start Guide</h1>
  <form method="post">
    <textarea id="mytextarea" name="mytextarea">
      Hello, World!
    </textarea>
  </form>
</body>
</html>
```
