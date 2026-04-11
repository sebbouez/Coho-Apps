# Document module

The `document` module provides a set of methods to interact with the current document.

Import the module with:

```js
import {document} from 'lib';
```

## Methods


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

### SelectAll()

This method selects all items in the document.

#### Arguments

* None.

#### Example

```js
import {document} from 'lib';

document.SelectAll();
```