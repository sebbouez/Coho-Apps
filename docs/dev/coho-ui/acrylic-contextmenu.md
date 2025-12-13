# AcrylicContextMenu

The `AcrylicContextMenu` uses the Acrylic texture on Windows 11. It will automatically fallback to a legacy style when it is not available.

### Properties
None.

### Methods
None.

### Events
None.

## Example

```xml
<Border Width="150" Height="150" Background="Silver">
	<Border.ContextMenu>
		<menus:AcrylicContextMenu>
			<MenuItem Header="Test 1"/>
			<MenuItem Header="Test 2"/>
			<MenuItem Header="Test 3"/>
		</menus:AcrylicContextMenu>
	</Border.ContextMenu>
</Border>
```

<img width="263" alt="image" src="https://user-images.githubusercontent.com/39953434/235143652-8c242a35-7410-4fcb-8266-07a79586992e.png">
