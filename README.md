# OCN 623 – Chemical Oceanography course website

Built with [Quarto](https://quarto.org/). No R or Python needed.

## Preview while editing

```bash
quarto preview
```

This opens the site in a browser and reloads it every time you save a file.
(In VS Code, the Quarto extension adds a "Preview" button that does the same.)

## Publish

```bash
quarto render
```

This writes the finished site to `docs/`. Commit and push, including `docs/`.
GitHub Pages setting: **Settings → Pages → Deploy from a branch → `main` / `docs`**.

## Where things are

| File | What it is |
|---|---|
| `_quarto.yml` | Site settings: title, navbar menu, theme |
| `index.qmd` | Home page: syllabus and schedule |
| `01-…qmd` to `05-…qmd` | One page per course section |
| `problem-sets.qmd`, `handouts.qmd` | PDF pages |
| `styles.css` | Small CSS tweaks (PDF embed size) |
| `assets/pdfs/`, `assets/images/` | Slides, handouts, figures |

## Common edits

**Add lecture slides:** put the PDF in `assets/pdfs/` (no spaces in the file name), then paste into the page:

```markdown
<embed class="pdf-embed" src="assets/pdfs/MY_FILE.pdf" type="application/pdf">

[Download PDF](assets/pdfs/MY_FILE.pdf){.pdf-link}
```

**Add a YouTube recording:**

```markdown
{{< video https://www.youtube.com/watch?v=VIDEO_ID >}}
```

**Boxed note / sidebar:**

```markdown
::: {.callout-note title="Sidebar title"}
Text here.
:::
```

Other types: `callout-tip`, `callout-important`, `callout-warning`. Add `appearance="minimal"` for a plain box with no title (used for the boxed equations).

**Math:** inline `$O_2$`, display `$$ ... $$` on its own line. Don't use `$$` inline. Quarto treats it as a centered display equation.

**Add a page to the menu:** add the `.qmd` file name under `navbar` in `_quarto.yml`.
