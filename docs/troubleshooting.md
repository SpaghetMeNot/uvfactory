# Troubleshooting

## UVs aren't appearing / changing

- Check that the `UV Map` specified is an existing map on your mesh.
- Check the `Selection` section. Have you specified a vertex group or material that doesn't exist?
- Check that the modifier is enabled.

## UVs are stretched / misaligned / have errors

- Apply scale/rotation to objects.
- Check for non-manifold geometry and impossible faces.
- Check the seams are sensible when using 'Island' projection methods. Projection modifiers will produce a `uv_seam` edge attribute that you can check.
- Ngons can sometimes by tricksy, a triangulate modifier before performing UV operations can help.

## Other issues?

Please reach out! I'm always happy to help.

:material-email: <spaghetmenot@gmail.com>   
:fontawesome-brands-bluesky: [@spaghetmenot.bsky.social](https://bsky.app/profile/spaghetmenot.bsky.social)  
:fontawesome-brands-mastodon: [@SpaghetMeNot@mastodon.social](https://mastodon.social/@SpaghetMeNot)  