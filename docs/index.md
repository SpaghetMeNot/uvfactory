# uvFactory Home

!!! warning "Documentation not complete!"
    This documentation is WIP

    Estimated completion for uvFactory 1.0 around April/May 2025

    Please reach out if you get stuck with anything in the meantime!

Welcome to the uvFactory documentation, here you'll find everything there is to know about the tools.
<div class="grid cards" markdown>

- [:octicons-download-16: Install uvFactory](install.md)
- [:material-run: How to Use](how_to_use.md)

</div>

If something isn't clear or is missing please reach out!  
:material-email: <spaghetmenot@gmail.com>  
:fontawesome-brands-bluesky: [@spaghetmenot.bsky.social](https://bsky.app/profile/spaghetmenot.bsky.social)  
:fontawesome-brands-mastodon: [@SpaghetMeNot@mastodon.social](https://mastodon.social/@SpaghetMeNot)

## What is uvFactory?

uvFactory is a set of tools designed to automate and eliminate many tedious unwrapping tasks. Use it to speed up manual unwrapping or create fully automated UV pipelines.

In many cases it allows you to model freely while UVs appear before your eyes.

![tools](assets/all_tools.png)

### Create UVs
Sophisticated projection methods create high quality UVs:

1. **Oriented**. UVs are aligned with object's up axis by default. Ideal for directional textures e.g. bricks, tiles, wood, leaks etc.
2. **Stable**. Unlike other procedural UV solutions, the projections are stable by default and if left unpacked, don't jump around as you change your model.
3. **Automatic and manual**. All projection types are available as modifiers and tools. UVs can be created in real-time as you model or you can use the tools directly in edit mode for fast manual UV unwrapping.

### Modify UVs
Edit UVs directly in the 3D viewport or procedurally via modifiers/nodes:

- **Transform**. Offset, rotate and scale UVs.
- **Randomize**. Randomize UV transforms.
- **Pack**. Quick access to Blender's Packing algorithm.
- **Align**. Align UVs to face a desired orientation.
- **Copy**. Copy UVs from one map to another.

  

### Create your own "UV Factory"

Chain together the tools as modifiers or nodes to create your own complex custom UV pipelines. There are extra tools included for managing UV seams and sharp edges.

----

## Where can I get uvFactory?

!!! warning "Blender 4.1+ Recommended (Blender 4.0+ Required)"
uvFactory is available on Gumroad and will be released on Blender Market for version 1.0

<div class="grid cards" markdown>
- [:simple-gumroad: Gumroad](https://spaghetmenot.gumroad.com/l/uvproject)
</div>