# Shape Class

The `shape` class represents a single shape in the document.


## Properties

### Id
This property returns the unique Identifier of the shape.

#### Type
* `String`


### Name
This property returns the name of the shape.


#### Type
* `String`


## Methods



### Highlight()

This method highlights the shape.   

#### Arguments

* None.

#### Returns

* None.

#### Example

```js
import {document} from 'lib';

let myShape = document.GetShapeByName("shape1");
myShape.Highlight();
```





### SetContent(content:string)

This method sets the content of the shape.

#### Arguments

* `string` content : The content to set for the shape.

#### Returns

* None.

#### Example

```js
import {document} from 'lib';

let myShape = document.GetShapeByName("shape1");
myShape.SetContent("hello world");
```




### SetFillColor(hexColor:string)

This method sets the fill color of the shape.

#### Arguments

* `string` hexColor : The hex color to set for the shape.

#### Returns

* None.

#### Example

```js
import {document} from 'lib';

let myShape = document.GetShapeByName("shape1");
myShape.SetFillColor("#336699");
```