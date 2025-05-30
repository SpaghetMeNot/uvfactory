# Extra tools

This page details the tools included with uvFactory that do not create or modify UVs directly.

## Sharp Edges

![transform](assets/icons/Mod_Edit_Sharp_Edges.png){ width=150 align=right }

Automatically mark edges as sharp on a mesh. This is similar to Blender's ***Smooth by Angle*** modifier, but with the ability to distinguish between convex and concave edges. This allows you to specify different angles for convex and concave sharp edges by using two modifiers.

- **Keep Existing.** Keep all existing sharp edges.
- **Angle.** Angle at which to mark edges as sharp.
- **Convex.** Apply sharp to convex edges.
- **Concave.** Apply sharp to concave edges.

## Seam Attribute

![transform](assets/icons/Mod_UV_Mark_Seams.png){ width=150 align=right }

Create an edge attribute for use as UV seams. This can sometimes be useful before [creating UVs](create_uvs.md).

### Seams

- **Edge Angle.** Edges that have a greater angle than that specified will be used as seams. Setting this to 360 or above will disable seams by edge angle.
- **Sharp Edges.** Edges marked as sharp will be used as UV seams.
- **Detect Existing.** Use existing seams in the specified UV map. This will only detect seams if there is a gap in UV space, it cannot detect unwelded UVs or the seam attribute.

### Box Projection Seams

- **Add Box Projection Seams.** Uses the [Box Projection](create_uvs.md#box-project) logic to generate seams.
- **Z Axis Bias.** See [Projection Transform](create_uvs.md#projection-transform) settings.
- **Rotate Projection XYZ.** See [Projection Transform](create_uvs.md#projection-transform) settings.

### Output Attributes

- **UV Seam.** The edge boolean attribute to write to.

</asdf>

## UV Existing Seams

![transform](assets/icons/Node_UV_ExistingSeams.png){ width=150 align=right }

!!! info "Geometry Nodes only"

This node contains the logic behind every ***Detect Existing*** UV seam option. This will only detect seams if there is a gap in UV space, it cannot detect unwelded UVs or the seam attribute.
