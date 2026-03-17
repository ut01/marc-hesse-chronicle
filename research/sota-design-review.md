# Eric C. Greene Chronicle — SOTA Design Review

Goal: build a premium research-chronicle page by borrowing proven patterns from open-source timeline, map-story, and editorial storytelling systems instead of inventing a bespoke interaction model too early.

## 1) Top 5 open-source references

### 1. TimelineJS3
- Repo: https://github.com/NUKnightLab/TimelineJS3
- Demo: https://timeline.knightlab.com/
- Why it matters:
  - Best-known open-source editorial timeline pattern.
  - Strong slide-by-slide chronology with date precision, media support, and narrative pacing.
  - Good reminder that the timeline should be story-first, not just a dense data table.

### 2. StoryMapJS
- Repo: https://github.com/NUKnightLab/StoryMapJS
- Demo: https://storymap.knightlab.com/
- Why it matters:
  - Canonical open-source "map + narrative card" reference.
  - Useful for the research-journey / geography layer: place, caption, image, transition.
  - Especially relevant because Eric's biography has clear location chapters (Texas → Maryland → New York).

### 3. Odyssey.js
- Repo: https://github.com/CartoDB/odyssey.js
- Demo: https://cartodb.github.io/odyssey.js/
- Why it matters:
  - Strong precedent for scroll-driven map storytelling.
  - More editorial than StoryMapJS: narrative blocks can drive map state, not just simple slides.
  - Helpful pattern for tying chronology and geography into a single reading flow.

### 4. vis-timeline
- Repo: https://github.com/visjs/vis-timeline
- Demo: https://visjs.github.io/vis-timeline/examples/timeline/
- Why it matters:
  - Not as editorial out of the box, but excellent for dense professional timelines.
  - Strong zooming, grouped items, ranges, and interaction model.
  - Useful when the page needs a second, more "reference-grade" timeline view beyond the hero narrative.

### 5. Pageflow
- Repo: https://github.com/codevise/pageflow
- Why it matters:
  - Open-source multimedia storytelling system with a more museum / magazine sensibility.
  - Valuable less for direct adoption and more for structure: chaptering, full-bleed media, pacing, transitions, and premium editorial framing.
  - Good reminder that the site should feel like a curated exhibition, not a generic academic CV with a timeline bolted on.

## 2) What we should directly adopt vs avoid

### Directly adopt
- From TimelineJS3:
  - One clear chronological spine.
  - Each milestone as a self-contained story card with headline, date, short narrative, and optional media.
  - Horizontal/sectional pacing principle: one important beat at a time.

- From StoryMapJS:
  - A chaptered geography layer.
  - One location per research phase, with concise explanatory copy.
  - Camera transitions that move only when the story changes.

- From Odyssey.js:
  - Scroll or chapter progression driving map/timeline state.
  - Sticky visual pane + narrative pane layout.
  - Treat map movement as narrative punctuation, not constant motion.

- From vis-timeline:
  - Secondary "archive/reference" mode for power users.
  - Grouping milestones into phases: Formation, Doctoral, Postdoc, Faculty, Innovations, Publications.
  - Range bars for long eras, points for pivotal moments.

- From Pageflow:
  - Full-bleed chapter breaks.
  - Strong rhythm: intro -> formation -> doctoral -> postdoc -> faculty -> innovations -> present.
  - High production-value feeling through spacing, restraint, and media hierarchy.

### Avoid
- Do not ship raw TimelineJS3 or StoryMapJS embeds as the main experience.
  - They are useful references, but the default styling feels educational / newsroom / template-like, not premium-research-editorial.
- Do not over-animate the map.
  - Constant camera movement makes biography pages feel gimmicky.
- Do not make every publication a milestone.
  - Too many papers turns the story into a CV dump.
- Do not force users into a single giant scrollytelling path with no quick navigation.
  - Research pages also need a skimmable mode.
- Do not use glossy "toy" sci-fi styling without evidence.
  - The final version should feel more archival, elegant, and source-backed.

## 3) Recommended information architecture for the Eric C. Greene page

