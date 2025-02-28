!!! warning ":construction_site: :construction:"

There are 3 methods for generating UVs with uvFactory:

- Box Project
- Island Project
- Island Unwrap

Here you can see a comparison of all three methods and Blender's "Smart UV Project"
![](assets/methods_compare.gif)

**Island Project** and **Island Unwrap** first define where UV islands are using seam edges. These are controlled in the "Seam" section of inputs.

## Box Project
Box Project is the simplest and fastest method. Each face is planar projected from the most appropriate axis. It is a fairly standard way of projecting UVs and is similar to the method in Blender's Texture shader node.

## Island Project
Island Project performs a planar UV projection per island. UVs are oriented based on the model's Z axis. This works well for models made of flat surfaces as there will be stretching if Islands are curved.

## Island Unwrap
Island Unwrap is the most advanced projection method. It unwraps and flattens each island then orients the UVs in the same way as "Island Project". It also has logic for handling cylindrical or looped UV islands.

On low to mid poly meshes with sharp edges, "Island Unwrap" produces the best fully automatic results.