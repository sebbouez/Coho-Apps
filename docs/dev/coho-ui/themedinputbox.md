---
appliesTo: V2.0
---

# ThemedInputBox dialog

The `ThemedInputBox` is a dialog that provides a message and a `TextBox` so that the user can enter text.

![](../assets/inputbox.png)

## Properties
None.

## Methods


### Show(string message, string title, string defaultValue = "")

Shows a modal dialog using the current theme. Returns a `string?`.  
If the returned value is `null`, it means that the user selected the **Cancel** button or closed the dialog.

#### Arguments
* `string` message : The message to display.
* `string` title : The title of the dialog.
* `string` defaultValue : The text to write in the `TextBox` by default when the dialog opens.


### Show(string message, string title, string defaultValue, string defaultButtonText, string secondaryButtonText)

Shows a modal dialog using the current theme. Returns a `string?`.  
If the returned value is `null`, it means that the user selected the **Cancel** button or closed the dialog.

#### Arguments
* `string` message : The message to display.
* `string` title : The title of the dialog.
* `string` defaultValue : The text to write in the `TextBox` by default when the dialog opens.
* `string` defaultButtonText : The text to display in the default button.
* `string` secondaryButtonText : The text to in the the secondary button.


### Show(string message, string title, Window owner, string defaultValue = "", string? defaultButtonText = null, string? secondaryButtonText = null

Shows a modal dialog using the current theme. Returns a `MessageBoxResult` that represents the choice of the user.  
This method can be used to override the default texts and provide a better UX while still using the default framework components.  
This method should be used with the `MessageBoxButton.YesNoCancel` or `MessageBoxButton.YesNo` arguments. The **Yes** button will be replaced with the **defaultButtonText** value, and the **No** button will be replaced with the **secondaryButtonText**.

#### Arguments
* `string` message : The message to display.
* `string` title : The title of the dialog.
* `Window` owner : The window that owns the dialog; used for the modal behavior.
* `string` defaultValue : The text to write in the `TextBox` by default when the dialog opens.
* `string` defaultButtonText : The text to display in the default button.
* `string` secondaryButtonText : The text to in the the secondary button.


## Events
None.

## Examples

### Example 1

This example shows how to use the `ThemedInputBox` from C# and handle the result.

``` csharp
string? value = ThemedInputBox.Show("Please provide name for this folder:", "Rename folder", this);

if (!string.IsNullOrEmpty(value))
{
    // some code to rename a folder
}
```