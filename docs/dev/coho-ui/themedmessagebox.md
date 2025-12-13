# ThemedMessageBox

The `ThemedMessageBox` is a dialog that replaces the default `MessageBox` using the current theme.


## Show(string message, string title, MessageBoxButton button)
Shows a modal dialog using the current theme. Returns a `MessageBoxResult` that represents the choice of the user.

### Arguments
* `string` message : The message to display
* `string` title : The title of the dialog
* `MessageBoxButton` button : The buttons to display

### Example

```cs
MessageBoxResult quest = ThemedMessageBox.Show("Do you want to save changes?", "Save changes", MessageBoxButton.YesNoCancel);

switch (quest)
{
    case MessageBoxResult.Yes:
        // Yes button was clicked
    break;
    case MessageBoxResult.No:
        // No button was clicked
    break;
    case MessageBoxResult.Cancel:
        // Cancel button was clicked
    break;
}
```


## Show(string message, string title, MessageBoxButton button, string defaultButtonText, string secondaryButtonText)
Shows a modal dialog using the current theme. Returns a `MessageBoxResult` that represents the choice of the user.  
This method can be used to override the default texts and provide a better UX while still using the default framework components.  
This method should be used with the `MessageBoxButton.YesNoCancel` or `MessageBoxButton.YesNo` arguments. The **Yes** button will be replaced with the **defaultButtonText** value, and the **No** button will be replaced with the **secondaryButtonText**.

### Arguments
* `string` message : The message to display
* `string` title : The title of the dialog
* `MessageBoxButton` : The buttons to display
* `string` defaultButtonText : The text to display in the default button (the **Yes** button when using `MessageBoxButton.YesNoCancel` or `MessageBoxButton.YesNo`)
* `string` secondaryButtonText : The text to in the the secondary button (the **No** button when using `MessageBoxButton.YesNoCancel` or `MessageBoxButton.YesNo`)


## MessageBoxResult Show(string message, string title, Window owner, MessageBoxButton button, string? defaultButtonText = null, string? secondaryButtonText = null)

Shows a modal dialog using the current theme. Returns a `MessageBoxResult` that represents the choice of the user.  
This method can be used to override the default texts and provide a better UX while still using the default framework components.  
This method should be used with the `MessageBoxButton.YesNoCancel` or `MessageBoxButton.YesNo` arguments. The **Yes** button will be replaced with the **defaultButtonText** value, and the **No** button will be replaced with the **secondaryButtonText**.

### Arguments
* `string` message : The message to display
* `Window` owner: The Window that will own the dialog
* `string` title : The title of the dialog
* `MessageBoxButton` : The buttons to display
* `string` defaultButtonText : The text to display in the default button (the **Yes** button when using `MessageBoxButton.YesNoCancel` or `MessageBoxButton.YesNo`)
* `string` secondaryButtonText : The text to in the the secondary button (the **No** button when using `MessageBoxButton.YesNoCancel` or `MessageBoxButton.YesNo`)