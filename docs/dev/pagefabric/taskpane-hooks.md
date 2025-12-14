# Task pane hooks

Hooks are new ways to integrate your task pane extensions in PageFabric.

By defining the `pf:ActivableHooks` meta tag on your main page, you can activate one or more hooks.

If you define several hook codes, you must separate them with a semicolon.

## Supported hook codes

This table shows all the supported hook codes and where they apply.

| Name    | Description                                                                                             |
|---------|---------------------------------------------------------------------------------------------------------|
| charts  | Allows your extension to be visible in the context menu when a chart is selected                        |
| images  | Allows your extension to be visible in the context menu when an image is selected                       |
| mosaics | Allows your extension to be visible in the context menu when a mosaic container is selected             |
| tables  | Allows your extension to be visible in the context menu when a table is selected                        |
| videos  | Allows your extension to be visible in the context menu when a local video is selected (html video tag) |

## Example

The head tag of the Pexels extension looks like that:

```html

<head>
    <meta name="pf:ActivableHooks" value="images;">
</head>
```