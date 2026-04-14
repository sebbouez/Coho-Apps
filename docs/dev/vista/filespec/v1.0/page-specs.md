# Vista Diagram XML Format Specification Version 1.0

## Overview

This XML format describes a diagram document, including:

- document-level properties,
- layers,
- stencil instances,
- visual and layout properties,
- optional custom data,
- connector points for linking shapes.

It is designed for structured diagram editors and rendering engines that need to persist both layout and semantic
information.

---

## File Structure

The root element is:

- `Diagram`

The main sections are:

- `Properties` — general diagram metadata
- `Layers` — layer definitions and visibility state
- `Stencils` — diagram objects/shapes placed on the canvas
- `Connections` — links between stencils

---

## Root Element: `Diagram`

The `Diagram` element is the container for the entire document.

### Purpose

Represents one complete diagram, including all its pages, layers, and objects.

---

## `Properties` section

The `Properties` section stores high-level information about the diagram.

### Common properties

- `Name` — human-readable diagram name
- `Index` — page or diagram index

## `Layers` section

The `Layers` section defines the available layers in the diagram.

Each `Layer` has its own `Properties`.

### Layer properties

| Property    | Type   | Description                                     |
|-------------|--------|-------------------------------------------------|
| `Name`      | string | display name of the layer                       |
| `Id`        | string | unique identifier used by shapes and connectors |
| `IsVisible` | bool   | whether the layer is visible                    |
| `IsLocked`  | bool   | whether the layer is editable                   |
| `ZIndex`    | int    | layer ordering priority                         |

### Example

```xml

<Layer>
    <Properties>
        <Prop name="Name" value="Layer 1"/>
        <Prop name="Id" value="default"/>
        <Prop name="IsVisible" value="True"/>
        <Prop name="IsLocked" value="False"/>
        <Prop name="ZIndex" value="1"/>
    </Properties>
</Layer>
```

### Notes

- Layers are typically used to separate diagram content by purpose.
- A dedicated layer can be reserved for connections or links.

## `Stencils` section

The `Stencils` section contains the diagram elements placed on the canvas.

Each `Stencil` represents one drawable object, such as a shape, icon, or custom component.

### Attributes

- `type` — the stencil type, for example `SvgStencil`
- `id` — unique identifier for the stencil instance

### Stencil Properties

A stencil contains a `Properties` block that defines its visual and positional state.

#### Common properties

| Property                     | Type                              | Description                                          |
|------------------------------|-----------------------------------|------------------------------------------------------|
| `LayerId`                    | string                            | target layer identifier                              |
| `ZIndex`                     | int                               | drawing order within the layer                       |
| `Rotation`                   | int                               | rotation angle in degrees                            |
| `Opacity`                    | int                               | opacity of the shape                                 |
| `FlipHorizontal`             | bool                              | horizontal mirroring flag                            |
| `FlipVertical`               | bool                              | vertical mirroring flag                              |
| `X`                          | double                            | horizontal position                                  |
| `Y`                          | double                            | vertical position                                    |
| `Width`                      | double                            | stencil width                                        |
| `Height`                     | double                            | stencil height                                       |
| `ContentPadding`             | [`Thickness`](thickness-class.md) | internal content padding                             |
| `ContentHorizontalAlignment` | int                               | horizontal content alignment                         |
| `ContentVerticalAlignment`   | int                               | vertical content alignment                           |
| `ForegroundColor`            | [`Color`](color-class.md)         | text or icon foreground color                        |
| `BackgroundColor`            | [`Color`](color-class.md)         | background color                                     |
| `BorderColor`                | [`Color`](color-class.md)         | border color                                         |
| `BorderThickness`            | int                               | border width                                         |
| `LineStyle`                  | [`LineStyle`](linestyle-enum.md)  | border or line style                                 |
| `IsLocked`                   | bool                              | whether the stencil is editable                      |
| `MediaKey`                   | string                            | reference key for the associated media or icon asset |

### Stencil content

The `Content` element stores the stencil's textual payload.

