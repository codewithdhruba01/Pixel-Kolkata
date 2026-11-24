# Development Roadmap

## Delivery strategy

Build a small, technically complete prototype first, then scale the same engine and pipeline to the agreed city boundary. The schedule below is an indicative plan for a small team; actual timing depends heavily on artwork and geographic-data quality.

## Phase 0 — Scope and project setup

Tasks:
- Confirm the geographic boundary.
- Create repository and documentation.
- Set up Next.js, TypeScript and Tailwind.
- Add PixiJS and a minimal canvas lifecycle.
- Define code style and environment variables.

Exit criteria:
- App starts locally.
- PixiJS canvas mounts and cleans up correctly.
- README and project scripts are in place.

## Phase 1 — Isometric engine prototype

Tasks:
- Implement grid-to-isometric and inverse conversion.
- Render a small test grid.
- Add camera pan and zoom.
- Add pointer hit testing.
- Add sprite depth sorting.
- Add a sample landmark sprite.

Exit criteria:
- User can pan and zoom a small demo scene.
- A rendered object can be selected reliably.
- Coordinate transforms pass unit tests.

## Phase 2 — Geographic data foundation

Tasks:
- Approve coverage boundary.
- Acquire a small test extract.
- Build Python processing scripts.
- Normalize roads, buildings, water and green spaces.
- Create a source/provenance register.
- Generate a first chunk manifest.

Exit criteria:
- Reproducible pipeline produces validated test chunks.
- Source licensing and attribution are documented.

## Phase 3 — Art system

Tasks:
- Define palette and sprite conventions.
- Create terrain, water and road tiles.
- Create generic building families.
- Create initial Kolkata landmark sprites.
- Test atlases and rendering scale.

Exit criteria:
- A coherent sample neighbourhood can be rendered.
- Assets have consistent perspective, anchors and dimensions.

## Phase 4 — City chunk generation

Tasks:
- Process the full approved boundary.
- Generate chunk assets and metadata.
- Implement visible-chunk detection and caching.
- Add chunk loading, retry and eviction.
- Validate seams and coverage.

Exit criteria:
- User can explore the full approved boundary.
- Map remains usable while moving between chunks.

## Phase 5 — Discovery features

Tasks:
- Add location search and pagination.
- Add category filters.
- Add selected-place detail panel.
- Add camera fly-to and highlight.
- Add neighbourhood navigation.

Exit criteria:
- Search results correctly navigate to verified map locations.
- Details and filters work on desktop and mobile.

## Phase 6 — Quality and release

Tasks:
- Profile reference devices.
- Optimize atlases, culling and level of detail.
- Add accessibility and reduced-motion support.
- Add error handling and telemetry.
- Verify attribution and privacy copy.
- Deploy staging, run acceptance tests, then release.

Exit criteria:
- Release checklist passes.
- No known critical data, security or rendering defects.

## Suggested first two weeks

### Week 1
- Day 1: Create repository and Next.js app.
- Day 2: Integrate PixiJS safely in a client component.
- Day 3: Render isometric diamond tiles.
- Day 4: Implement camera pan and zoom.
- Day 5: Add sample buildings and depth sorting.

### Week 2
- Day 1: Add object selection and hit testing.
- Day 2: Add a sample landmark and detail panel.
- Day 3: Define map coordinate conventions.
- Day 4: Process a small geographic sample.
- Day 5: Review prototype and lock the next phase scope.

## Release checklist

- [ ] Approved coverage boundary is versioned.
- [ ] Data source register and attribution are complete.
- [ ] Map pan, zoom and reset work.
- [ ] Chunk loading and error recovery work.
- [ ] Search and landmark details work.
- [ ] Keyboard and touch interactions are tested.
- [ ] Performance is measured on reference devices.
- [ ] Secrets are server-only.
- [ ] Privacy and licensing notes are published.
- [ ] Production build and deployment are verified.
