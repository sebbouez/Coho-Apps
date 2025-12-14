# Create controls library as Web Package
A great way to improve websites appearance is to replace the native controls (checkbox, radio buttons, select, video player...). To do so, Javascript and CSS help a lot. There are already a lot of great solutions on the market to replace browsers native controls. In this article, we will explain how to turn an existing library into a Web Package for PageFabric.

## Best practices
Because Web Packages files are deployed with the website itself, you should take care of the user's hosting limitations, such as files size and bandwidth consumption. Always minify your JavaScript and CSS files.

Your styles should adapt to any PageFabric website. To do so, we provide a set of CSS variables that set Font family, Font size, preferred corner radius, preferred colors... Check the list of CSS variables and use them in your style sheets to make your controls look great on any website.

Remember that PageFabric allows users to create multilingual websites. If your controls include text resources (labels, tooltips...), you should localize them. If you need to get the current language the the page, you can use the lang attribute on the html tag (PageFabric adds it by default), or use the PageFabric client API using the PageFabric.pageLanguage property.

> DO NOT include JQuery Framework in your Web Packages, it's already included in any PageFabric website.

## Example: Plyr (video control replacement)
Plyr is a great JavaScript library that can replace the default HTML5 video tag to a better looking video player.

It is composed of a JS file and a CSS file for styling the new player. Remember that a best practice is of course that your library controls adapt to the website theme. Your CSS files must use the CSS variables that we provide (read the list of CSS variables).

The default JS file of Plyr only contains the code that replaces the video tag and features implementations. It does not activate itself automatically. It means that someone has to activate the plugin by adding JavaScript code to his website.

It's not how Web Packages should work in PageFabric. Our philosophy is Plug-And-Play, No-Code.

## CSS Files modifications
Libraries should not use hard coded values such as colors, font family or corner radius.

Use the predefined CSS variables instead.



Here is how we changed the default CSS sheet:

```css
:root {
--plyr-color-main: var(--themePrimary);
--plyr-badge-background: var(--themeDark);
--plyr-audio-control-color: var(--black);
--plyr-badge-border-radius: var(--corner-radius);
--plyr-control-radius: var(--corner-radius);
--plyr-tooltip-radius: var(--corner-radius);
--plyr-menu-radius: var(--corner-radius);
}
```

## JavaScript files modifications
We have just added one line at the end of the original library JS file to ensure the library will instanciate itself when the page is loaded.

``` js
// original library JS code here
...
// Added code to instanciate the library
const players = Plyr.setup('video');
```

Remember that PageFabric users have the option to load Web Packages asynchronously (it adds the defer attribute to the script tags), so your scripts have to support both sync and async loading modes.

> Note: All PageFabric websites embed JQuery Framework. You can use the $(document).ready({ }) method to instantiate your libraries.

### What if my scripts need parameters?
As we said, the philosophy is not to ask users to type code to make your libraries work.

Instead of asking them to type Json or Javascript scripts, you can use the HTML custom attributes.


You can tell create a naming convention for custom attributes and give instructions to PageFabric users to add custom attributes on their Parts.

In this example, we can add plyr-fullscreen on the video tag on the page.

Then, in your initialization script, you can rely on these attributes to create your components.

```js
// very basic example
$("video").each(function() {

let supportsFullScreen = $(this).attr("plyr-fullscreen");
// now init the plyr with this value
});
```

## Package manifest file
The Plyr library contains only one Javascript file and a CSS file.

The XML manifest must declare those two files to be included and imported on pages using the BuildActions section.

```xml
<BuildActions>
<!-- Include files in the publication process -->
<IncludeResource>plyr.js</IncludeResource>
<IncludeResource>plyr.css</IncludeResource>

<!-- Import references to the files in the HEAD tag -->
<ImportResource>plyr.css</ImportResource>
<ImportResource>plyr.js</ImportResource>
</BuildActions>
```