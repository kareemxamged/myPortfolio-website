<div align="center">

# Kareem Amged — Personal Portfolio Website

[![Astro](https://img.shields.io/badge/Astro-4.x-BC52EE?logo=astro&logoColor=white)](https://astro.build)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.x-38BDF8?logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![DaisyUI](https://img.shields.io/badge/DaisyUI-4.x-5A0EF8?logo=daisyui&logoColor=white)](https://daisyui.com)
[![TypeScript](https://img.shields.io/badge/TypeScript-Strict-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![MDX](https://img.shields.io/badge/MDX-Supported-F9AC00?logo=mdx&logoColor=white)](https://mdxjs.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-22C55E.svg)](LICENSE)

</div>

---

## Overview

**AMEGOFY** is a free, open-source personal portfolio website template built with **Astro 4**, **TailwindCSS**, and **DaisyUI**. It is designed for developers, designers, and creatives who want a fast, fully static, and highly customizable online presence — complete with a blog, a digital store, and a résumé page, all managed through simple Markdown files.

The site is deployed at: [kemooamegoo.great-site.net](https://kemooamegoo.great-site.net)

---

## Key Features

- **Blog** — Markdown/MDX-powered posts with tag filtering, pagination (10 posts per page), and an RSS feed
- **Digital Store** — Static product/service listings with pricing, badges, and configurable external checkout URLs
- **CV / Résumé Page** — Timeline-based education and experience sections, skills, and certifications
- **Projects Showcase** — Horizontal card layout for highlighting work with live links and tags
- **View Transitions API** — Native browser transitions for smooth, app-like navigation between pages
- **SEO-Ready** — Auto-generated sitemap, RSS feed, OpenGraph meta tags, and `robots.txt`
- **Image Optimization** — Automatic WebP conversion and responsive images via Sharp
- **Responsive Layout** — Drawer-based sidebar: always visible on desktop, toggleable on mobile
- **Type-Safe Content** — Astro Content Collections with Zod schema validation for blog and store entries
- **Themeable** — Full DaisyUI theme support (defaults to `lofi`; swap any theme in one line)

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | [Astro 4](https://astro.build) |
| Styling | [TailwindCSS 3](https://tailwindcss.com) + [DaisyUI 4](https://daisyui.com) |
| Typography | [@tailwindcss/typography](https://tailwindcss.com/docs/typography-plugin) |
| Content | Astro Content Collections (Markdown + MDX) |
| Language | TypeScript (strict mode) |
| Image Processing | [Sharp](https://sharp.pixelplumbing.com) |
| Date Formatting | [Day.js](https://day.js.org) |
| RSS | [@astrojs/rss](https://docs.astro.build/en/guides/rss/) |
| Sitemap | [@astrojs/sitemap](https://docs.astro.build/en/guides/integrations-guide/sitemap/) |
| Package Manager | pnpm (recommended) / npm |

---

## Getting Started

### Prerequisites

- Node.js **v18.14.1** or higher
- [pnpm](https://pnpm.io) (recommended) or npm

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-username/myPortfolio-website.git
cd myPortfolio-website

# 2. Install dependencies (pnpm recommended)
pnpm install
# or
npm install
