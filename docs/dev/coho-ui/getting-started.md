# Getting started with Coho.UI

## Define your theme

> Have a look at the sample application, the file `App.xaml` contains all the required resources to make it work nicely. Just change the brushes to make it yours.

You must define the Font Family and Font size to use.
* `FontFamily` **AppFont**: Defines the font to use in the UI.
* `system:Double` **AppFontSize**: Defines the font size to use in the UI.

**Example**:

```xml
<FontFamily x:Key="AppFont">Segoe UI Variable Display,Segoe UI</FontFamily>
<system:Double x:Key="AppFontSize">14</system:Double>
```


You must define your color theme using specified resource names.
* `Color` **ChromeBorderActiveColor**: Defines the color of the window border when it is active.
* `Brush` **AccentColor**: Defines the accent color to be used on various UI elements.
* `Brush` **AccentColorDark**: Defines the darker accent color to be used on various UI elements (used for hover state for example).
* `Brush` **AccentColorDarker**: Defines the even darker accent color to be used on various UI elements (used for pressed state for example).
* `Brush` **IconsAccentColor**: Defines the color to be used in Coho.UI bundled isons.
* `Brush` **AccentButtonBorderColor**: Defines the brush to be used for border on buttons that use the `PrimaryButton` style.

**Example**:  

```xml
<Color x:Key="ChromeBorderActiveColor">#038387</Color>
<LinearGradientBrush x:Key="AccentButtonBorderColor" StartPoint="0,0.9" EndPoint="0,1">
   <GradientStop Color="#038387" Offset="0" />
   <GradientStop Color="#026163" Offset="1" />
</LinearGradientBrush>

<SolidColorBrush x:Key="AccentColor" Color="#038387" />
<SolidColorBrush x:Key="TitleBarAccentedColor" Color="#038387" />
<SolidColorBrush x:Key="IconsAccentColor" Color="#038387" />
<SolidColorBrush x:Key="AccentColorDark" Color="#026163" />
<SolidColorBrush x:Key="AccentColorDarker" Color="#024D4F" />
```