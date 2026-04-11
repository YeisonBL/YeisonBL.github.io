---
name: portfolio-nyt-style
description: Apply or extend the New York Times newspaper-style editorial design to pages in the mi-portafolio Quarto site. Use whenever the user asks to style a new page, section, or component in this portfolio, or asks for "newspaper style" / "NYT style" / "editorial" design.
---

# Portfolio — NYT newspaper style

The `mi-portafolio` Quarto site follows a **New York Times / newspaper editorial** aesthetic. When creating or modifying pages in this site, use the conventions and CSS classes already defined in `styles.css`.

## Design principles

- **Typography**: Playfair Display for display/headlines, Source Serif 4 for body and labels, Source Code Pro for tags/pills, UnifrakturCook only for the masthead nameplate.
- **Palette**: near-black `#121212` on off-white, muted gray `#727272` for secondary, single red accent `#D0021B` (NYT masthead red), link blue `#326891`.
- **Layout**: thin rules and generous whitespace over boxes/shadows. Double rules (`3px double`) for section boundaries, single hairlines (`1px solid var(--nyt-rule)`) for inline separators.
- **Imagery**: grayscale or heavy duotone; desaturate on hover rather than adding colored overlays.
- **Editorial hierarchy**: kicker (small-caps eyebrow, red) → headline (Playfair) → byline (small-caps gray) → lede with drop cap → body.
- **Avoid**: gradients, rounded-xl cards, neon accents, drop shadows beyond subtle, emoji UI, SaaS-style hero blocks.

## Available CSS classes (defined in `styles.css`)

### Page-top masthead
```html
<header class="masthead">
  <div class="masthead-top">
    <span class="edition">Vol. I · No. 1</span>
    <span class="date">Saturday, April 11, 2026</span>
    <span class="locale">Bogotá · 18°C</span>
  </div>
  <h1 class="masthead-title">The Yeison Times</h1>
  <div class="masthead-tagline">"All the Data That's Fit to Model"</div>
  <div class="masthead-rule"></div>
</header>
```

### Kicker + headline + byline
```markdown
[Data Science Portfolio]{.kicker}

# Page Headline Here

[By **YEISON BUITRAGO** · Data Scientist at Habi Colombia]{.byline}
```

### Lede with drop cap
Wrap the first paragraph in a `.lede` div. The first letter becomes a Playfair drop cap and the first line renders in small-caps automatically.
```markdown
::: {.lede}
Opening paragraph goes here. First letter drops, first line small-caps.
:::
```

### Pull quote
```html
<blockquote class="pullquote">
  "A single sentence that deserves its own moment on the page."
</blockquote>
```

### Section headings
Just use `## Heading` — `h2` is already styled as a centered, uppercase, double-ruled section label.

### Project grid (editorial two-column, no cards)
```html
<div class="project-grid">
  <div class="project-card">
    <a href="projects/foo.qmd"><img src="assets/foo-preview.svg" alt="Foo preview"/></a>
    <div class="project-card-body">
      <div class="project-tags">
        <span class="tag">Python</span>
      </div>
      <h3>Project Headline</h3>
      <p>One-sentence dek that explains the project.</p>
      <a href="projects/foo.qmd" class="project-link">View project →</a>
    </div>
  </div>
  <!-- second .project-card: automatically separated by a vertical rule -->
</div>
```

### Skills grid
```html
<div class="skills-grid">
  <div class="skill-group">
    <span class="skill-label">Languages</span>
    <span class="skill-pill">Python</span>
  </div>
</div>
```

### Contact strip (footer)
```html
<div class="contact-strip">
  <div class="contact-strip-name">Yeison Buitrago <span>· Data Scientist · Bogotá, Colombia</span></div>
  <div class="contact-strip-links">
    <a href="mailto:...">✉ email</a>
  </div>
</div>
```

## Dark mode

Every class above has overrides under `body.quarto-dark` in `styles.css`. When adding a new class with a hardcoded color, always add its dark-mode counterpart in the same file under the dark-mode section.

## Bilingual content

The site ships two indices: `index.qmd` (EN) and `index-es.qmd` (ES). Whenever content changes on one, mirror it on the other. The navbar in `_quarto.yml` toggles between them.

## Workflow

1. Read `styles.css` first to confirm available classes before introducing new ones.
2. Prefer reusing existing classes over adding new CSS.
3. If new CSS is needed, add it to `styles.css` following the section comments, and always include a dark-mode override.
4. After changes, run `quarto render` from the `mi-portafolio` directory to verify the build.
5. Mirror any content change between `index.qmd` and `index-es.qmd`.
