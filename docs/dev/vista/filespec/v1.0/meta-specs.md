# Vista Metadata XML Format Specification Version 1.0

## Overview

In `meta.xml`.

This XML file defines the basic metadata associated with a resource or archive.

#### Overview

The Metadata XML format defines a minimal, structured way to describe basic information about a resource, package, or archive.
It is intentionally simple and contains only two fields:
* `Title`
* `Author`

This format is suitable for lightweight metadata storage, indexing, or documentation purposes.

#### File Format
* Format: XML
* Encoding: UTF-8
* Root element: `Metadata`
* Purpose: Store descriptive metadata for a content item

#### Structure
A valid metadata file must contain a single root element named Metadata, with the following child elements:
* `Title`
* `Author`

Example:

``` xml
<?xml version="1.0" encoding="utf-8"?>
<Metadata>
  <Title></Title>
  <Author></Author>
</Metadata>
```

#### Element Reference

##### `Metadata`

The root element of the document.

* **Required**: Yes
* **Occurrence**: Exactly one
* **Role**: Container for all metadata fields

##### `Title`

Represents the title of the item being described.

* **Required**: Yes, though it may be empty
* **Type**: Text
* **Role**: Identifies the name or title of the resource


##### `Author`

Represents the author or owner of the item being described.

* **Required**: Yes, though it may be empty
* **Type**: Text
* **Role**: Identifies the creator, publisher, or responsible party

