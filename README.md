# AMEGOFY | Personal Portfolio Website Template

![AMEGOFY | Personal Portfolio Website Template](public/full_page.webp)

[![Astro](https://img.shields.io/badge/Astro-v4-BC52EE?logo=astro&logoColor=white)](https://astro.build)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-v3-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![DaisyUI](https://img.shields.io/badge/DaisyUI-v4-5A0EF8?logo=daisyui&logoColor=white)](https://daisyui.com/)
[![TypeScript](https://img.shields.io/badge/TypeScript-Enabled-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/manuelernestog/AMEGOFY/blob/main/LICENSE)
[![Version](https://img.shields.io/badge/Version-3.0.0-informational)](package.json)

AMEGOFY is a free and open-source template for your Personal Portfolio Website built with **Astro v4** and **TailwindCSS**. Launch a professional, fully-featured site in minutes — complete with a Blog, CV, Projects, Services, Store, and RSS Feed.

## Live Demo

▶ [kemooamegoo.great-site.net](https://kemooamegoo.great-site.net/)

---

## Key Features

- **Blog** — Markdown & MDX-powered posts with pagination and tag-based filtering
- **CV / Resume** — Interactive timeline component for experience and education history
- **Projects** — Showcased with rich card components (image, description, badges, tags)
- **Services** — Dedicated services page for freelance or agency offerings
- **Store** — Paginated shop items with pricing, old-price strikethrough, checkout URLs, and custom links
- **RSS Feed** — Auto-generated `/rss.xml` for subscribers via `@astrojs/rss`
- **Sitemap** — Auto-generated on every build via `@astrojs/sitemap`
- **Custom 404 Page** — Branded error page included out of the box
- **30+ Themes** — Swap DaisyUI themes instantly or define your own
- **View Transitions API** — Smooth client-side page navigation (toggleable in config)
- **Image Optimization** — Sharp-powered processing for fast load times
- **Typography Plugin** — `@tailwindcss/typography` for beautifully styled prose content
- **Auto Slug Generation** — Slugs derived from post title or filename (configurable)

---

## Tech Stack

| Technology | Version | Purpose |
|---|---|---|
| [Astro](https://astro.build) | v4 | Core framework & static site generation |
| [TailwindCSS](https://tailwindcss.com/) | v3 | Utility-first styling |
| [DaisyUI](https://daisyui.com/) | v4 | Component library & multi-theming |
| [@astrojs/mdx](https://docs.astro.build/en/guides/integrations-guide/mdx/) | v2 | MDX support in content collections |
| [@astrojs/rss](https://docs.astro.build/en/guides/rss/) | v3 | RSS feed generation |
| [@astrojs/sitemap](https://docs.astro.build/en/guides/integrations-guide/sitemap/) | v3 | Automatic sitemap generation |
| [@tailwindcss/typography](https://tailwindcss.com/docs/typography-plugin) | latest | Prose / article styling |
| [dayjs](https://day.js.org/) | latest | Lightweight date formatting |
| [sharp](https://sharp.pixelplumbing.com/) | latest | Server-side image optimization |
| TypeScript | — | Type safety across the codebase |

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) >= 18
- [pnpm](https://pnpm.io/) (recommended package manager)

### Installation

```bash
pnpm install
```

### Development Server

```bash
pnpm dev
```

Open [http://localhost:4321](http://localhost:4321) in your browser to see the site live with hot-module reloading.

### Build for Production

```bash
pnpm build
```

### Preview Production Build Locally

```bash
pnpm preview
```

---

## Project Structure

```
├── src/
│   ├── components/
│   │   ├── cv/
│   │   │   └── TimeLine.astro          # CV timeline entries
│   │   ├── BaseHead.astro              # <head> meta tags & SEO
│   │   ├── Card.astro
│   │   ├── Footer.astro
│   │   ├── Header.astro
│   │   ├── HorizontalCard.astro        # Blog / project cards
│   │   ├── HorizontalShopItem.astro    # Store item cards
│   │   ├── SideBar.astro
│   │   ├── SideBarMenu.astro           # Navigation links
│   │   └── SideBarFooter.astro         # Social icons
│   ├── content/
│   │   ├── blog/                       # Markdown/MDX blog posts
│   │   ├── store/                      # Store item markdown files
│   │   └── config.ts                   # Content collection schemas
│   ├── layouts/
│   │   ├── BaseLayout.astro            # Global page wrapper
│   │   ├── PostLayout.astro            # Blog post layout
│   │   └── StoreItemLayout.astro       # Store item detail layout
│   ├── lib/
│   │   └── createSlug.ts               # Slug generation utility
│   ├── pages/
│   │   ├── blog/
│   │   │   ├── tag/[tag]/[...page].astro  # Tag-filtered post list
│   │   │   ├── [...page].astro            # Paginated post list
│   │   │   └── [slug].astro               # Individual post page
│   │   ├── store/
│   │   │   ├── [...page].astro            # Paginated store listing
│   │   │   └── [slug].astro               # Individual store item
│   │   ├── cv.astro
│   │   ├── index.astro
│   │   ├── projects.astro
│   │   ├── services.astro
│   │   ├── 404.astro
│   │   └── rss.xml.js
│   ├── styles/
│   │   └── global.css
│   └── config.ts                       # Global site configuration
├── public/
│   └── robots.txt
├── astro.config.mjs
├── tailwind.config.cjs
├── package.json
└── tsconfig.json
```

---

## Site Configuration

Edit `/src/config.ts` to control global site variables:

```ts
export const SITE_TITLE = 'Your Name | Portfolio';
export const SITE_DESCRIPTION = 'Your site description for SEO.';
export const GENERATE_SLUG_FROM_TITLE = true; // false = use filename as slug
export const TRANSITION_API = true;           // toggle View Transitions API
```

Also update the `site` URL in `astro.config.mjs` to match your domain:

```js
export default defineConfig({
  site: 'https://your-domain.com',
  integrations: [mdx(), sitemap(), tailwind()],
});
```

---

## Environment Variables

This template requires **no environment variables** for its core static functionality. If you extend it with external services (e.g., contact forms, CMS APIs, analytics), add a `.env` file at the project root:

```env
# All client-exposed variables must be prefixed with PUBLIC_
PUBLIC_ANALYTICS_ID=your_analytics_id

# Server-side only (no PUBLIC_ prefix) — accessible only in .astro frontmatter
CMS_API_SECRET=your_secret_key
```

> Astro only exposes variables prefixed with `PUBLIC_` to the browser. Keep sensitive keys unprefixed and server-side only.

---

## Components Usage

### Layout Components

`BaseHead`, `Footer`, `Header`, and `SideBar` are already wired into the layout system. Edit those files to change global content and metadata.

#### SideBar

Update your profile picture, page links, and social icons inside `SideBar.astro`. Change the avatar shape using [DaisyUI mask classes](https://daisyui.com/components/mask/). Social icons use SVGs from the [BoxIcons](https://boxicons.com/) pack — swap them in `SideBarFooter.astro`.

Add a new page link in `SideBarMenu.astro`:

```html
<li><a class="py-3 text-base" id="services" href="/services">Services</a></li>
```

To mark a link as active, pass the matching `sideBarActiveItemID` to `BaseLayout` on your page:

```astro
<BaseLayout sideBarActiveItemID="services">
```

#### TimeLine (CV)

```html
<div class="time-line-container">
  <TimeLineElement title="Job Title" subtitle="Company · 2022–Present">
    Description of your role, responsibilities, and key achievements.
  </TimeLineElement>
</div>
```

#### HorizontalCard

Used for blog posts and project showcases:

```html
<HorizontalCard
  title="Card Title"
  img="image_url"
  desc="Short description"
  url="https://link.com"
  target="_blank"
  badge="NEW"
  tags={['astro', 'tailwind']}
/>
```

#### HorizontalShopItem

Used in the Store layout:

```html
<HorizontalShopItem
  title="Item Title"
  img="image_url"
  desc="Item description"
  pricing="$15"
  oldPricing="$25"
  checkoutUrl="https://checkout.example.com/"
  badge="SALE"
  url="/store/item-slug"
  custom_link="https://demo.example.com"
  custom_link_label="View Demo"
  target="_self"
/>
```

#### Adding a Custom Component

Create a `.astro` file in `/src/components/`. Every Astro component follows this structure:

```astro
---
// Component Script — imports, props, JS logic
const { title } = Astro.props;
---
<!-- Component Template — HTML + JSX-like expressions -->
<div>{title}</div>
```

See the [Astro components docs](https://docs.astro.build/en/core-concepts/astro-components/) for full details.

### Blog Post Format

Create `.md` or `.mdx` files inside `/src/content/blog/`:

```yaml
---
title: "Post Title"
description: "A short SEO description"
pubDate: "Jan 01 2024"
heroImage: "/images/hero.webp"
tags: ["astro", "webdev"]
---
Your post content here.
```

### Store Item Format

Create `.md` files inside `/src/content/store/`:

```yaml
---
title: "Item Name"
description: "Item description"
heroImage: "/images/item.webp"
pubDate: "Jan 01 2024"
pricing: "$15"
oldPricing: "$25"
badge: "Featured"
checkoutUrl: "https://checkout.example.com/"
custom_link_label: "View Demo"
custom_link: "https://demo.example.com"
details: true
---
```

### Layouts

Use `BaseLayout` in every page you create, and `PostLayout` for blog post pages. `StoreItemLayout` is used automatically for store item detail pages.

### Content Collections

Add new content types in `/src/content/` and register their schema in `/src/content/config.ts`. See the [Astro content collections guide](https://docs.astro.build/en/guides/content-collections/) for details.

---

## Theming

Change the `data-theme` attribute in `BaseLayout.astro` to switch themes instantly:

```html
<html lang="en" data-theme="dark">
```

30+ built-in themes are available. Browse and preview them at [daisyui.com/docs/themes](https://daisyui.com/docs/themes/).

---

## Sitemap & SEO

The sitemap is auto-generated at build time. Update `public/robots.txt` with your actual domain:

```
User-agent: *
Allow: /

Sitemap: https://your-domain.com/sitemap-index.xml
```

---

## Deploy

Deploy to any static hosting platform:

| Platform | Guide |
|---|---|
| Vercel | [Astro on Vercel](https://docs.astro.build/en/guides/deploy/vercel/) |
| Netlify | [Astro on Netlify](https://docs.astro.build/en/guides/deploy/netlify/) |
| GitHub Pages | [Astro on GitHub Pages](https://docs.astro.build/en/guides/deploy/github/) |

> **⚠️ CAUTION**
> Blog and Store pagination use dynamic route parameters (`[...page].astro`), which are **incompatible with SSR deploy configurations**. Always use the default **static** output mode for deployments.

---

## Contributing

Suggestions and pull requests are welcomed! Feel free to open a discussion or an issue for a new feature request or bug.

One of the best ways to contribute is to grab a [bug report or feature suggestion](https://github.com/manuelernestog/AMEGOFY/issues) marked `accepted` and dig in.

Please be wary of working on issues *not* marked as `accepted` — just because someone has created an issue doesn't mean we'll accept a pull request for it.

---

## License

AMEGOFY is licensed under the MIT license — see the [LICENSE](https://github.com/manuelernestog/AMEGOFY/blob/main/LICENSE) file for details.

---

## Contributors

<a href="https://github.com/manuelernestog/AMEGOFY/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=manuelernestog/AMEGOFY" />
</a>

Made with [contrib.rocks](https://contrib.rocks).

---
---

<div dir="rtl">

# AMEGOFY | قالب موقع المحفظة الشخصية

[![Astro](https://img.shields.io/badge/Astro-v4-BC52EE?logo=astro&logoColor=white)](https://astro.build)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-v3-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![DaisyUI](https://img.shields.io/badge/DaisyUI-v4-5A0EF8?logo=daisyui&logoColor=white)](https://daisyui.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/manuelernestog/AMEGOFY/blob/main/LICENSE)

AMEGOFY هو قالب مجاني ومفتوح المصدر لإنشاء موقع محفظة أعمال شخصية مبني على **Astro v4** و**TailwindCSS**. أطلق موقعك الاحترافي في دقائق — مع مدونة، سيرة ذاتية، مشاريع، خدمات، متجر، وخلاصة RSS.

## العرض التجريبي المباشر

▶ [kemooamegoo.great-site.net](https://kemooamegoo.great-site.net/)

---

## المميزات الرئيسية

- **المدونة** — مقالات مكتوبة بصيغة Markdown وMDX مع ترقيم الصفحات وتصفية بالوسوم
- **السيرة الذاتية** — مكوّن جدول زمني تفاعلي للخبرات والتعليم
- **المشاريع** — عرض احترافي ببطاقات غنية تتضمن صورة ووصفًا وشارات ووسومًا
- **الخدمات** — صفحة مخصصة لعرض الخدمات المستقلة أو خدمات الشركة
- **المتجر** — قوائم منتجات مع الأسعار وخطوط الدفع والروابط المخصصة
- **خلاصة RSS** — ملف `/rss.xml` يُولَّد تلقائيًا للمشتركين
- **خريطة الموقع** — تُولَّد تلقائيًا عند كل عملية بناء
- **صفحة 404 مخصصة** — صفحة خطأ احترافية جاهزة
- **أكثر من 30 ثيمًا** — تبديل ثيمات DaisyUI فورًا أو تصميم ثيم خاص بك
- **واجهة برمجة انتقالات العرض** — تنقل سلس بين الصفحات (قابل للتفعيل/التعطيل)
- **تحسين الصور** — معالجة تلقائية عبر Sharp لأوقات تحميل أسرع
- **مكوّن الطباعة** — تنسيق احترافي للمحتوى النصي الطويل
- **توليد الرابط التلقائي** — يُشتق من عنوان المقال أو اسم الملف (قابل للتهيئة)

---

## التقنيات المستخدمة

| التقنية | الإصدار | الغرض |
|---|---|---|
| [Astro](https://astro.build) | v4 | إطار العمل الأساسي وتوليد المواقع الثابتة |
| [TailwindCSS](https://tailwindcss.com/) | v3 | تنسيق مرن قائم على المرافق |
| [DaisyUI](https://daisyui.com/) | v4 | مكتبة مكوّنات وثيمات متعددة |
| @astrojs/mdx | v2 | دعم صيغة MDX في المحتوى |
| @astrojs/rss | v3 | توليد خلاصة RSS |
| @astrojs/sitemap | v3 | توليد خريطة الموقع تلقائيًا |
| @tailwindcss/typography | الأحدث | تنسيق المحتوى النثري |
| dayjs | الأحدث | تنسيق التواريخ |
| sharp | الأحدث | تحسين الصور من طرف الخادم |
| TypeScript | — | الأمان النوعي عبر قاعدة الشيفرة |

---

## البدء السريع

### المتطلبات الأساسية

- [Node.js](https://nodejs.org/) الإصدار 18 أو أحدث
- [pnpm](https://pnpm.io/) (مدير الحزم الموصى به)

### التثبيت

```bash
pnpm install
```

### تشغيل خادم التطوير

```bash
pnpm dev
```

افتح المتصفح على [http://localhost:4321](http://localhost:4321) لمشاهدة الموقع مباشرةً.

### البناء للإنتاج

```bash
pnpm build
```

### معاينة بناء الإنتاج محليًا

```bash
pnpm preview
```

---

## هيكل المشروع

```
├── src/
│   ├── components/
│   │   ├── cv/
│   │   │   └── TimeLine.astro          # مدخلات الجدول الزمني للسيرة الذاتية
│   │   ├── BaseHead.astro              # وسوم meta لـ SEO
│   │   ├── HorizontalCard.astro        # بطاقات المدونة والمشاريع
│   │   ├── HorizontalShopItem.astro    # بطاقات المتجر
│   │   ├── SideBar.astro
│   │   ├── SideBarMenu.astro           # روابط التنقل
│   │   └── SideBarFooter.astro         # أيقونات التواصل الاجتماعي
│   ├── content/
│   │   ├── blog/                       # مقالات المدونة
│   │   ├── store/                      # ملفات المتجر
│   │   └── config.ts                   # مخططات مجموعات المحتوى
│   ├── layouts/
│   │   ├── BaseLayout.astro            # القالب العام للصفحات
│   │   ├── PostLayout.astro            # قالب المقالات
│   │   └── StoreItemLayout.astro       # قالب تفاصيل المنتج
│   ├── lib/
│   │   └── createSlug.ts               # أداة توليد الروابط المختصرة
│   ├── pages/
│   │   ├── blog/                       # صفحات المدونة والوسوم
│   │   ├── store/                      # صفحات المتجر
│   │   ├── cv.astro
│   │   ├── index.astro
│   │   ├── projects.astro
│   │   ├── services.astro
│   │   ├── 404.astro
│   │   └── rss.xml.js
│   └── config.ts                       # إعدادات الموقع العامة
├── public/
│   └── robots.txt
├── astro.config.mjs
├── tailwind.config.cjs
└── package.json
```

---

## إعداد الموقع

عدّل ملف `/src/config.ts` للتحكم في المتغيرات العامة:

```ts
export const SITE_TITLE = 'اسمك | محفظة الأعمال';
export const SITE_DESCRIPTION = 'وصف موقعك لمحركات البحث.';
export const GENERATE_SLUG_FROM_TITLE = true; // false = استخدم اسم الملف
export const TRANSITION_API = true;           // تفعيل/تعطيل انتقالات العرض
```

حدّث أيضًا عنوان الموقع في `astro.config.mjs`:

```js
export default defineConfig({
  site: 'https://نطاقك.com',
  integrations: [mdx(), sitemap(), tailwind()],
});
```

---

## متغيرات البيئة

لا يحتاج هذا القالب إلى متغيرات بيئية لوظائفه الثابتة الأساسية. إن أضفت خدمات خارجية (نماذج، واجهات API، تحليلات)، أنشئ ملف `.env` في جذر المشروع:

```env
# المتغيرات المكشوفة للعميل تبدأ بـ PUBLIC_
PUBLIC_ANALYTICS_ID=معرّف_التحليلات

# متغيرات الخادم فقط — لا تُكشف للمتصفح
CMS_API_SECRET=مفتاحك_السري
```

> يكشف Astro فقط المتغيرات التي تبدأ بـ `PUBLIC_` للمتصفح. احتفظ بالمفاتيح الحساسة بدون هذا البادئ.

---

## استخدام المكوّنات

### الشريط الجانبي (SideBar)

عدّل الصورة الشخصية وروابط الصفحات وأيقونات التواصل الاجتماعي في `SideBar.astro`. غيّر شكل الصورة الرمزية باستخدام [فئات DaisyUI mask](https://daisyui.com/components/mask/).

أضف رابطًا جديدًا في `SideBarMenu.astro`:

```html
<li><a class="py-3 text-base" id="services" href="/services">الخدمات</a></li>
```

لتمييز الرابط النشط، مرّر `sideBarActiveItemID` إلى `BaseLayout`:

```astro
<BaseLayout sideBarActiveItemID="services">
```

### الجدول الزمني (TimeLine)

```html
<div class="time-line-container">
  <TimeLineElement title="المسمى الوظيفي" subtitle="الشركة · 2022–الآن">
    وصف دورك ومسؤولياتك وإنجازاتك.
  </TimeLineElement>
</div>
```

### صيغة مقالات المدونة

أنشئ ملفات `.md` أو `.mdx` في `/src/content/blog/`:

```yaml
---
title: "عنوان المقال"
description: "وصف مختصر لمحركات البحث"
pubDate: "Jan 01 2024"
heroImage: "/images/hero.webp"
tags: ["astro", "تطوير-ويب"]
---
محتوى المقال هنا.
```

### صيغة منتجات المتجر

أنشئ ملفات `.md` في `/src/content/store/`:

```yaml
---
title: "اسم المنتج"
description: "وصف المنتج"
heroImage: "/images/item.webp"
pubDate: "Jan 01 2024"
pricing: "$15"
oldPricing: "$25"
badge: "مميز"
checkoutUrl: "https://checkout.example.com/"
custom_link_label: "عرض تجريبي"
custom_link: "https://demo.example.com"
details: true
---
```

---

## الثيمات

غيّر خاصية `data-theme` في `BaseLayout.astro` لتبديل الثيم فورًا:

```html
<html lang="ar" dir="rtl" data-theme="dark">
```

يتوفر أكثر من 30 ثيمًا جاهزًا. استعرضها على [daisyui.com/docs/themes](https://daisyui.com/docs/themes/).

---

## خريطة الموقع وتحسين محركات البحث

تُولَّد خريطة الموقع تلقائيًا عند كل بناء. حدّث ملف `public/robots.txt` بنطاقك:

```
User-agent: *
Allow: /

Sitemap: https://نطاقك.com/sitemap-index.xml
```

---

## النشر

انشر الموقع على أي منصة استضافة ثابتة:

| المنصة | الدليل |
|---|---|
| Vercel | [Astro على Vercel](https://docs.astro.build/en/guides/deploy/vercel/) |
| Netlify | [Astro على Netlify](https://docs.astro.build/en/guides/deploy/netlify/) |
| GitHub Pages | [Astro على GitHub Pages](https://docs.astro.build/en/guides/deploy/github/) |

> **⚠️ تحذير**
> يستخدم ترقيم صفحات المدونة والمتجر معاملات مسار ديناميكية (`[...page].astro`)، وهي **غير متوافقة مع إعدادات النشر SSR**. استخدم دائمًا وضع الإخراج **الثابت** الافتراضي.

---

## المساهمة

نرحب بالاقتراحات وطلبات السحب! لا تتردد في فتح نقاش أو إبلاغ عن مشكلة أو طلب ميزة جديدة.

ابحث عن [تقارير الأخطاء وطلبات الميزات](https://github.com/manuelernestog/AMEGOFY/issues) المُعلَّمة بـ `accepted` وابدأ العمل.

---

## الرخصة

يخضع AMEGOFY لرخصة MIT — راجع ملف [LICENSE](https://github.com/manuelernestog/AMEGOFY/blob/main/LICENSE) للتفاصيل.

---

## المساهمون

<a href="https://github.com/manuelernestog/AMEGOFY/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=manuelernestog/AMEGOFY" />
</a>

صُنع بواسطة [contrib.rocks](https://contrib.rocks).

</div>
