# Selection Class

The `selection` class represents the selected items in the document.

## Properties

### Count
This property returns the number of selected items in the document.

#### Example

```js
import { document, ui } from 'lib';
let sel = document.GetSelection();
ui.SetStatusText('selected ' + sel.Count + ' items');
```

## Methods  

### SetFillColor(color) 
This property returns the number of selected items in the designer.

> **Note:** Unless you are using a Batch script, this method will trigger a redraw.

#### Arguments
* color : `string` - The color to set the fill color to.

#### Example

```js
import { document } from 'lib';
let sel = document.GetSelection();
sel.SetFillColor('#d40000');
```
