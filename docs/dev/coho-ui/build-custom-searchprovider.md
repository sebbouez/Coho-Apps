# Build custom search provider for the Omnibar

The `ApplicationWindow` provides an Omnibar search bar in the window chrome title bar. By default it will search through the ribbon commands to provide the user a quick and easy access.  
You can extend this feature by adding you own search provider. For example, you may want to help your users to find files in a project, or any other item that your application manages.  
This article will help you create and register a new search provider for the built-in omnibar search.

## The service class
Your custom search provider must inherit from `OmnibarSearchServiceBase`.  
This is a typical content of a custom search provider:

```cs
public class CustomOmnibarSearchService : OmnibarSearchServiceBase
{
    // The text that will be displayed in the drop down popup
    public override string DisplayName
    {
        get
        {
            return "Search in files...";
        }
    }

    // The icon that will be shown next to the text above
    public override Brush Icon
    {
        get
        {
            return Brushes.Transparent;
        }
    }

    // The results to show after the user has launched your search provider
    public override IEnumerable<OmnibarSearchResult> ExecuteSearch(string terms)
    {
        // Perform your search operation using the argument "terms" that contains the text typed by the user.
        // Then return the list of results.
    }
}
```

Once registered, this search provider will look like this:  
<img width="328" alt="image" src="https://user-images.githubusercontent.com/39953434/235304626-fed7a404-ef62-4d0c-8efd-8f5df7ef9f95.png">


## Register your service provider
To make the application know your custom search provider, you have to register it using the `OmnibarSearchService.RegisterOmnibarSearchService()` method in the `Window_Loaded` event.

```cs
private void MainWindow_Loaded(object sender, RoutedEventArgs e)
{
    ...
    // Register your custom service in the Window_Loaded event
    OmnibarSearchService.RegisterOmnibarSearchService(new CustomOmnibarSearchService());
}
```

## Handle the search result click
After the search, when the user clicks a result in the drop down list, the event `OmnibarSearchService.SearchResultClicked` is raised. You can listen to it to perform the corresponding action.

```cs
private void MainWindow_Loaded(object sender, RoutedEventArgs e)
{
    ...
    OmnibarSearchService.RegisterOmnibarSearchService(new CustomOmnibarSearchService());
    
    // Add this line to handle the click event on a search result.
    OmnibarSearchService.SearchResultClicked += OmnibarSearchServiceOnSearchResultClicked;
}

private void OmnibarSearchServiceOnSearchResultClicked(object? sender, OmnibarSearchResult e)
{
    // Do something with the result that the user has selected.
    MessageBox.Show("You clicked " + e.CommandTabName);
}
```