### A. Hero / thesis
- Name, one-sentence thesis, portrait or restrained abstract visual.
- Short framing line: doctoral biochemistry training -> NIH postdoc -> Columbia professor -> single-molecule imaging pioneer.
- 3-5 proof chips only, not 10+.

### B. At-a-glance chronology
- Compact horizontal phase rail:
  - Early formation
  - Texas A&M / PhD
  - NIH / Postdoc
  - Columbia faculty
  - DNA curtains innovation
  - CRISPR research
  - Current research
- Clicking a phase jumps to that chapter.

### C. Main narrative chapters
Each chapter should have:
- date / time range
- chapter title
- 120-220 words of narrative
- 1-3 key proof points
- optional image / diagram / publication link

Recommended chapters:
1. Early academic formation
2. Doctoral research (Texas A&M, telomere biology)
3. NIH postdoctoral training
4. Columbia faculty appointment
5. DNA curtains innovation
6. CRISPR-Cas9 research
7. RAD51 and genome stability
8. Present direction / cancer biology connections

### D. Geography module
- A separate but integrated map section.
- 3 key place markers only.
- Each place corresponds to a chapter, not every event.
- Map should answer: how did the research journey move across institutions?

### E. Validation / research impact section
- Curated institutional affiliations and research metrics.
- Better structure than a raw publication list:
  - Academic institutions
  - Technical innovations
  - High-impact publications
  - Research citations
- Keep it evidence-driven and selective.

### F. Archive / sources
- Expandable source list or evidence drawer.
- This is what upgrades the page from tribute-style to museum/editorial credibility.

## 4) Visual / UX principles to make it feel premium, not toy

- Favor editorial elegance over academic-dashboard gloss.
  - More off-white, charcoal, muted blue/green accents.
  - Less neon, fewer decorative orbit effects.
- Build around typography first.
  - Premium biography pages feel expensive because the text hierarchy is calm and deliberate.
- Use motion sparingly.
  - Fade, parallax, and camera transitions only at chapter boundaries.
- Give milestones breathing room.
  - Fewer cards, more substance per card.
- Distinguish "major chapter" vs "minor proof point."
  - Not everything deserves equal visual weight.
- Use maps as orientation, not spectacle.
  - Clean basemap, limited markers, subtle routes.
- Prefer real artifacts over abstract decoration.
  - Publication figures, technique diagrams, microscopy images, citations.
- Maintain dual reading modes:
  - skim mode for busy visitors
  - deep mode for readers who want the full chronology
- Make source credibility visible.
  - Small citations and outbound references create trust fast.

## 5) Exact build recommendation: what stack to use now

## Recommendation
Build this now as a lightweight custom site, not as an iframe composition of third-party tools.

### Stack
- Framework: Astro
- UI islands: React (only where interaction is needed)
- Styling: Tailwind CSS or plain CSS modules (either is fine; Tailwind is faster if the team wants speed)
- Map: MapLibre GL JS
- Scroll/chapter behavior: custom lightweight intersection-observer logic inspired by Odyssey.js / editorial scrollytelling patterns
- Timeline rendering:
  - custom chapter timeline for the main narrative
  - optional vis-timeline secondary view for "full chronology / archive" mode
- Content source: structured JSON or YAML in-repo for milestones, chapters, locations, publications, and sources
- Deployment: static build on GitHub Pages / Vercel / Netlify

### Why this stack now
- Astro keeps the site mostly static, fast, and easy to ship.
- React islands let us add only the interactive map/timeline pieces.
- MapLibre avoids lock-in and is enough for a polished biography map.
- A custom narrative timeline will look far better than raw TimelineJS styling.
- vis-timeline can be added later only if a dense reference view becomes necessary.

### Recommended implementation pattern
1. Define a clean content schema first:
   - chapters.json
   - locations.json
   - timeline-events.json
   - sources.json
2. Build the page as 5-8 curated chapters, not dozens of equal cards.
3. Sync chapter scroll state with the map.
4. Add a compact phase rail for jumping.
5. Add an archive drawer / sources panel last.

## Bottom line
The right move is: borrow the information architecture of TimelineJS3 + StoryMapJS + Odyssey.js, but implement a custom editorial surface. That gives us proven storytelling structure without inheriting the dated visual language of off-the-shelf embeds.
