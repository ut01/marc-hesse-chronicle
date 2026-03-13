# Next Steps

## Completed
- New git repo created
- Git author confirmed as Koutian Wu <ktwu01@gmail.com>
- Research dossier created
- Milestone table v1 and v2 created
- Initial timeline / storymap JSON scaffold created
- First landing page prototype created
- SOTA design review added at `research/sota-design-review.md`
- Editorial content schema added:
  - `data/chapters.json`
  - `data/locations.json`
  - `data/validation.json`
  - `data/sources.json`
  - `data/artifacts.json`
- Landing page rebuilt into an editorial chronicle with:
  - premium hero + thesis framing
  - phase rail / quick navigation
  - narrative timeline chapters
  - synced MapLibre geography module
  - curated validation groups
  - denser reference timeline sourced from `data/timeline.json`
  - source archive
  - source-backed editorial artifact cards for the strongest chapters
  - archive timeline sourcing labels + source-origin filters
  - lightweight artifact/media taxonomy via `data/artifact-taxonomy.json`
  - chapter-specific map captions, camera presets, and active route emphasis
  - present-direction / why-now module via `data/present-direction.json`
  - chapter-to-archive crosslinks with supporting milestone clusters and archive return links
  - chapter-aware archive scoping so support clusters open filtered evidence sets in the reference timeline
  - stronger editorial geography navigation cards with chapter tone, evidence counts, and source-backed cues
  - chapter evidence matrix + open source gaps panel so sourcing strength is visible, not implied

## Next implementation steps
1. Strengthen the source archive further by capturing more direct primary URLs for early academic/founding details.
2. Deepen the artifact system with real media slots for conference visuals, article snippets, and future scans only where source quality is strong enough.
3. Add richer chapter-level artifact slots for the strongest early/founding chapters once source quality supports them.
4. Consider migrating the static prototype into Astro once the content model stabilizes.
