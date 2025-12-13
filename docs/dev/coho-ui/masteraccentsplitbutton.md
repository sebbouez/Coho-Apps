# MasterAccentSplitButton

The `MasterAccentSplitButton` is a button that it usually used to start an activity in the application. For example, in Microsoft Office, you can find them in the Backstage view, to create new documents.
It's a split button that uses the `AccentColor` brush as background. The text uses a semibold weight. It supports an icon (brush resource).

![image](https://user-images.githubusercontent.com/39953434/234863128-847233f2-b663-4429-99b7-8799f6b0f87c.png)


### Properties
* `string` Text: The text to display in the button.
* `brush` Icon: The icon to display in the button.
* `object` DropDownContent: The content of the dropdown menu.

### Methods
None.

### Events
* `RoutedEventHandler` Click: Occurs when the user clicks the left part of the button.

```xml
<buttons:MasterAccentSplitButton Text="Create new" Icon="{DynamicResource IconMagic}" Click="MasterAccentSplitButton_Click">
   <buttons:MasterAccentSplitButton.DropDownContent>
      <StackPanel>
         <MenuItem Header="ddd" />
         <MenuItem Header="ddd" />
      </StackPanel>
   </buttons:MasterAccentSplitButton.DropDownContent>
</buttons:MasterAccentSplitButton>
```