# Task pane extensions
PageFabric tasks pane extensions are new ways to extend the application by adding custom panes that add features for end users. Task panes are web pages included in PageFabric in a separate chromium process. Task panes must use the PageFabric JS API to interact with documents and UI.

> Note: Task panes websites must be hosted online and accessible with https protocol. Online hosting may incur service charges.

## Architecture overview

## Building your first task pane extension

Here are the prerequisites to start in good conditions:

* You know Javascript and how the Web works
* You are used to create and debug Web applications using Chromium dev tools
* You own a dedicated space on the Web to host your creations
* You have activated HTTPS on your website


Open your favorite code editor to create a new web project. It will contain the HTML, JS and CSS files to run your extension correctly.
In this example, we will use Visual Studio Code.

1. Create a new HTML file
1. Create a default HTML structure
1. Add a script tag <script src="local://pfapi.js"></script> in the head section of your page


Your file should look like that at this point:

```html
<!DOCTYPE html>
<html lang="en-US">
<meta charset="utf-8">
<head>
<script src="local://pfapi.js"></script>
</head>
<body>

</body>

</html>
``` 

The local://pfapi.js tag will include all required methods when your page will be loaded in PageFabric.
In the body section, add a script tag to add some Javascript code.

```js
(async () => {
let appVersion = await PageFabric.Client.GetApplicationVersionAsync();
document.write("Hello from PageFabric V" + appVersion);
})();
``` 

> Note: The Javascript API works asynchronously. If you need to learn about sync/async programming in Javascript, have a look at https://javascript.info/async-await

Save your file.
It should look like that:

```html
<!DOCTYPE html>
<html lang="en-US">
<meta charset="utf-8">
<head>
<script src="local://pfapi.js"></script>
</head>
<body>

<script>

(async () => {
let appVersion = await PageFabric.Client.GetApplicationVersionAsync();
document.write("Hello from PageFabric V" + appVersion); 
 })();

</script>

</body>
</html>
```