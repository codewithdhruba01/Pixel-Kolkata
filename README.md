# Pixel Kolkata

**Explore the City. One Pixel at a Time.**

Pixel Kolkata is a web-based city exploration experience that represents Kolkata and its surrounding selected urban areas as an interactive isometric pixel-art world.

## Documentation

- [Product Requirements (PRD)](docs/PRD.md)
- [System Architecture](docs/architecture.md)
- [Visual Design Guidelines](docs/design.md)
- [Geographic Data Pipeline](docs/data-pipeline.md)
- [Development Roadmap](docs/roadmap.md)
- [Contribution Guidelines](CONTRIBUTING.md)

## Proposed technology stack

- Next.js App Router, React and TypeScript
- PixiJS for the interactive isometric renderer
- Tailwind CSS for application UI
- Python geospatial tooling for source-data processing
- GeoJSON for interchange and spatial features
- Supabase PostgreSQL with PostGIS for location metadata and spatial queries
- Cloudflare R2 or equivalent object storage for static map assets
- Vercel or another compatible platform for application hosting

## Project status

Planning and prototype stage. The geographic boundary, source datasets, art pipeline, performance targets and production hosting choices must be validated during implementation.

## Getting started

```bash
npx create-next-app@latest pixel-kolkata
cd pixel-kolkata
npm install pixi.js lucide-react zustand
npm run dev
```

Choose TypeScript, ESLint, Tailwind CSS, App Router, `src/` directory and the `@/*` import alias.

## Important scope note

“Whole Kolkata” must be defined as a documented geographic boundary before data processing. The initial target can include Kolkata, Howrah, Bidhannagar/Salt Lake and New Town/Rajarhat, with the wider metropolitan area treated as an explicitly versioned expansion. Do not imply that every building is hand-illustrated in the first release.
