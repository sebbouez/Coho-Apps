# Document module

The `document` module provides a set of methods to interact with the current document.

Import the module with:

```js
import {document} from 'lib';
```

## Methods






### ClearHighlight()

This method clears all the highlights in the document.

#### Arguments

* None.

#### Example

```js
import {document} from 'lib';

document.ClearHighlight();
```





### GetShapeById(string id)

This method returns the shape with the specified id in the document.

#### Arguments

* `string` id : The id of the shape to return.

#### Returns

* [`Shape`](class-shape.md) : The shape with the specified name. Can be `null` if no shape with the specified name
  exists.

#### Example

```js
import {document} from 'lib';

let sel = document.GetShapeById("shp.1234");

```




### GetShapeByName(string name)

This method returns the shape with the specified name in the document.

#### Arguments

* `string` name : The name of the shape to return.

#### Returns

* [`Shape`](class-shape.md) : The shape with the specified name. Can be `null` if no shape with the specified name
  exists.

#### Example

```js
import {document} from 'lib';

let sel = document.GetShapeByName("myShape");
// sel is now the shape with the name "myShape"
```





### GetSelection()

This method returns the selected items in the document.

#### Arguments

* None.

#### Example

```js
import {document} from 'lib';

let sel = document.GetSelection();
// sel is now an array of selected items
```




### Query(string query)

This method executes a query on the document and returns the found shapes.

#### Arguments

* `string` query : The query to execute. See [Query language model](../../queries/v1.0.7.0/index.md)

#### Returns

* List of [`Shape`](class-shape.md) : Found shapes.

#### Example

```js
import {document} from 'lib';

let shapes = document.Query("SEARCH shapes WHERE meta.method = 'post'");

for (let i = 0; i < shapes.Count; i++) {
  shapes[i].Highlight();
}
```








### SelectAll()

This method selects all items in the document.

#### Arguments

* None.

#### Example

```js
import {document} from 'lib';

document.SelectAll();
```





### UnSelectAll()

This method unselects all items in the document.

#### Arguments

* None.

#### Example

```js
import {document} from 'lib';

document.UnSelectAll();
```