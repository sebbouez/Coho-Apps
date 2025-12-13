# ThemedSpecialDialogOptions class

This class is used to configure the behavior of the [`ThemedOpenFileDialog`](themedopenfiledialog.md) dialog.

## Properties


### DefaultHeight

Type: `int`  
Default value: `650`  
The **DefaultHeight** property defines the initial height of the dialog in pixels.


### DefaultWidth

Type: `int`  
Default value: `920`  
The **DefaultWidth** property defines the initial width of the dialog in pixels.


### FileTypes

Type: `Dictionary<string, string>`  
Default value: `default`  
The **FileTypes** property defines the extensions that are supported by the dialog.

### InitialDirectory

Type: `string`  
Default value: `String.Empty`  
The **InitialDirectory** property defines the first folder to show when the dialog is opened.


### ShowDefaultSpecialFolders

Type: `bool`  
Default value: `true`  
The **ShowDefaultSpecialFolders** property defines if the special folders (Documents, Images, Videos...) section will be displayed. This property has no effect if the `ShowNavigationPane` property is set to `false`.


### ShowNavigationPane

Type: `bool`  
Default value: `true`  
The **ShowNavigationPane** property defines if the navigation pane (on the left side) will be displayed.


## Methods

None.


## Events

None.