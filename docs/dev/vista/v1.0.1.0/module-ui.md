# Ui module

The `ui` module provides a set of methods to show dialogs and messages.

Import the module with:

```js
import { ui } from 'lib';
```

## SetStatusText(string message)
This method sets the status text of the application.

### Arguments
* `string` message : The message to display

### Example

```js
import { designer, ui } from 'lib';
let sel = designer.GetSelection();
ui.SetStatusText('selected ' + sel.Count + ' items');
```
