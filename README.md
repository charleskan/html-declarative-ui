# html-declarative-ui

Write UI like Flutter / SwiftUI — directly in HTML. No build step, no runtime, just HTML and CSS.

---

## Example

```html
<div class="vstack padding"
     style="
       --gap:16px;
       --padding-horizontal:clamp(16px,6vw,120px);
     ">

  <h2 class="text">Overview</h2>

  <div class="hstack" style="--gap:24px; --justify:center;">
    <img src="icon-a.svg" alt="" />
    <img src="icon-b.svg" alt="" />
    <img src="icon-c.svg" alt="" />
  </div>

  <p class="text">
    Complete the required steps to enter the lucky draw.
  </p>

</div>
```

If this HTML already feels clear and readable, this project may be a good fit. If you prefer utility-heavy class lists or component abstractions, this is probably not what you are looking for.

---

## What you are looking at

html-declarative-ui is a small declarative UI language on top of plain HTML and CSS. It describes UI structure by composing a tiny set of primitives (`vstack`, `hstack`, `padding`, `text`, …) and configuring them with CSS variables.

There is no JavaScript runtime, no component system, no build step. This is a language layer, not a framework.

---

## Why this exists

Writing HTML + CSS at scale is hard because layout, spacing, and responsiveness leak everywhere:

- CSS selectors become tightly coupled to DOM structure.
- Spacing rules leak across components.
- Responsive behavior is scattered and inconsistent.
- HTML stops describing UI and starts describing CSS output.

Many solutions add more machinery (frameworks, runtimes, large utility systems). html-declarative-ui treats HTML itself as a UI description language instead.

---

## Why not Tailwind?

Tailwind optimizes for speed by encoding visual decisions into class names:

```html
<div class="flex flex-col gap-4 px-8 py-6 bg-green-600 text-white">
```

This works, but the HTML now describes styling output, not UI structure.

With html-declarative-ui, the same intent looks like this:

```html
<div class="vstack padding"
     style="--gap:16px; --padding-horizontal:32px;">
  <h2 class="text">Title</h2>
  <p class="text">Description</p>
</div>
```

- Structure remains structural.
- Layout remains behavioral.
- Design decisions remain configurable.
- HTML remains readable as a UI tree.

This project deliberately avoids value-based utility classes, encoding design tokens into class names, and flattening UI intent into styling shortcuts.

---

## Why not a framework?

Frameworks are powerful when you can afford them. Many real-world projects cannot (legacy codebases, server-rendered HTML, CMS-driven markup, partial refactors, tight integration constraints).

html-declarative-ui works with existing HTML, not instead of it. You can adopt it incrementally—one section or one page at a time—without rewriting your app.

---

## What this is (and is not)

**This is:**
- a small set of UI primitives
- a declarative layout model
- predictable, composable behavior
- a thin language layer over HTML

**This is not:**
- a component library
- a design system
- a utility-first CSS framework
- a replacement for React / Vue / Svelte

---

## Design philosophy

- HTML expresses structure.
- Primitives express behavior.
- CSS variables express configuration.
- Nesting expresses composition.
- Media queries express policy.

If it feels like “writing widgets in HTML”, that is intentional.

---

## Status

This project is intentionally small. It aims to be understandable in one file, stable over time, difficult to misuse, and easy to remove if needed. If future changes make the examples harder to read, the change is wrong.
