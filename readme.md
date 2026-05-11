# Corso Vue Landing Page

Corso is a responsive training/seminar landing page converted from a static Bootstrap template into a Vue 3 application.

This version keeps the original visual style and layout while using a clean Vue project structure.

## Preview

![Corso Preview](./public/images/screen.png)

## Tech Stack

- Vue 3 (Vue CLI)
- Bootstrap 5 (layout/components behavior)
- Font Awesome 6 (icons)
- `vue3-styled-components` (component wrapper pattern)

## Features

- Sticky navbar with scroll-based background change
- Hero section with Bootstrap carousel slider
- Multiple marketing content sections (Discover, Summary, Takeaways)
- Registration and subscription forms
- Fully responsive layout using Bootstrap utility/grid classes
- Original template styling preserved for visual parity

## Project Structure

```text
corsovue/
├─ public/
│  ├─ css/
│  │  ├─ bootstrap.css
│  │  ├─ font-awesome.css
│  │  └─ styles.css
│  ├─ images/
│  │  └─ ...image assets
│  ├─ webfonts/
│  │  └─ ...font awesome font files
│  └─ index.html
├─ src/
│  ├─ App.vue
│  └─ main.js
├─ package.json
└─ ...Vue CLI config files
```

## Getting Started

### 1) Install dependencies

```bash
npm install
```

### 2) Run development server

```bash
npm run serve
```

The app will be available at the local URL printed in terminal (usually `http://localhost:8080` or `http://localhost:8081`).

### 3) Build for production

```bash
npm run build
```

Production files are generated in `dist/`.

## Available Scripts

- `npm run serve` - Starts the Vue dev server
- `npm run build` - Builds optimized production assets
- `npm run lint` - Runs ESLint checks

## Styling Notes

The app currently loads styles from `public/index.html`:

- `/css/font-awesome.css`
- `/css/bootstrap.css`
- `/css/styles.css`

This approach keeps a clear separation:

- `src/` for Vue app code
- `public/` for static assets (CSS, images, fonts)

## Key Vue Behavior

In `src/App.vue`, the navbar background toggles when scrolling:

- Adds `bg-dark` when `window.scrollY > 50`
- Removes it near the top

This reproduces the behavior from the original template JS in Vue lifecycle hooks.

## Customization Guide

### Update content

Edit section text/markup directly in `src/App.vue`.

### Update styles

Edit:

- `public/css/styles.css` for custom page-specific styles
- `public/css/bootstrap.css` only if you intend to maintain a compiled Bootstrap override file manually

### Update assets

Replace files under:

- `public/images/`
- `public/webfonts/` (if icon font files change)

## Troubleshooting

### Missing module / weird compile errors

Clean reinstall dependencies:

```bash
rm -rf node_modules package-lock.json
npm install
```

On Windows PowerShell:

```powershell
Remove-Item -Recurse -Force .\node_modules
Remove-Item -Force .\package-lock.json
npm install
```

### CSS or fonts not loading

Check that these paths exist and are correct:

- `public/css/*`
- `public/webfonts/*`
- `public/images/*`

## Deployment

After running `npm run build`, deploy the contents of `dist/` to any static hosting provider (Netlify, Vercel static output, GitHub Pages, shared hosting, etc.).

## License

This project inherits the original template licensing context and keeps third-party library licenses (Bootstrap, Font Awesome) as applicable.
