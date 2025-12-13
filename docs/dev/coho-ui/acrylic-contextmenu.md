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