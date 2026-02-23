# 🎨 Tailwind CSS v4 — Full Course

> **Zero to Expert · 2025 Edition**
> A modern, hands-on course built exclusively for Tailwind CSS v4. No fluff, no outdated docs — just real knowledge that sticks.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Who This Is For](#who-this-is-for)
- [Prerequisites](#prerequisites)
- [How to Use This Course](#how-to-use-this-course)
- [Course Modules](#course-modules)
- [Key Concepts Covered](#key-concepts-covered)
- [What's New in Tailwind v4](#whats-new-in-tailwind-v4)
- [Quick Reference Cheat Sheet](#quick-reference-cheat-sheet)
- [Recommended Tools](#recommended-tools)
- [Resources & Further Learning](#resources--further-learning)
- [FAQ](#faq)

---

## Overview

This is a single-file, fully interactive HTML course covering **Tailwind CSS version 4** from the ground up. It was built because most existing resources — tutorials, PDFs, YouTube series — are outdated and still teach v2/v3 patterns that no longer apply.

Tailwind v4 (released 2025) is a near-complete rewrite of the framework. The configuration system changed, the import syntax changed, new layout primitives were added, and the underlying build engine was replaced with a Rust-based compiler. This course covers all of it.

**Format:** Single `.html` file — open it in any browser, no server needed.
**Progress tracking:** The sidebar marks modules as visited and tracks your completion percentage.
**Quizzes:** Key modules include interactive multiple-choice questions with instant feedback.

---

## Who This Is For

| You are... | This course is... |
|---|---|
| Complete beginner to Tailwind | Perfect starting point |
| Know CSS but new to utility-first | Great — your CSS knowledge transfers directly |
| Experienced with Tailwind v2/v3 | Essential — v4 has breaking changes you need to know |
| Coming from Bootstrap or another framework | Ideal — covers the philosophy shift clearly |

---

## Prerequisites

You don't need much. Before starting, you should be comfortable with:

- **Basic HTML** — knowing what elements, attributes, and classes are
- **Basic CSS** — understanding what `padding`, `margin`, `color`, and `display` mean (you don't need to be an expert)

That's it. You do **not** need to know JavaScript, React, or any build tools to start. Those are introduced gradually in context.

---

## How to Use This Course

### Opening the Course

```bash
# Just open the file in your browser
open tailwind-v4-course.html

# Or on Windows
start tailwind-v4-course.html
```

No installation, no npm, no server required. It's a self-contained HTML file.

### Recommended Workflow

1. **Read each module in order** — they build on each other
2. **Type out the code examples** — don't copy-paste; muscle memory matters
3. **Answer the quizzes** — they reinforce the concepts before you move on
4. **Build something small** after every 2–3 modules using what you've learned
5. **Revisit modules** freely using the sidebar — nothing is locked

### Study Tips

- Pair this course with the [Tailwind Play](https://play.tailwindcss.com) sandbox — paste code examples there and experiment live
- Install the **Tailwind CSS IntelliSense** VS Code extension before you start (covered in Module 01)
- Don't try to memorise every class — learn the *patterns*, use autocomplete for the rest

---

## Course Modules

### 🟣 Getting Started

#### Module 00 — Introduction
*Estimated time: 10 minutes*

Covers what Tailwind CSS is, the utility-first philosophy, and why it's different from traditional CSS frameworks. Introduces the full course structure with a visual table of contents.

**You will learn:**
- What "utility-first" means and why it exists
- How Tailwind compares to writing custom CSS
- Why Tailwind v4 is a fundamentally different product from v3
- How to navigate and use this course

---

#### Module 01 — Setup & Installation
*Estimated time: 15 minutes*

Three different ways to get Tailwind v4 running, from zero-install CDN to a production Vite project.

**You will learn:**
- Installing Tailwind v4 with **Vite** (recommended for new projects)
- Using the **Play CDN** for instant experimentation
- Setting up Tailwind in a **React / Next.js** project
- Verifying your setup works
- Installing and using the VS Code IntelliSense extension

**Key code:**
```css
/* The only import you need in v4 */
@import "tailwindcss";
```

```js
// vite.config.js
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [tailwindcss()]
})
```

> **Quiz included** ✓

---

#### Module 02 — Core Concepts
*Estimated time: 20 minutes*

The most important module. Understanding how Tailwind thinks is what makes everything else click.

**You will learn:**
- The utility-first mental model (HTML vs CSS co-location)
- The **4px spacing scale** — the foundation of all layout in Tailwind
- **Arbitrary values** — escape the scale when you need exact values
- How the build process works (scan → generate → output)
- Class naming patterns so you can guess classes you haven't memorised

**The spacing scale:**
| Class | rem | px |
|---|---|---|
| `p-1` | 0.25rem | 4px |
| `p-2` | 0.5rem | 8px |
| `p-4` | 1rem | 16px |
| `p-6` | 1.5rem | 24px |
| `p-8` | 2rem | 32px |
| `p-12` | 3rem | 48px |

> **Quiz included** ✓

---

### 🔵 Fundamentals

#### Module 03 — Layout & Spacing
*Estimated time: 25 minutes*

The bread and butter of building any page: how things are sized and spaced.

**You will learn:**
- The `container` class and centering with `mx-auto`
- All padding and margin utilities (`p`, `px`, `py`, `pt`, `pb`, `pl`, `pr`)
- Logical properties (`ps`, `pe`) for RTL/LTR support
- Width and height utilities (fixed, percentage, viewport, min/max)
- Display utilities (`block`, `flex`, `grid`, `hidden`, `inline-flex`)
- A complete real-world profile card example

---

#### Module 04 — Typography
*Estimated time: 20 minutes*

Making text look exactly right is a core Tailwind skill.

**You will learn:**
- The full font-size scale (`text-xs` → `text-9xl`)
- Font weight classes (`font-thin` → `font-black`)
- Line height (`leading-none` → `leading-loose`)
- Letter spacing (`tracking-tight` → `tracking-widest`)
- Text alignment, truncation, and `line-clamp`
- **How to use custom Google Fonts in v4** using `@theme`

**Custom fonts in v4:**
```css
@import "tailwindcss";

@theme {
  --font-sans: 'Inter', sans-serif;
  --font-display: 'Playfair Display', serif;
}
```
```html
<h1 class="font-display text-5xl font-black">Hero Title</h1>
```

---

#### Module 05 — Colors & Backgrounds
*Estimated time: 20 minutes*

Tailwind's colour system is one of its most polished features.

**You will learn:**
- The built-in palette: 22 colours × 11 shades (50–950)
- Text, background, and border colour utilities
- The **opacity modifier** syntax (`bg-blue-500/20`, `text-white/60`)
- Defining **custom brand colours** in `@theme`
- Building gradients with `bg-gradient-to-*`, `from-`, `via-`, `to-`
- The gradient text technique using `bg-clip-text text-transparent`

---

### 🟢 Intermediate

#### Module 06 — Flexbox & Grid
*Estimated time: 30 minutes*

The two layout systems that power 95% of real-world UI.

**You will learn:**
- Flexbox: `flex`, `flex-col`, `flex-wrap`, and `gap`
- `justify-content` — all 6 values
- `align-items` and `align-self`
- CSS Grid: `grid`, `grid-cols-{n}`, `col-span-{n}`
- The auto-fill responsive grid pattern (no breakpoints needed!)
- Classic sidebar layout with `grid-cols-[250px_1fr]`
- When to use Flex vs Grid (a clear mental model)

**Most useful patterns:**
```html
<!-- Navbar -->
<nav class="flex items-center justify-between px-6 py-4">

<!-- Responsive card grid -->
<div class="grid grid-cols-[repeat(auto-fill,minmax(240px,1fr))] gap-6">

<!-- Sidebar layout -->
<div class="grid grid-cols-[250px_1fr] min-h-screen">
```

---

#### Module 07 — Responsive Design
*Estimated time: 25 minutes*

Tailwind's responsive system is mobile-first and uses a prefix pattern that's easy to learn.

**You will learn:**
- The mobile-first mental model (no prefix = all screens)
- All 5 default breakpoints (`sm`, `md`, `lg`, `xl`, `2xl`)
- Common responsive patterns: stacking, showing/hiding, responsive grids
- The single most common mistake beginners make with breakpoints
- Adding custom breakpoints in v4 using `@theme`
- **Container Queries** — a v4 built-in feature for component-level responsiveness

**Breakpoints:**
| Prefix | Min-Width | Target |
|---|---|---|
| *(none)* | 0px | All screens — start here |
| `sm:` | 640px | Landscape phones / small tablets |
| `md:` | 768px | Tablets |
| `lg:` | 1024px | Laptops |
| `xl:` | 1280px | Desktops |
| `2xl:` | 1536px | Large monitors |

> **Quiz included** ✓

---

#### Module 08 — States & Variants
*Estimated time: 30 minutes*

Where Tailwind gets really powerful — interactivity without a single line of custom CSS.

**You will learn:**
- Pseudo-class variants: `hover:`, `focus:`, `active:`, `disabled:`
- Dark mode with `dark:` (OS preference and class-toggle methods)
- The `group` pattern — style children when a parent is hovered
- The `peer` pattern — style siblings based on input state
- Transitions: `transition-*`, `duration-*`, `ease-*`
- Built-in animations: `animate-spin`, `animate-pulse`, `animate-bounce`

**The group pattern:**
```html
<div class="group relative">
  <img src="..." />
  <div class="opacity-0 group-hover:opacity-100 transition-opacity ...">
    Overlay appears on hover
  </div>
</div>
```

---

### 🟡 Advanced

#### Module 09 — Tailwind v4 New Features
*Estimated time: 35 minutes*

Everything that is brand new or fundamentally changed in v4. Required reading if you've used any previous version.

**You will learn:**
- The new Rust-based build engine (Lightning CSS) and why it matters
- `@theme` — CSS-first configuration replacing `tailwind.config.js`
- `@layer components` and `@layer utilities` — creating reusable classes
- The `@apply` directive for composing utilities in CSS
- New **3D transform utilities** (`rotate-x-*`, `rotate-y-*`, `perspective-*`)
- The `starting:` variant for CSS entry animations (no JS needed)
- The official v3 → v4 migration guide and upgrade tool

> **Quiz included** ✓

---

## Key Concepts Covered

### The Utility-First Philosophy
Instead of writing `.card { padding: 24px; }` in a separate CSS file, you write `class="p-6"` directly in HTML. Every class does one thing. You compose them to build any design. The result: you almost never write a CSS file again.

### The 4px Base Scale
Every spacing-related utility (padding, margin, gap, width, height) uses a scale where 1 unit = 4px. `p-4` = 16px. `p-8` = 32px. Learn this scale once and it applies everywhere.

### Arbitrary Values
When the default scale isn't enough, use square brackets: `w-[372px]`, `bg-[#1a1a2e]`, `grid-cols-[250px_1fr]`. This gives you the full power of CSS inside Tailwind classes.

### Responsive Prefixes
Add a breakpoint prefix to any class to make it conditional: `md:flex-row` means "apply `flex-row` on medium screens and up". No prefix = applies everywhere.

### State Variants
Prefix any class with a state to make it conditional: `hover:bg-blue-700`, `focus:ring-2`, `dark:text-white`. Stack them: `md:hover:scale-105`.

---

## What's New in Tailwind v4

This table is essential if you've used Tailwind before:

| Feature | v3 | v4 |
|---|---|---|
| Import syntax | `@tailwind base; @tailwind utilities;` | `@import "tailwindcss";` |
| Configuration | `tailwind.config.js` | `@theme {}` block in CSS |
| Content detection | Manual `content: [...]` array | Automatic — zero config |
| Custom colors | `theme.extend.colors` in JS | `--color-x: value` in `@theme` |
| Custom fonts | `theme.extend.fontFamily` in JS | `--font-x: value` in `@theme` |
| Opacity syntax | `bg-opacity-50` class | `bg-black/50` slash modifier |
| Container queries | Separate plugin required | Built-in, use `@container` |
| 3D transforms | Not included | Built-in |
| Entry animations | Not included | `starting:` variant |
| Build engine | Node.js (PostCSS) | Rust / Lightning CSS (~10x faster) |
| Dark mode config | Config file | `@variant dark` in CSS |

### Migration from v3

Run the official upgrade tool — it handles most changes automatically:

```bash
npx @tailwindcss/upgrade
```

---

## Quick Reference Cheat Sheet

### Spacing
```
p-{n}   px-{n}   py-{n}   pt-{n}   pr-{n}   pb-{n}   pl-{n}
m-{n}   mx-auto  my-{n}   mt-{n}   mr-{n}   mb-{n}   ml-{n}
gap-{n}
```

### Sizing
```
w-full  w-1/2  w-1/3  w-screen  w-[372px]
h-full  h-screen  h-dvh  h-[240px]
max-w-sm  max-w-md  max-w-lg  max-w-xl  max-w-2xl  max-w-prose
```

### Typography
```
text-xs  text-sm  text-base  text-lg  text-xl  text-2xl  text-4xl  text-6xl
font-thin  font-light  font-normal  font-medium  font-semibold  font-bold  font-black
leading-none  leading-tight  leading-normal  leading-relaxed  leading-loose
tracking-tight  tracking-normal  tracking-wide  tracking-widest
text-left  text-center  text-right  truncate  line-clamp-{n}
```

### Colors
```
text-{color}-{shade}      e.g. text-blue-600
bg-{color}-{shade}        e.g. bg-indigo-500
border-{color}-{shade}    e.g. border-gray-200
bg-{color}-{shade}/{opacity}  e.g. bg-blue-500/20
```

### Layout
```
flex  flex-col  flex-row  flex-wrap  inline-flex
items-start  items-center  items-end  items-stretch
justify-start  justify-center  justify-end  justify-between  justify-around
grid  grid-cols-{n}  col-span-{n}  gap-{n}
block  inline-block  hidden
```

### Responsive
```
sm:{class}  md:{class}  lg:{class}  xl:{class}  2xl:{class}
```

### States
```
hover:{class}  focus:{class}  active:{class}  disabled:{class}
dark:{class}
group  group-hover:{class}
peer  peer-focus:{class}
```

### Transitions
```
transition  transition-all  transition-colors  transition-opacity  transition-transform
duration-75  duration-150  duration-200  duration-300  duration-500
ease-in  ease-out  ease-in-out
```

### v4 Theme
```css
@theme {
  --color-brand: #7c6aff;
  --font-display: 'Syne', sans-serif;
  --breakpoint-xs: 480px;
  --spacing-18: 4.5rem;
}
```

---

## Recommended Tools

| Tool | Purpose | Link |
|---|---|---|
| **Tailwind CSS IntelliSense** | VS Code autocomplete, hover previews, linting | [Marketplace](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) |
| **Tailwind Play** | In-browser sandbox — no install needed | [play.tailwindcss.com](https://play.tailwindcss.com) |
| **Prettier Tailwind Plugin** | Auto-sorts class names in a consistent order | [npm](https://github.com/tailwindlabs/prettier-plugin-tailwindcss) |
| **Tailwind UI** | Official component library (paid) | [tailwindui.com](https://tailwindui.com) |
| **shadcn/ui** | Free, beautifully designed React components | [ui.shadcn.com](https://ui.shadcn.com) |
| **Headless UI** | Unstyled accessible components from the Tailwind team | [headlessui.com](https://headlessui.com) |

---

## Resources & Further Learning

### Official
- [Tailwind CSS Documentation](https://tailwindcss.com/docs) — always the source of truth
- [Tailwind CSS Blog](https://tailwindcss.com/blog) — release notes and deep-dives
- [Tailwind CSS GitHub](https://github.com/tailwindlabs/tailwindcss) — source code, issues

### Practice
- [Tailwind Play](https://play.tailwindcss.com) — official sandbox
- [Frontend Mentor](https://www.frontendmentor.io) — real design challenges to build with Tailwind
- Build your own: portfolio site, landing page, dashboard — anything real beats tutorials

### Community
- [Tailwind CSS Discord](https://discord.gg/tailwindcss) — official community
- [r/tailwindcss](https://reddit.com/r/tailwindcss) — subreddit

---

## FAQ

**Q: Do I need to know CSS before learning Tailwind?**
A: Basic CSS knowledge helps — you should know what `padding`, `margin`, `color`, and `display` mean. You don't need to be a CSS expert; Tailwind often makes CSS easier to learn because the class names describe the property they set.

**Q: Is Tailwind v4 backwards compatible with v3?**
A: Not fully. There are breaking changes — the import syntax, configuration system, and some class names changed. Run `npx @tailwindcss/upgrade` to automatically migrate a v3 project. Module 09 covers a full comparison table.

**Q: I keep forgetting class names. Is that normal?**
A: Completely normal and expected. Install the VS Code IntelliSense extension and use autocomplete. After a few weeks of building things, the most common classes become second nature. You'll never memorise every class — that's what the docs and autocomplete are for.

**Q: Should I use Tailwind or write regular CSS?**
A: For most projects, Tailwind. You'll ship faster, maintain more easily, and keep consistent spacing/colour. That said, Tailwind and CSS aren't mutually exclusive — you can always drop into regular CSS using `@layer` when needed.

**Q: Does Tailwind work with React / Vue / Svelte?**
A: Yes, all of them. Tailwind is framework-agnostic — it just processes class names in your templates. Module 01 covers React/Next.js setup specifically.

**Q: Will Tailwind generate huge CSS files?**
A: No. One of Tailwind's core features is that it only generates CSS for the classes you actually use. A typical production stylesheet is 5–20KB, regardless of how many Tailwind utilities exist.

**Q: What's the difference between `hidden` and `invisible`?**
A: `hidden` sets `display: none` — the element is removed from layout flow completely. `invisible` sets `visibility: hidden` — the element is transparent but still takes up space.

**Q: Can I use Tailwind and a component library together?**
A: Yes. shadcn/ui and Headless UI are designed specifically to be used with Tailwind. Tailwind UI is the official paid component library.

---

## File Structure

```
tailwind-v4-course/
│
├── README.md                    ← You are here
└── tailwind-v4-course.html      ← The complete course (open in any browser)
```

The course is intentionally a single self-contained file. There are no dependencies, no build step, and no internet connection required after download.

---

## License

This course material is free to use for personal learning. Please don't redistribute it commercially without permission.

---

*Built in 2025 for Tailwind CSS v4. Last verified against Tailwind CSS v4.0.*