#### Notes

- The content is wrapped in `CDATA`.
- It may be plain text or limited supported markdown.

### Stencil Datas

The `Datas` section contains arbitrary custom key-value data attached to the stencil.

#### Data entry format

- `Data`
    - `name` — custom field name
    - `value` — custom field value

### Stencil Connectors

The `Connectors` section defines attachment points on the stencil.

These points are typically used to connect lines, arrows, or relationships between shapes.

#### Connector attributes

- `id` — unique connector identifier
- `x` — horizontal position normalized to the stencil bounds
- `y` — vertical position normalized to the stencil bounds

#### Coordinate model

Connector coordinates are typically relative to the stencil box:

- `0` = left or top edge
- `1` = right or bottom edge
- `0.5` = centered

### Example

```xml

<Stencil type="RoundedRectangleStencil" id="shp.f3df0533">
    <Properties>
        <Prop name="LayerId" value="default"/>
        <Prop name="ZIndex" value="0"/>
        <Prop name="Rotation" value="0"/>
        <Prop name="FlipHorizontal" value="False"/>
        <Prop name="FlipVertical" value="False"/>
        <Prop name="X" value="251.16506958007812"/>
        <Prop name="Y" value="111.36334228515625"/>
        <Prop name="Width" value="173"/>
        <Prop name="Height" value="90"/>
        <Prop name="ContentPadding" value="0,0,0,0"/>
        <Prop name="ContentHorizontalAlignment" value="2"/>
        <Prop name="ContentVerticalAlignment" value="2"/>
        <Prop name="ForegroundColor" value="#000000"/>
        <Prop name="BackgroundColor" value="@1"/>
        <Prop name="BorderColor" value="@4"/>
        <Prop name="BorderThickness" value="1"/>
        <Prop name="LineStyle" value="0"/>
        <Prop name="IsLocked" value="False"/>
    </Properties>
    <Datas/>
    <Connectors>
        <Connector id="206b6b05-1c25-4db6-82e6-2b8114dafdef" x="0" y="0.5"/>
        <Connector id="fcd2b078-f358-49fe-91b9-9bee42c54cf7" x="1" y="0.5"/>
        <Connector id="c8e37b51-c3e2-409e-8e15-a4f0de3ad81f" x="0.5" y="0"/>
        <Connector id="b83ff590-517b-412e-8768-cbac8179bf8e" x="0.5" y="1"/>
    </Connectors>
</Stencil>
```

## `Connections` section

The `Connections` section contains links between two stencil instances.

A connection usually represents a line, arrow, or relationship that starts from one shape and ends on another.

### Attributes

- `Id` — unique identifier of the connection

### Connection properties

| Property                  | Type                                         | Description                               |
|---------------------------|----------------------------------------------|-------------------------------------------|
| `LayerId`                 | string                                       | layer used to render the connection       |
| `ZIndex`                  | int                                          | drawing order                             |
| `Style`                   | [`ConnectionStyle`](connectionstyle-enum.md) | connection style identifier               |
| `LineColor`               | string                                       | stroke color                              |
| `LineStyle`               | [`LineStyle` ](linestyle-enum.md)            | line pattern or dash style                |
| `LineThickness`           | int                                          | stroke width                              |
| `StartHeadType`           | [`ArrowHeadType`](arrowheadtype-enum.md)     | decoration at the start of the connection |
| `EndHeadType`             | [`ArrowHeadType`](arrowheadtype-enum.md)     | decoration at the end of the connection   |
| `SourceShapeId`           | string                                       | identifier of the source shape            |
| `TargetShapeId`           | string                                       | identifier of the target shape            |
| `SourceConnectionPointId` | string                                       | connector point used on the source shape  |
| `TargetConnectionPointId` | string                                       | connector point used on the target shape  |

### Notes

- Connections are typically rendered on a dedicated layer.
- Endpoint references are expected to match existing stencil and connector identifiers.
- If a connection endpoint is missing or invalid, the renderer may need to ignore or repair it.
