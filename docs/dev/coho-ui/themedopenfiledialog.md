---
appliesTo: V2.0
---

# ThemedOpenFileDialog dialog

The `ThemedOpenFileDialog` is a dialog that replaces the default `OpenFileDialog` using the current theme.

![](../assets/opendialog.png)

## Properties
None.

## Methods


### Show(string title, Dictionary<string, string> fileTypes, Window owner)

Opens a dialog that lets the user browse the computer to open an existing file. Returns a `string?`.  
When the result is null, it means that the user has closed the dialog without selecting a file.

#### Arguments

* `string` title : The title of the dialog
* `Dictionary<string, string>` fileTypes : The supported extensions
* `Window` owner: The Window that will own the dialog

### Show(string title, ThemedSpecialDialogOptions options, Window owner, string? defaultButtonText = null, string? secondaryButtonText = null)

Opens a dialog that lets the user browse the computer to open an existing file. Returns a `string?`.  
When the result is null, it means that the user has closed the dialog without selecting a file.

#### Arguments

* `string` title : The title of the dialog
* [`ThemedSpecialDialogOptions`](../classes/ThemedSpecialDialogOptions.md) options : The options to configure the dialog
* `Window` owner: The Window that will own the dialog
* `string` defaultButtonText : The text to display in the default button
* `string` secondaryButtonText : The text to in the the secondary button

## Events

None.

## Examples

### Example 1

This example shows how to localize the `ThemedOpenFileDialog` texts.

``` csharp
public MainWindow()
{
  InitializeComponent();
  Loaded += OnLoaded;
}

private void OnLoaded(object sender, RoutedEventArgs e)
{
  // Set Coho.UI Texts resources from your own localization resources
  GenericText.Cancel = Localization.Resources.GenericCancel;
  DialogsText.Open = Localization.Resources.GenericOpen;
  DialogsText.FileName = Localization.Resources.GenericFileName;
  DialogsText.FileType = Localization.Resources.GenericFileType;

  ...
}
```


### Example 2

This example shows how to use the `ThemedOpenFileDialog` from C# and handle the result.

``` csharp
ThemedSpecialDialogOptions options = new ThemedSpecialDialogOptions()
{
    FileTypes =
    {
        {"All supported file types (*.md;*.pwdp)", "*.md;*.pwdp"},
        {"Markdown file (*.md)", "*.md"},
        {"PowerDocs Project file (*.pwdp)", "*.pwdp"}
    }
};

string? filePath = ThemedOpenFileDialog.Show(Localization.Resources.MenuOpen, options, this);

if (!string.IsNullOrEmpty(filePath))
{
    // open the selected file in your application
}
```