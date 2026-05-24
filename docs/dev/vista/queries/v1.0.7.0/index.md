# Query language model

Queries are written in a simple language that is similar to SQL.


## Query Language Description
The query language is a simple, SQL-like language used to search for shapes that match specific conditions.
A query starts with the `SEARCH` keyword, followed by the target collection, such as `shapes`. The `WHERE` clause defines the filtering criteria that each shape must satisfy.


### Basic Structure

``` sql
SEARCH shapes WHERE <condition>
```

### Field Conditions
Conditions can compare shape properties using field paths and comparison operators.
Field paths may reference nested properties using dot notation, for example:

``` sql
meta.status = 'active'
size.width > 300
size.height < 100
```

### Comparison Operators
The following comparison operators are supported:

| Operator | Description              |
|----------|--------------------------|
| =        | equal to                 |
| !=       | not equal to             |
| <        | less than                |
| <=       | less than or equal to    |
| \>       | greater than             |
| >=       | greater than or equal to |

String values are written between single quotes, while numeric values are written directly.

**Example:**
```sql
SEARCH shapes WHERE meta.status = 'active'
```

### Logical Operators
Multiple conditions can be combined using logical operators such as `AND` and `NOT`.

**Example:**

```sql
SEARCH shapes WHERE size.width > 300 AND size.height < 100
```


### Relationship Conditions
The language can also filter shapes based on their links to other shapes.
The `HAS LINK` clause checks whether a shape has at least one linked shape matching a condition.

**Example:**
```sql
SEARCH shapes WHERE HAS LINK (meta.type = 'server')
```

Links can be filtered by direction:
* `HAS OUTGOING` checks outgoing links from the current shape.
* `HAS INCOMING` checks incoming links to the current shape.

**Example:**
```sql
SEARCH shapes WHERE NOT HAS OUTGOING (meta.status = 'archived')
```


## Examples 

```sql 
SEARCH shapes WHERE meta.status = 'active'
SEARCH shapes WHERE size.width > 300 AND size.height < 100
SEARCH shapes WHERE HAS LINK (meta.type = 'server')
SEARCH shapes WHERE NOT HAS OUTGOING (meta.status = 'archived')
SEARCH shapes WHERE meta.type = 'router' AND NOT HAS INCOMING (meta.env = 'dev')
```