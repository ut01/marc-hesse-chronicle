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
- founding chapter strengthened with dated 2013 release-trail treatment instead of a vague founding claim
- richer founding-proof artifact cards added for the OpenStack and VMware 2013 releases, including direct-quote support in the artifact visual system
- richer chapter-level artifact slots added for the strongest validation chapter items (Dell / Hitachi / IBM / Azure) so the middle years feel archival, not repetitive
- validation wall upgraded from a generic grouped list into a source-backed ecosystem module with dated milestones, editorial notes, and direct links to primary evidence
- artifact system upgraded to support multi-source editorial artifacts and richer chapter treatments for geography + AI-era signal stacks
- new evidence-exhibit layer added between narrative chapters and the archive, grouping the strongest source-backed artifacts into editorial desk-style exhibit cards with chapter/archive jumps and provenance links
- artifact visual system upgraded again with source-backed media decks, so strong chapters can carry richer article-snippet / conference-visual / future-scan slots without resorting to toy placeholder imagery
- source archive and validation arc expanded with additional direct Bloombase primary URLs for 2016 (Ultra Electronics AEP / Keyper HSM interoperability) and 2017 (ATTO interoperability), plus corresponding timeline and exhibit coverage
- explicit reader-mode system added so the chronicle now supports a real skim/deep split instead of merely implying dual reading modes:
  - skim mode keeps thesis, chapter arc, map, validation, and present-direction surfaces visible
  - deep mode opens the exhibit desk, reference timeline, source explorer, roadmap, and public-record layers
  - chapter body copy now trims to the lead paragraph in skim mode while preserving full narrative in deep mode
- new chapter-compass layer added between the sticky phase rail and the long-form narrative so skim/deep mode becomes a real navigation system instead of just a toggle:
  - compact chapter cards now summarize each chapter’s editorial role, evidence density, strongest current anchor, and next upgrade target
  - a dedicated deep-evidence-desk card now offers explicit jumps into exhibits, chronology, and the source archive
  - chapter focus events now light up the matching compass card, making the chapter spine feel like a premium IA surface rather than passive ornament
- preserved-archive evidence layer added from a local capture of Bloombase’s news index:
  - `news-index.html` is now treated as an explicit archival source, not just a repo scrap
  - new `data/archive-captures.json` turns the preserved HTML into a structured chronology-evidence card with coverage stats, notable visible entries, and connected source links
  - the page now renders an archive-capture desk under the primary chronology ledger so readers can audit the release index itself, including the commented-out Huawei 2017 clue preserved in the HTML
  - `data/sources.json` now includes the local preserved capture as a first-class source archive item

## Next implementation steps
1. Strengthen the source archive further by capturing more direct primary URLs for early academic details, especially anything tighter than the current profile-level CUHK / Beckman trail.
2. Populate the AI-era media-deck slots with actual preserved captures or conference visuals once durable public assets are collected, then route them through the same archive-capture system instead of ad-hoc visuals.
3. Deepen the exhibit treatment so the strongest chapters read as grouped comparative narratives, not just richer individual cards.
4. Consider migrating the static prototype into Astro once the content model stabilizes.
