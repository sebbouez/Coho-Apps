# Localize default strings

Coho.UI comes with default texts in English. You can however customize them to improve your UX.

## Table of default strings

| Class name             | Property name              | Default value                    | Description                                                                                                              |
|------------------------|----------------------------|----------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| `Coho.UI.GenericText`  | `Copy`                     | Copy                             | The text used to perform the "copy to clipboard" action                                                                  |
| `Coho.UI.GenericText`  | `Cut`                      | Cut                              | The text used to perform the "cut to clipboard" action                                                                   |
| `Coho.UI.GenericText`  | `Paste`                    | Paste                            | The text used to perform the "paste from clipboard" action                                                               |
| `Coho.UI.GenericText`  | `SelectAll`                | Select all                       | The text used to perform the "select all content" action                                                                 |
| `Coho.UI.GenericText`  | `Ok`                       | OK                               | The text used that is displayed in the Ok buttons in dialogs                                                             |
| `Coho.UI.GenericText`  | `Yes`                      | Yes                              | The text used that is displayed in the Yes buttons in dialogs                                                            |
| `Coho.UI.GenericText`  | `No`                       | No                               | The text used that is displayed in the No buttons in dialogs                                                             |
| `Coho.UI.GenericText`  | `Add`                      | Add                              | The text used that is displayed in the Add buttons in dialogs                                                            |
| `Coho.UI.GenericText`  | `Remove`                   | Remove                           | The text used that is displayed in the Remove buttons in dialogs                                                         |
| `Coho.UI.GenericText`  | `HelpGenericHint`          | Press F1 to get help.            | The text used in the Omnibar results and in the ribbon/QAT buttons tooltips                                              |
| `Coho.UI.GenericText`  | `MoreOptions`              | More options                     | The text used in various contexts when other options are available to the user                                           |
| `Coho.UI.GenericText`  | `ErrorOccured`             | An error occured                 | The text used in the  the [ThemedMultiTaskDialog](ThemedMultiTaskDialog.md) to tell the user that an error occured       |
| `Coho.UI.GenericText`  | `WorkInProgress`           | Work in progress, please wait... | The text used in the  the [ThemedMultiTaskDialog](ThemedMultiTaskDialog.md) to tell the user that the process is running |
| `Coho.UI.OmnibarTexts` | `NoResult`                 | No result found.                 | The text used when the omnibar search did not return any result                                                          |
| `Coho.UI.OmnibarTexts` | `PlaceholderText`          | Search or type a command         | The text used as a placeholder when the focus is not set to the omnibar                                                  |
| `Coho.UI.OmnibarTexts` | `ResultsCommandsGroupName` | Commands                         | The text used to group results in the omnibar results popup                                                              |
| `Coho.UI.OmnibarTexts` | `ResultsOtherServices`     | Other searches...                | The text used to group results in the omnibar results popup                                                              |
| `Coho.UI.OmnibarTexts` | `ResultsInFiles`           | Results found in files           | The text used to group results in the omnibar results popup                                                              |
| `Coho.UI.OmnibarTexts` | `SearchInFiles`            | Search in files...               | The text used to start the "Find in files" command                                                                       |
| `Coho.UI.DialogsText`  | `Open`                     | Open                             | The text of the default button of the [ThemedOpenFileDialog](themedopenfiledialog.md)                                    |
| `Coho.UI.DialogsText`  | `FileName`                 | File name                        | The text next to the file name textbox in the [ThemedOpenFileDialog](themedopenfiledialog.md)                            |
| `Coho.UI.DialogsText`  | `FolderParentLevel`        | Parent                           | The text of the browse top folder button in the [ThemedOpenFileDialog](themedopenfiledialog.md)                          |

## Customize strings

You can easily change the default values using your own strings.

This example shows how to change text using a static value:

``` csharp
private void OnLoaded(object sender, RoutedEventArgs e)
{
    Coho.UI.GenericText.Yes = "YES!";
}
```

This example shows how to change text using your own localized strings:

``` csharp
private void OnLoaded(object sender, RoutedEventArgs e)
{
    // Localization.Resources is the class name of your RESX generated class
    Coho.UI.GenericText.Yes = Localization.Resources.GenericYes;
}
```