# Cosmic Calm - Interactive Edition

A browser-based generative visual experience designed for relaxation and focus. Seven immersive 3D modes run entirely in your browser — no backend, no login, no time limit. Built to leave running for hours.

Live at [mortgageratemonitor.github.io/visual-calm-interactive](https://mortgageratemonitor.github.io/visual-calm-interactive/)



---

## Modes

### Warp
You are traveling through deep space at warp speed. Colorful tunnel rings surround you while thousands of stars stretch into streaking lines of light as you accelerate. Stars close to the tunnel axis pick up color from the rings; stars further out fade toward white. A deep blue-purple fog gives the tunnel real depth.

A **Pulse** toggle sits in the bottom-right corner. When enabled, the ship surges every ~9 seconds — the tunnel compresses, stars blur outward dramatically, then everything settles back to cruising speed. Toggle it off for a denser starfield (16,000 stars vs 7,000) and a calmer, steady experience.

**Interactive:** Scroll to control warp speed in real time — stars stretch longer as you accelerate. Click anywhere to trigger an on-demand pulse surge with a ring flash. A speed indicator appears bottom-left.

---

### Forest Stream
You drift slowly above a forest stream at golden hour, built from layered environmental systems.

**Water** — a subdivided mesh ripples with layered sine-wave displacement. A reflection layer pulses in sync with overhead light shafts. Expanding ripple rings spawn randomly across the water surface. **God-ray** light shafts pulse down through a canopy of 36 swaying leaf planes.

**Forest** — 28 three-dimensional trees line the stream, each with a tapered trunk and overlapping foliage clusters. Two layers of ground mist hug the water surface. Fine dust, glowing pollen, and spores float through the air. Fireflies pulse near the waterline.

**Interactive:** Click the water surface to place a ripple exactly where you click. Click above the water to scatter nearby spores and fireflies outward from your cursor.

---

### Deep Ocean
You drift through a bioluminescent deep-sea environment. Blue-green light shafts pierce down from the surface. 1,800 bioluminescent particles pulse in blue, cyan, and teal. 600 bubbles rise steadily upward. 14 jellyfish — built from glowing torus bells and trailing tentacle line segments — drift in gentle arcs.

**Interactive:** Click anywhere to trigger a bioluminescent bloom burst — nearby particles explode outward and the field briefly supercharges before fading back over ~2 seconds. Move your cursor near a jellyfish and it will dart away, accumulating velocity and damping smoothly into a new position.

---

### Sacred Geometry
A meditative 3D geometry experience. Five nested Platonic solids — icosahedron, dodecahedron, octahedron, tetrahedron, and a second icosahedron — rotate on independent axes, each with a wireframe shell and translucent face fill. Colors breathe slowly through the hue spectrum. Three rings of line segments link vertices between shells. 280 node particles orbit the structure. A pulsing white bloom expands and contracts at the center.

A **Spiral** toggle sits in the bottom-right corner. When enabled, the camera slowly spirals inward over 60 seconds — pulling you deep inside the nested geometry — then releases back out. Defaults to off.

**Interactive:** Click to trigger a shockwave — all node particles burst outward and elastically snap back while the nested solids briefly scale up. Scroll to zoom the camera in and out, floating right into the center or pulling back to see all layers.

---

### Desert Night
You drift slowly over a moonlit desert. A full moon with a soft glow halo casts a cool blue-silver wash across the scene. Rolling dune silhouettes line the horizon with bright ridge highlights. Saguaro cacti, branching arms, and angular rock formations provide depth. The Milky Way starfield twinkles continuously. Fine dust drifts in a slow desert wind.

**Desert wildlife** crosses the scene occasionally, each with a distinct silhouette:
- **Roadrunner** — darts quickly across, legs alternating, head bobbing, tail angled upward
- **Quail** — a covey of 4–7 birds crosses slowly together, each with an iconic topknot plume
- **Gila Monster** — crawls deliberately slow, segmented body undulating, four splayed legs shuffling
- **Coyote** — trots across at medium speed, occasionally pausing mid-stride
- **Javelina** — a group of 2–3 stocky peccaries shuffle together, bristly ridge along the back

**Interactive:** Click anywhere in the sky to fire a shooting star from that screen position — it streaks diagonally away from the click point. Click the ground to spawn a swirling dust devil that spirals upward and disperses over ~6 seconds. Up to 3 dust devils can coexist.

---

### Thunderstorm
You drift over a dark landscape as a massive storm rolls overhead. Three depth layers of volumetric clouds drift at different speeds creating genuine parallax. Lightning bolts are jagged 14-segment strikes with a secondary branch off the midpoint, each triggering a cloud flash and secondary flicker. Distant horizon lightning flares inside far clouds every few seconds — no bolt visible, just the storm lit from within. Ground puddle reflections shimmer and briefly brighten with each flash. Rain streams down at a wind angle with periodic squalls. Wind-blown debris crosses the scene horizontally.

A **Storm** toggle sits in the bottom-right corner. When enabled, lightning strikes every 2–6 seconds. Toggle it off for infrequent lightning every 12–18 seconds.

**Interactive:** Click anywhere to call a lightning strike at that horizontal screen position, complete with full flash, branching bolt, and puddle reflection. Hold the mouse button down to intensify the squall on demand — rain thickens while held, eases when released.

---

### Murmuration
3,500 starlings wheel and ripple across a moonlit desert sky using an emergent Boids simulation — no shapes are scripted, every formation arises from three simple rules applied to each bird simultaneously: stay apart from immediate neighbors, match the velocity of nearby birds, drift toward the local center of mass. The result is a living, breathing mass that folds, splits, and reforms unpredictably every second.

You observe from a fixed vantage point at a distance, watching the flock move against the full Desert Night environment — starfield, moon with glow halo, dunes with ridge highlights, saguaro cacti, and rock formations — giving the birds real depth and scale to fly against. The camera sways gently from side to side over time.

**Interactive:** Click anywhere to send a hawk into the flock at that exact screen position. The hawk appears as an amber streak and applies a strong repulsion force to every bird within range — the flock parts, swirls, and closes back around it. Up to 3 hawks can be active at once; each fades out after 8 seconds.

---

## Controls

| Input | Effect |
|-------|--------|
| **Mode buttons** | Bottom center pill — switches between the seven scenes with a fade transition |
| **Mouse move / finger drag** | Subtly influences every scene |
| **Click** | Triggers an interaction unique to the current scene |
| **Scroll** | Warp: adjusts speed · Sacred Geometry: zooms camera |
| **Hold click** | Thunderstorm: intensifies the rain squall |
| **Pulse toggle** | Bottom right — Warp mode only |
| **Spiral toggle** | Bottom right — Sacred Geometry mode only |
| **Storm toggle** | Bottom right — Thunderstorm mode only |
| **Fullscreen button** | Top right |

A hint appears briefly above the nav bar when entering each scene, describing its interaction. It fades after 5 seconds or on the first click.

UI and toggles auto-hide after 3.5 seconds of inactivity and reappear on any mouse movement or tap.

---

## Device Support

- **Desktop** — full experience with mouse interaction, scroll, and custom cursor
- **Mobile & tablet** — full touch support; drag to influence the scene, tap to trigger interactions
- Works in Chrome, Safari, Firefox, and Edge on both desktop and mobile

---

## Technical Notes

- Built with [Three.js](https://threejs.org/) (r128) and vanilla JavaScript
- Single `index.html` — no build step, no dependencies to install
- Frame rate capped at 30fps with full memory cleanup on every scene switch
- All interactivity uses raycasting against the live 3D scene — no screen-space hacks
- Murmuration uses an integer-key spatial hash grid (pre-allocated typed arrays, zero heap allocation per frame) with physics running at 15fps and positions integrating at 30fps for smooth motion
- Hosted via GitHub Pages — static, always-on, no cold starts
