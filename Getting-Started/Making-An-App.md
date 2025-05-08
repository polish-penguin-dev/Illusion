# Making Your App

> [!WARNING]  
> Kindles Support ES5 And Semi-Modern HTML5, CSS3.

To Begin, All You Need To Do Is Make A New Folder With A HTML, CSS, And JS File. For Example,

`hello/index.html`:
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Hello Illusion!</title>
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
    <link rel="stylesheet" type="text/css" media="screen" href="style.css">
    <script src="script.js"></script>
</head>
<body>
    <div class="container">
        <h1>Illusion</h1>
        <p id="status">JavaScript Doesn't Work</p>
    </div>
</body>
</html>
```

`hello/style.css`:
```css
.container {
    text-align: center;
};

h1, p {
    font-family: Arial, Helvetica, sans-serif; 
};
```

`hello/script.js`:
```js
document.addEventListener("DOMContentLoaded", function() {
    document.getElementById("status").innerHTML = "JavaScript Works!";
});
```

This Is Your Basic App. You Can Add More Logic Later.

[Next Page](/Getting-Started/Utilities-Helpers.md)