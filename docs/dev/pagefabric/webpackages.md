# Web packages

Web packages are the official way to add features to existing PageFabric websites. PageFabric users should not have to type code to add features to their websites. Web packages must handle all the technical and styling operations.



Web packages can contain Javascript and Stylesheet resources. They are packaged in a ZIP file that also contains a manifest file.

Explore the online Web Packages directory

## Resources
### Writing the manifest
Learn how to easily create your manifest file.

Read article
### Cookies policy
Make sure your Web Packages respect privacy and visitors Cookie consent choices.

Read article
### Create a controls library
Follow this article to see how to transform an existing library to a Web Package with small modifications.

Read article
Best practices
Whatever does your web package, PageFabric users must not have to type code to activate it or make it work.

It means that you have to trigger the page loaded event and activate your scripts on your own.



PageFabric includes JQuery by default. You can rely on the Document Ready event to start your functions.

``` js
$(document).ready(function(){

// auto activate your scripts using the JQuery document ready event.myFunction();

});
If your web package requires settings to apply transformations (or whatever you want to do with parts on the page), ask the user to specify custom attributes on his page.

$(document).ready(function() {
$("video").each(function() {
let $this = $(this);
let someVariableUsefulForYourScript = $this.attr("data-myattribute");
});
});
```

> Note: By default, Web Packages are loaded asynchronously when the website is published. You must ensure that your scripts work correctly when they are added using the "async" attribute. Be aware that the user has the possibility to turn off async loading.

Limitations
We allow you to deploy only the following files in your Web Packages:

.css
.js
.png
.jpg
.jpeg
.jiff
.gif
.svg
.woff
.eot
.ttf
.woff2