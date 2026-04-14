# Vista file specification Version 1.0

Vista uses a custom file format to store your diagrams data.  
This file format adopts the same logic as the Open Document Format, based on XML packed in ZIP archives.  
This documentations describes the file format to help you create tools to read and write this format.


## Archive composition

The archive file is a ZIP archive containing the following files:

```text
file.vdox
 |- meta.xml
  |- pages/
    |- page1.xml
    |- page2.xml
  |- medias/
    |- image1.svg
    |- image2.svg
```

## General Specification

| Specs name                 |                                    |
|----------------------------|------------------------------------|
| Metadata file (/meta.xml)  | [Read format specs](meta-specs.md) | 
| Pages files (/pages/*.xml) | [Read format specs](page-specs.md) |

## Other references

This section references classes and enums used in the file format.

| Specs name           |                                       |
|----------------------|---------------------------------------|
| ArrowHeadType Enum   | [Read specs](arrowheadtype-enum.md)   | 
| Color Class          | [Read specs](color-class.md)          | 
| ConnectionStyle Enum | [Read specs](connectionstyle-enum.md) | 
| LineStyle Enum       | [Read specs](linestyle-enum.md)       | 
| Thickness Class      | [Read specs](thickness-class.md)      | 
