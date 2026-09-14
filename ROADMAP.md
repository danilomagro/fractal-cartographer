# Roadmap

Ideas in rough order of how much they would change the result. Nothing here is committed — it is a
list of things worth building, not a schedule.

## Hydraulic erosion

The single biggest gain in realism. Drop droplets on the heightmap, let each one carry sediment
downhill, erode where it accelerates and deposit where it slows. Fractal noise gives mountains that
are statistically plausible but hydrologically wrong: no drainage network, no V-shaped valleys, no
alluvial fans. A few hundred thousand droplets fix all three.

- Particle-based erosion pass after the noise stage, before normalisation.
- Run it in a Web Worker so the UI keeps responding; show a progress bar.
- Expose droplet count, inertia, capacity and evaporation as an advanced group.

## Rivers and lakes

Falls out of erosion almost for free: accumulate droplet paths into a flow map, then draw anything
above a flow threshold as water. Lakes need basin filling (priority flood) to find closed
depressions.

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
