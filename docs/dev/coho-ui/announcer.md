# Announcer control

The `Announcer` is a slider that allows you to specify the number of items per page and the template of bound items.

## AnnounceTemplate (DataTemplate)
The **AnnounceTemplate** property defines the template to be used to display items in the slider.

### Example

``` xaml
<announcer:Announcer AnnouncesAreaMargin="0,8,0,0" Margin="0,8" ItemsPerView="4"
                                     x:Name="AnnouncesPresenter" MinHeight="200">
                    <announcer:Announcer.AnnounceTemplate>
                        <DataTemplate>
                            <Border x:Name="BdrContainer" CornerRadius="6">
                                <StackPanel>
                                    <TextBlock Text="{Binding Title}" FontWeight="SemiBold" FontSize="14"
                                               TextWrapping="Wrap" Margin="0,0,10,0" />
                                    <TextBlock Text="{Binding Content}"
                                               TextWrapping="Wrap" Margin="0,0,10,0" />
                                </StackPanel>
                            </Border>
                        </DataTemplate>
                    </announcer:Announcer.AnnounceTemplate>
</announcer:Announcer>
```

## IsLoadingContent (DependencyProperty, bool)
The **IsLoadingContent** property is used to hide control content and display a `LoadingRing` to indicate that content is being loaded.

### Example

``` csharp
// Put the control in Loading mode, it shows a loading ring
AnnouncesPresenter.IsLoadingContent = true;

OnlineContentService.GetItems().ContinueWith(r =>
{
    // Stop the loading mode to show fetched items
    AnnouncesPresenter.IsLoadingContent = false;
    AnnouncesPresenter.ItemsSource = r.Result;

}, TaskScheduler.FromCurrentSynchronizationContext());

```

## ItemsPerView (DependencyProperty, int)
The **ItemsPerView** property is used to set the number of items per page. When there are more items than this value, the user can slide content using the arrows on the top right of the control.

## ItemsSource (IEnumerable&lt;object&gt;)
The **ItemsSource** property is used to set the collection of objects to display.

### Example

``` csharp
// Put the control in Loading mode, it shows a loading ring
AnnouncesPresenter.IsLoadingContent = true;

OnlineContentService.GetItems().ContinueWith(r =>
{
    // Stop the loading mode to show fetched items
    AnnouncesPresenter.IsLoadingContent = false;
    AnnouncesPresenter.ItemsSource = r.Result;

}, TaskScheduler.FromCurrentSynchronizationContext());

```


## Label (DependencyProperty, string)
The **Label** property is used to set the text displayed at the top of the `Announcer` control.

### Example

```xaml
<announcer:Announcer AnnouncesAreaMargin="0,8,0,0" Margin="0,8" ItemsPerView="4"
                     x:Name="AnnouncesPresenter" MinHeight="200"
                     Label="{x:Static localization:Resources.OnlineResourcesDescription}">
</announcer:Announcer>
```
