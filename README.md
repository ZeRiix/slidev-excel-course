# Slidev Template - Programming Course

Modular boilerplate for building an interactive programming course with Slidev and the Neversink theme.

## Structure

- `slides.md` contains only the global configuration and page imports.
- `pages/` contains replaceable slide examples. Files use camelCase and describe the slide content.
- `layouts/` contains reusable templates: `coverLayout`, `summaryLayout`, `sectionTransitionLayout`, `theoryContentLayout`, `staticCodeExampleLayout`, `liveMonacoLayout`, `exerciseLayout`, `qrLinkLayout`, `correctionLayout`, `conclusionLayout`.
- `components/` contains small reusable components for pages, also named in camelCase.
- `composables/useFrontmatter.ts` exposes typed access to Slidev frontmatter to avoid using `$frontmatter` as `any` in layouts.
- `global-bottom.vue` adds keyboard scrolling for long slides.
- `style.css` centralizes the white / black / gray / yellow visual direction.
- `public/assets/` contains temporary images to replace.
- `examples/` can contain code examples to import in Shiki blocks, for example `<<< ../examples/demo.ts ts {} twoslash`.

## Presenter Notes

Add trainer notes at the end of a slide with an HTML comment. They appear in presenter mode, not on the projected slide.

```md
# Slide title

Visible content.

<!--
Trainer notes.
- Point to mention aloud.
- Question to ask the group.
-->
```

To synchronize notes with clicks, add `[click]` markers in the comment:

```md
<!--
Introduction before the first click.

[click] Note displayed on the first click.

[click:3] Note associated with the third click.
-->
```
