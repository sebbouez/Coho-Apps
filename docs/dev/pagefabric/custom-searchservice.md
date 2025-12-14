# Custom search JSon Service

This article describes how to create your own service and use it with integrated search in PageFabric.

## Service call definition

Your service will be called by the website with two parameters in the GET querystring:

| Parameter | Description                                                                                                                                                                                     |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| q         | The text that was typed by the visitor                                                                                                                                                          |
| l         | The current page language; It should be used to give relevant results in the same language of your visitors; This value is the language you set in PageFabric (2 chars or 5 chars: en OR en-US) |

This is an example or GET query that will be done:

```http request
https://mywebsite.com/mysearchapi?l=en-US&q=some%20text
```

## Service result description

Your service must return a JSon feed that follow these specifications:

1. It is a list of entities that represent results to the user's search
1. Each result entity contains all those properties:

| Property Name | Description                                                             |
|---------------|-------------------------------------------------------------------------|
| url           | The URL of the page, it can be absolute or relative to the current page |
| title         | The title of the result page                                            |
| keywords      | The keywords that define the result page                                |
| description   | The short description of the content on the result page                 |

## JSon feed example

This example will show 2 results after the visitor launches the search.

```js
[{
    "url": "/en-US/home.html",
    "title": "Welcome to Fabrikam International",
    "keywords": "", "description": "Fabrikam is a worldwide company that produces great techs."

}, {

    "url": "/en-US/contact.html",
    "title": "Contact Fabrikam International",
    "keywords": "",
    "description": "Contact a reseller near you."

}]
```