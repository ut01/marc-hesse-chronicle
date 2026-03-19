# Contributing

Thanks for helping improve this animated chronicle template.
This project is primarily a static web template (HTML, JSON, Markdown, and light JavaScript integrations), so correctness of content and data structure matters more than framework conventions.

## What contributions are most useful

- New subject conversions (replace one person's content with another while preserving layout and behavior)
- Data quality fixes in timeline/map/artifact JSON files
- Rendering and interaction bug fixes (TimelineJS, StoryMapJS, chapter navigation)
- Documentation improvements that make repeat conversions easier

## Ground rules

1. Keep the existing design and structure intact unless the change is explicitly about design.
2. Do not break existing data schemas used by the page scripts.
3. Prefer small, reviewable pull requests over large mixed changes.
4. Keep personal/sensitive information out of commits.

## Local development

Run the site locally:

```bash
python -m http.server 8000
```

Open `http://localhost:8000`.

## Recommended workflow

1. Create a branch from `main`.
   - Suggested names:
     - `content/<subject-name>`
     - `fix/<area>`
     - `docs/<topic>`
2. Read the files you will change before editing.
3. Make focused edits.
4. Verify behavior in browser.
5. Open a PR with a clear description and screenshots when UI behavior changes.

## Required checks for content conversion PRs

If your PR updates the subject/person content, check all of the following:

- `index.html` and `news-index.html` no longer contain old subject-specific text.
- All relevant files in `data/` are updated and valid JSON.
- All relevant files in `research/` are updated.
- Timeline events render correctly.
- Map markers move to the expected locations when chapters are clicked.
- Chapter navigation remains functional.
- No obvious layout regressions (especially banner/chapter overlap with longer chapter lists).

## Pull request checklist

Include this checklist in your PR description:

- [ ] Scope is clear and limited (content, fix, or docs)
- [ ] I reviewed all touched files for consistency
- [ ] I tested locally at `http://localhost:8000`
- [ ] Timeline renders correctly
- [ ] Story map behavior is correct per chapter
- [ ] No schema-breaking changes in `data/` files
- [ ] README/CONTRIBUTING docs are updated if workflow changed

## Style and commit guidance

- Keep edits simple and explicit.
- Match existing naming and formatting in JSON/Markdown/HTML.
- Use commit messages that describe intent, for example:
  - `Update chronicle content for <subject>`
  - `Fix map chapter location transitions`
  - `Clarify conversion workflow in CONTRIBUTING`

## Questions and issue reports

When filing an issue or asking for review help, include:

- What you expected to happen
- What actually happened
- File(s) changed
- Browser and OS
- Screenshot or short repro steps
