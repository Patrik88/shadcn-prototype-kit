# Shadcn Prototype Kit

A versatile, multi-framework prototyping sandbox built with Astro, Tailwind CSS, and Shadcn UI.  
Designed for rapid UI layout iterations using Basecoat UI for vanilla HTML, with optional React and Svelte support via Shadcn component stubs.  
Ideal for developers seeking a streamlined, flexible environment to prototype, experiment, and scale UI concepts quickly.
  
---

## Core Default: Basecoat UI + Tailwind CSS

By default, this Starter Kit uses Basecoat UI, a lightweight vanilla HTML + Tailwind CSS library built on the same design principles and styling tokens as Shadcn UI, enabling rapid prototyping without any framework overhead.

- Basecoat uses **Tailwind CSS** for styling and includes prebuilt utility classes like `btn`, `card`, `input`, etc.  
- It requires you to install Tailwind CSS in your project following [Tailwind’s official instructions](https://tailwindcss.com/docs/installation/framework-guides/astro).  
- Basecoat’s CSS is included by installing the npm package and importing in your CSS:  

  ```css
  @import "tailwindcss";
  @import "basecoat-css";
  ```

- Some Basecoat components with JavaScript behavior (e.g., Select, Dialog, Accordion) need Alpine.js or custom scripts. The docs provide Alpine.js snippets you can copy or use via the Basecoat CLI.  
- This approach lets you prototype **fast** with plain HTML and minimal tooling.

---

## Getting Started

```bash
npm install
npm run dev
```

Runs a local dev server at [http://localhost:4321](http://localhost:4321).

---

## Where to Prototype

- **HTML prototypes (default):** `src/pages/html/`  
  Write plain HTML files using Basecoat classes.

- **React stubs:** `src/pages/react/`  
  Create `.jsx` or `.tsx` files; import React components from `src/components/ui/`.  
  (Run `npm run setup:react` to enable React + Shadcn UI support.)

- **Svelte stubs:** `src/pages/svelte/`  
  Create `.svelte` files; import components from `src/components/ui/`.  
  (Run `npm run setup:svelte` to enable Svelte + Shadcn Svelte support.)

---

## Adding or Regenerating React Components

After enabling React support with:

```bash
npm run setup:react
```

Run:

```bash
npx shadcn-ui init --src src/components/ui --tailwind --dark
```

to generate your initial React UI stubs. To add components later:

```bash
npx shadcn-ui add <componentName> --src src/components/ui --tailwind --dark
```

---

## About Theming

You can import any shadcn/ui-compatible theme (like tweakcn) alongside Basecoat’s CSS by importing its CSS file after Basecoat’s in your styles:

```css
@import "tailwindcss";
@import "basecoat-css";
@import "theme.css";
```

To customize styles, override Tailwind utility classes or modify theme variables. For deep customization, you can copy and edit the Basecoat CSS file directly in your project.

---

## Folder Structure

```text
/
├── public/
│   └── favicon.svg
├── src/
│   ├── layouts/
│   │   └── BaseLayout.astro
│   ├── components/
│   │   └── ui/
│   │       └── README.md
│   ├── pages/
│   │   ├── html/      ← Basecoat HTML prototypes (default)
│   │   ├── react/     ← React + Shadcn UI stubs (enable manually)
│   │   └── svelte/    ← Svelte + Shadcn Svelte stubs (enable manually)
│   └── styles/
│       └── global.css
├── astro.config.mjs
├── tailwind.config.js
├── package.json
└── README.md
```

---

## Summary

- **Basecoat UI is your default prototyping environment**: fast, simple, no framework needed.  
- Use **React** or **Svelte** stubs only when you want to build real interactive components with Shadcn UI.  
- Keep Alpine.js in mind for Basecoat’s JS components or write your own JS if needed.

---

## Helpful Links

- [Basecoat UI Documentation](https://basecoatui.com/docs)  
- [Tailwind CSS with Astro](https://tailwindcss.com/docs/installation/framework-guides/astro)  
- [Shadcn UI](https://ui.shadcn.com)  
- [Alpine.js](https://alpinejs.dev)

