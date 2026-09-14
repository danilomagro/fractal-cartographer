# Roadmap

Ideas in rough order of how much they would change the result. Nothing here is committed — it is a
list of things worth building, not a schedule.

## Thermal erosion

Four lines next to the hydraulic pass, and a different kind of realism: any slope steeper than a
talus angle sheds material to its lower neighbours. Rounds off the spires the noise leaves behind
and piles scree at the foot of cliffs. Cheap enough to run to equilibrium.

## Rivers and lakes

Nearly free now that droplets exist: accumulate their paths into a flow map, then draw anything
above a flow threshold as water. Lakes need basin filling (priority flood) to find closed
depressions.

## Faster erosion

A droplet costs about 50 µs, so 40,000 of them take a couple of seconds. Worth revisiting if the
counts grow: a Web Worker would free the main thread (at the cost of a second file — workers do not
load from a page opened by double-click), and the grid-based pipe model parallelises onto the GPU
in a way the particle model does not.

## Parameter permalinks

Encode the whole state into the URL hash so a landscape can be shared as a link, and a seed that
happens to produce something beautiful is not lost the moment a slider moves.

## Heightmap export

- 16-bit PNG of the raw field, for use in game engines and terrain tools.
- OBJ or glTF export of the mesh as generated.
- High-resolution render of the current view, larger than the viewport.

## Tiling and infinite terrain

Sample the noise on a torus so the map tiles seamlessly, then optionally stream neighbouring chunks
as the camera moves instead of generating one fixed block.

## Biomes from a second field

A separate low-frequency noise field for temperature and humidity, crossed with elevation, so colour
comes from a biome lookup rather than a single elevation ramp. Deserts on the lee side of ranges,
forests where the moisture lands.

## Lighting and time of day

Sun azimuth and elevation as controls, soft shadow mapping, and atmospheric scattering for the sky
instead of a static CSS gradient.

## Presets

A handful of named starting points — archipelago, high plateau, fjords, badlands, crater field —
each one a saved parameter set, so the generator opens somewhere interesting instead of somewhere
average.
