# Visual Design Guidelines

## 1. Creative direction

Pixel Kolkata should feel like a carefully illustrated city-building game: warm, inviting, readable and recognizably Kolkata.

**Visual principle:** the map is the hero. Interface controls should be quiet and should never compete with the artwork.

## 2. Map perspective

- Use a consistent 2:1 diamond tile ratio as the initial grid convention.
- Keep a consistent camera angle and light direction.
- Use clear ground, road, water, vegetation, building and landmark layers.
- Ensure adjacent tiles connect without visible seams.
- Avoid mixing top-down, side-on and isometric sprite perspectives.

## 3. Art direction

Suggested palette:
- Warm off-white and muted sandstone for buildings.
- Terracotta and faded red for selected roofs.
- Deep teal and blue-green for the Hooghly and water.
- Leaf green for parks and trees.
- Charcoal for outlines and interface text.
- Small sky-blue accents for selected UI states.

Use a restrained palette and reserve high-contrast colours for landmarks and interactive states.

## 4. Asset specifications

Initial working conventions (revise after a visual prototype):
- Ground tile: 32 × 16 px.
- Building sprites: multiples of the base tile dimensions.
- Transparent PNG or a suitable atlas format for sprites.
- Pixel edges should remain crisp; disable unintended smoothing where appropriate.
- Use consistent pivot/anchor points.
- Include collision or hit-test metadata for clickable assets.

Suggested asset groups:
- Ground: grass, pavement, soil, water.
- Roads: straight, corner, junction, crossings.
- Transit: railway, metro structures, tram track details.
- Buildings: homes, shops, markets, offices, institutions.
- Nature: trees, gardens, ponds.
- Landmarks: custom, recognizable landmark sprites.
- Details: streetlights, benches, signs and vehicles.

## 5. Landmark treatment

Major landmarks should have custom silhouettes and recognisable details. Examples:
- Victoria Memorial: pale marble mass and dome.
- Howrah Bridge: steel truss silhouette over the river.
- Prinsep Ghat: riverside monument and steps.
- Dakshineswar Temple: distinctive temple roof forms.

Do not use a generic building sprite for a landmark if the goal is recognisability.

## 6. Interface layout

### Desktop
- Compact header with brand, search and basic navigation.
- Map occupies most of the viewport.
- Floating zoom, reset and layer controls.
- Selected-place detail panel appears on demand.
- Optional minimap or neighbourhood selector.

### Mobile
- Full-screen map.
- Large touch-friendly zoom and reset controls.
- Search opens a dedicated overlay.
- Location details appear in a bottom sheet.
- Support pinch zoom and one-finger pan without trapping page scrolling unexpectedly.

## 7. Interaction states

- Default: subtle hover affordance.
- Hover/focus: outline or gentle highlight.
- Selected: clear highlight and detail panel.
- Loading: non-blocking progress indicator.
- Missing data: friendly unavailable state.
- Error: retry action where appropriate.

## 8. Accessibility

- Every icon-only control needs an accessible name.
- Search and filters must work with a keyboard.
- Do not communicate selection only through colour.
- Provide focus indicators.
- Respect `prefers-reduced-motion`.
- Keep text contrast readable.
- Provide a non-canvas list/search route to access important places.

## 9. Motion

- Camera movement should be smooth but interruptible.
- Avoid excessive parallax or continuous animation.
- Respect reduced-motion preferences.
- Do not animate thousands of map objects independently.
