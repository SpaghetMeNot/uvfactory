# Create UVs

## UV Generation Methods

There are 3 methods for generating UVs with uvFactory. Each is available as both a modifier and an edit mesh tool:

- [Box Project](#box-project)
- [Island Project](#island-project)
- [Island Unwrap](#island-unwrap)

### Box Project

Box Project is the simplest and fastest method. Each face is planar projected from the most appropriate axis. It is a fairly standard way of projecting UVs and is similar to the method in Blender's Texture shader node.

![box project](assets/box_project.gif)

### Island Project

Island Project performs a planar UV projection per island*. UVs are oriented based on the model's Z axis. This works well for models made of flat surfaces but there will be stretching if islands are curved.

![island project](assets/island_project.gif)

### Island Unwrap

Island Unwrap is the most advanced projection method. It unwraps and flattens each island* then orients the UVs in the same way as [Island Project](#island-project). It also has logic for handling cylindrical or looped UV islands.  
On low to mid poly meshes with sharp edges, this method produces the best fully automatic results.

![island unwrap](assets/island_unwrap.gif)

!!! info "*Islands"
    **Island Project** and **Island Unwrap** first define where UV islands are using seam edges. These are controlled in the [Seams](#seams) section of their settings."

----

## Settings

Most of the settings for UV generators are identical across generation methods. Specific settings are called out in the relevant sections.

- **Tile Size.** Scales the UVs. For tiling textures this should match the expected size of the texture.
- **UV Map.** Which UV map to write to. This is a string parameter currently, be sure the name matches the map you wish to write to.

### Selection

Controls which faces the UV modifier applies to.

- **Selection.** Defaults to generating UVs for every face. You can limit to vertex groups by specifying as an attribute.
- **Material.** Limit the UV generation to a specific material.
- **Invert Selection.** Inverts the selection to generate UVs on every face that isn't selected using the above options.

### UV Transform

Transform the UVs in UV space after they have been generated.

- **Offset U.** Offsets generated UVs in U direction.
- **Offset V.** Offsets generated UVs in V direction.
- **Rotate Islands.** Rotates each island around it's center in degrees.

### Projection Transform

Transform the projection of UVs in 3d space. You can think of this as transforming the object itself, projecting the UVs, then transforming it back to it's original orientation.

- **Reference Origin.** Specify an object to align, scale and center UVs too. This can offer a very visual way of transforming the projection and can be very useful when you need multiple objects to match UVs.
- **Offset XYZ.** Offset the projection/alignment of UVs in object space
- **Rotate XYZ*.** Rotate the projection/alignment of UVs in object space. Note that for island-based UV generation, Z rotation will only affect perfectly aligned top and bottom faces. This is because all other faces are aligned to their slope.

!!! info "Box Project"
    - **Z Axis Bias.** Controls the angle at which faces will be projected from the Z axis (top and bottom). Increase to include more faces, decrease to include less.

!!! info "Island Unwrap"
    - **Initial Pack Size.** Advanced option that should be left at 1.0 in most cases. Raising this value can sometimes reduce errors on complex meshes at the cost of speed.

### Seams

!!! info "Island Project & Island Unwrap only"
Control where seam edges are that define UV islands.

- **Edge Angle.** Edges that have a greater angle than that specified will be used as seams. Setting this to 360 or above will effectively disable seams by edge angle.
- **Sharp Edges.** Edges marked as sharp will be used as UV seams.
- **Detect Existing.** Use existing seams in the specified UV map. This will only detect seams if there is a gap in UV space, it cannot detect unwelded UVs or the seam attribute.
- **Attribute.** Specify an edge attribute to use as seams. As of Blender 4.4 this will detect manually marked seams when set to the "uv_seam" attribute.

## Output Attributes

- **UV Seam.** Outputs all the UV seams created by UV generation. This is an edge boolean attribute and is useful for other uvFactory processes.