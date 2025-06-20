# Changelog

## Changes since the "uvProject" beta

- **Blender 4.2 required:** The minimum version of Blender supported is now 4.2. Downloads for the uvProject beta are still available on Gumroad's download page if you are on 4.0/4.1. Most of this documentation will still be relevant.
- **Re-categorization:** All modifiers/nodes/materials now live under a ***UV Factory*** category by default. Mesh tools are still in the ***UV*** category to appear in the unwrap menu. There is still the [alternative catalog](install.md#alternative-catalog).
- **UV Grid Materials:** The UV grid textures are included as materials in the asset library instead of separate downloads.
- [**Align Islands:**](modify_uvs.md#align-islands) A new modifier/tool/node to align UV islands to a 3D vector. This can be a field/attribute.
- **UDIM Tile packing:** [Pack Islands](modify_uvs.md#pack-islands) now has an option to pack to a specific UDIM tile.
- **Island Unwrap Optimisation**: [Island Unwrap](create_uvs.md#island-unwrap) is now **much** faster on some meshes. It falls back to [Island Project](create_uvs.md#island-project) for all flat islands.
- **Unified bottom faces orientations:** Box project now matches the "island" UV generators orientation for bottom faces.
- **Many small improvements/fixes:** Fixed several edge cases and optimized/updated logic for many node internals.
