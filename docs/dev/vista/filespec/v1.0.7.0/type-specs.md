# Vista Data Type XML Format Specification Version 1.1

## Overview

This XML format describes a data type:

- document-level properties,

---

## File Structure

The root element is:

- `ObjectType`

The main sections are:

- `Properties` — general Type metadata
- `DataProperties` — the data type properties

---


## Example


```xml
<ObjectType>
  <Properties>
    <Prop name="Uid" value="2cb9b21f-47b7-4e4c-b65c-e905168c9e8a" />
    <Prop name="Name" value="AzureFunc" />
  </Properties>
  <DataProperties>
    <Property>
      <Prop name="Uid" value="f8c48973-24bc-4a46-8a74-f0ab7820e908" />
      <Prop name="Name" value="Name" />
      <Prop name="PropertyType" value="0" />
    </Property>
    <Property>
      <Prop name="Uid" value="23bdbfc6-1a5e-463f-bffd-3e8dad53150f" />
      <Prop name="Name" value="Methode" />
      <Prop name="PropertyType" value="0" />
    </Property>
  </DataProperties>
</ObjectType>
```
