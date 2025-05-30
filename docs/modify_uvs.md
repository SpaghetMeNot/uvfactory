# Modify UVs

## Transform Tools

Most UV modification tools apply some form of transformation to existing UVs. All transform tools are available as [modifiers](tools_overview.md#modifiers), [nodes](tools_overview.md#geometry-nodes) and [mesh tools](tools_overview.md#mesh-tools).

### Common Settings

All transform tools have common settings to specify which UVs to modify.

- **UV Map.** Which UV map to modify. This is a string parameter currently, be sure the name matches the map you wish to modify.

#### Seams

- **Detect Existing.** Use existing seams in the specified UV map. This will only detect seams if there is a gap in UV space, it cannot detect unwelded UVs or the seam attribute.
- **Attribute.** UV seam attribute. Each uvFactory node that creates nodes also creates this attribute. As of Blender 4.4 it also includes manually marked seams.

#### Selection

- **Selection.** Which faces to modify UVs for. Defaults to "on", applying to every face.
- **Material.** Limit UV modification to a specific material.
- **Invert Selection.** Inverts the selection to modify UVs on every face that isn't selected using the above options.

### Transform

Apply basic offset, rotation and scale to UVs.

- **Per Island.** Apply transforms per UV island when turned on. Otherwise transforms will be in global UV space.
- **Offset U / Offset V.** Offset UVs in either direction uniformly.
- **Uniform Scale.** Apply uniform scale to UVs. This will use the ***Scale U*** value.
- **Scale U / Scale V.** Apply scale to UVs. When ***Uniform Scale*** is on, only the ***U*** value will be used.

### Pack Islands

Packs UV islands into 0-1 UV space. This uses Blender's native geometry node packing algorithm. This is less effective than the ***Pack Islands*** tool in the UV Editor. For use when procedural packing is required.

- **Margin.** The distance to leave between UV islands.
- **Rotate.** Allow Rotating islands for best fit.

### Align Islands

Aligns UV islands to a vector in 3D space. UVs will be oriented to the "slope" of islands relative to the input vector.

- **Reference Object.** Specify an object to align UVs too.
- **Align Vector.** Vector to align UVs to. This can be a constant or an attribute/field. When inputting an attribute/field, it will be averaged across each island before aligning.

### Randomize Islands

Randomizes offset, rotation and scale of UV islands.

- **Seed.** The seed used for randomization.
- **Snapped Rotation.** Will rotate UV Islands randomly by multiples of the ***Snap Increment***. This can be useful for materials such as wood or tiles, and works best with values of either 90° or 180°.
- **Snap Increment.** The angle to use for ***Snapped Rotation***.
- **Smooth Rotation.** Rotates UV islands randomly up to a maximum of this angle.
- **Offset U / Offset V.** Applies a random offset per UV island in the specified axis up to a maximum of this value.
- **Uniform Scale.** Whether or not to use uniform scale. When on ***Scale U*** will be used.
- **Scale U / Scale V.** Applies a random scale in the specified axis. The value will be added/subtracted to a default scale of 1. When ***Uniform Scale*** is on only ***Scale U*** will be used.

## Copy Map

Copy all UVs from one map to another.

- **Copy Map.** UV Map to copy from.
- **To.** UV Map to copy to. Enter the name of the map you wish to copy to. This will overwrite any existing UVs.
