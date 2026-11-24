# Product Requirements Document (PRD)

## 1. Product overview

**Product name:** Pixel Kolkata  
**Tagline:** Explore the City. One Pixel at a Time.  
**Product type:** Interactive web-based isometric pixel-art city map.

Pixel Kolkata lets visitors explore a stylized representation of Kolkata through a navigable isometric world. It combines a game-like visual experience with useful location discovery.

## 2. Problem and opportunity

Conventional maps are useful for navigation but do not provide a playful, illustrated sense of place. Pixel Kolkata aims to make discovering neighbourhoods and landmarks memorable through a distinctive visual interface.

## 3. Goals

1. Build a responsive and performant isometric map experience.
2. Represent the agreed Kolkata coverage area using geographic data as a foundation.
3. Make important landmarks and selected places discoverable.
4. Provide search, filters, location details and camera navigation.
5. Create a reusable asset and chunk pipeline that can expand over time.

## 4. Non-goals for the first release

- Turn-by-turn navigation or routing.
- Live traffic, transit arrival times or real-time transport operations.
- Exact architectural reproduction of every building.
- Indoor maps.
- User accounts, reviews, check-ins or user-generated edits.
- A complete simulation with animated crowds and traffic.

## 5. Target users

- Residents curious about their city.
- Visitors exploring notable Kolkata places.
- Students and educators learning about local geography.
- Pixel-art, map and indie-game enthusiasts.

## 6. Core user journeys

### Journey A: Explore the map
1. Visitor opens the homepage.
2. The map loads at a useful city-wide overview.
3. Visitor drags to pan and uses controls or the wheel to zoom.
4. Nearby map chunks load as needed.

### Journey B: Find a landmark
1. Visitor enters a place name in search.
2. Matching results appear.
3. Visitor selects a result.
4. The camera moves to the place and highlights it.
5. A detail panel displays available information.

### Journey C: Filter places
1. Visitor opens category filters.
2. Visitor enables or disables categories.
3. The map updates visible points of interest.

## 7. MVP requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-01 | Render an isometric map canvas | Must |
| FR-02 | Support pointer drag to pan | Must |
| FR-03 | Support zoom in/out with sensible limits | Must |
| FR-04 | Load map content by visible chunks | Must |
| FR-05 | Display selected landmarks | Must |
| FR-06 | Select a landmark and show details | Must |
| FR-07 | Search known locations | Should |
| FR-08 | Filter points by category | Should |
| FR-09 | Provide a reset/home camera action | Should |
| FR-10 | Work on common desktop and mobile screens | Must |
| FR-11 | Show loading and error states | Must |
| FR-12 | Provide data-source attribution | Must |

## 8. Content and coverage

The project must define a versioned geographic boundary before building the production dataset. Proposed initial coverage:

- Central Kolkata
- North Kolkata
- South Kolkata
- East Kolkata, including Bidhannagar/Salt Lake and New Town/Rajarhat
- Howrah and selected west-bank riverfront areas

The exact extent must be agreed and recorded as a boundary GeoJSON. “Full coverage” means coverage of that defined boundary; it does not guarantee individually illustrated or verified detail for every property.

## 9. Landmark launch set

Suggested initial landmarks include Victoria Memorial, Howrah Bridge, Prinsep Ghat, College Street, Dakshineswar Temple, Park Street, Eden Gardens, Indian Museum and major railway/metro stations. Verify coordinates, names, descriptions, image rights and category before publication.

## 10. Non-functional requirements

- **Performance:** Load only visible or nearby chunks; establish measurable budgets after prototype profiling.
- **Accessibility:** Keyboard-operable UI controls, visible focus states, meaningful labels and reduced-motion support.
- **Responsive design:** Desktop-first map experience with touch support on mobile.
- **Reliability:** Handle missing chunks, network errors and unavailable metadata gracefully.
- **Privacy:** Do not collect precise user location unless a clear feature requires it and the user grants permission.
- **Maintainability:** Keep renderer, data pipeline, UI and data access separate.

## 11. Success metrics

- Initial map time and time-to-interactive.
- Average frame rate on agreed reference devices.
- Chunk request size and failure rate.
- Search success rate.
- Landmark selection and detail-panel usage.
- Mobile usability and error rates.

Set numeric targets after measuring the first working prototype rather than guessing them.

## 12. Risks and mitigations

| Risk | Mitigation |
|---|---|
| Large map overwhelms browser | Chunking, culling, level of detail and profiling |
| Geographic data is incomplete | Validate source coverage and provide correction workflow |
| Pixel-art production takes too long | Reusable tiles, procedural base geometry and hand-crafted landmark assets |
| Source licensing is misunderstood | Maintain attribution and dataset provenance records |
| Isometric map distorts geography | Preserve source coordinates and document visual transformations |
| Mobile performance is weak | Test early on mid-range devices and offer lower detail |

## 13. Release acceptance criteria

The MVP is ready for public testing when:
- The agreed boundary can be explored without a blank or broken map.
- Pan, zoom, reset and landmark selection work.
- Nearby chunks load and failed requests can recover.
- Search returns only verified indexed places.
- Attribution and privacy information are visible.
- Desktop and mobile smoke tests pass.
