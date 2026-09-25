# Portfolio

[![image](https://github.com/user-attachments/assets/138ef793-cb64-41b2-acda-8d9098c78720)](https://saav-super.onrender.com/)

Personal portfolio site for Alejandro Alcocer, a Mobile & Frontend Developer. Built as a single-page static site with [Astro](https://astro.build/) and styled with [Tailwind CSS](https://tailwindcss.com/). Live at [saav-super.onrender.com](https://saav-super.onrender.com/).

## Tech stack

- **[Astro](https://astro.build/)** (v4) — static site generator and component framework (`.astro` components)
- **[Tailwind CSS](https://tailwindcss.com/)** — utility-first styling, dark mode via the `class` strategy
- **TypeScript** — strict config via `astro/tsconfigs/strict`
- **[Fira Code](https://github.com/fonts-hub/fira-code)** (via `@fontsource`) — the site's font
- Package management via **pnpm** (a `pnpm-lock.yaml` and `pnpm-workspace.yaml` are present) with an `package-lock.json` also committed for npm compatibility

## Project structure

```
src/
├── components/       # Astro components that make up the page sections
│   ├── AboutMe.astro
│   ├── Badge.astro
│   ├── Card.astro
│   ├── DownloadCV.astro
│   ├── Education.astro
│   ├── Experience.astro
│   ├── ExperienceItem.astro
│   ├── Header.astro
│   ├── IconApp.astro
│   ├── Profile.astro
│   ├── Projects.astro
│   ├── SectionContainer.astro
│   ├── SocialPill.astro
│   └── Technologies.astro
├── icons/            # Inline SVG icon components (Download, Email, Github, Linkedin, ProfilePic)
├── layouts/
│   └── Layout.astro  # Base HTML document, fonts, global styles, background-image toggle
└── pages/
    └── index.astro   # The single page of the site, composes all sections into a grid

public/                # Static assets: profile photos, tech/project icons, CV PDF, background images
```

### Page composition

`src/pages/index.astro` lays out the following sections in a responsive CSS grid (`Layout.astro` wraps everything with the shared `<head>`, fonts, and global background):

- **Header** — floating pill in the top-right corner with two buttons that swap the page's background image (blue wall / ski photo)
- **Profile** — name, photo, and contact email
- **About Me** — short bio/summary
- **Education** — academic background
- **Technologies** — grid of tech icons (JavaScript, TypeScript, React, Redux, Astro, Cypress, Expo, Three.js, Spring Boot)
- **Projects** — showcased projects with links (Memento, Trivial, TP_Academy, TaxiMap)
- **Experience** — work history with company, role, and dates
- A footer pill with links to GitHub and a CV download (LinkedIn/Email links are present but currently commented out)

## Getting started

Install dependencies (pnpm is the primary package manager used in this repo):

```bash
pnpm install
```

### Available scripts

| Command         | Action                                           |
| --------------- | ------------------------------------------------- |
| `pnpm dev`      | Start the local dev server                        |
| `pnpm start`    | Alias for `pnpm dev`                               |
| `pnpm build`    | Type-check (`astro check`) and build for production |
| `pnpm preview`  | Preview the production build locally               |
| `pnpm astro`    | Run the Astro CLI directly                         |

The dev server runs at `http://localhost:4321` by default.

## Deployment

The site is deployed on [Render](https://render.com/) as a static/build site, available at [saav-super.onrender.com](https://saav-super.onrender.com/).
