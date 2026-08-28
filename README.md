# Hously — Modern Architecture Studio

Elegant full-stack workspace for architecture studios, property showcases, and design portfolios with immersive hero motion, curated project galleries, and enterprise-ready deployment.

**Live Demo:** https://gourab775.github.io/hously-modern-architecture

**Category:** Architecture / Real Estate

**Stack:** Next.js 16 · React 19 · TypeScript · Tailwind CSS v4 · Radix UI · shadcn/ui

## Overview

Hously presents modern architecture with editorial precision. The workspace combines a motion-driven hero with parallax foreground/background layering, philosophy and expertise narratives, project collections, FAQ, and conversion-focused calls to action. Built on a clean Next.js App Router foundation with a comprehensive Radix + shadcn/ui component system, it delivers a premium brand experience that scales from portfolio showcase to full property platform with service-backed extensions.

## Features

- **Immersive Motion Hero** — Scroll-driven parallax with foreground/background depth, 3D transforms, and touch + wheel handling for cinematic entry.
- **Curated Project Gallery** — Dedicated `Projects` section for showcasing architectural work with consistent visual language.
- **Narrative Sections** — `Philosophy`, `Expertise`, `FAQ`, and `CallToAction` modules for storytelling and lead conversion.
- **Design System Excellence** — Full Radix UI suite, shadcn/ui, and Tailwind tokens for accessible, themeable components.
- **Performance & Deployment Ready** — Optimized Next.js build, type-safe codebase, and static/hosted deployment flexibility.

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | Next.js 16 (App Router), React 19, TypeScript 5 |
| Styling | Tailwind CSS v4, tailwindcss-animate, class-variance-authority |
| UI | Radix UI, shadcn/ui, Lucide React, Sonner, Vaul |
| Utilities | React Hook Form + Zod, date-fns, Embla Carousel, Recharts |
| Deployment | GitHub Pages / Vercel / EdgeOne, Node.js 18+ |

## Project Structure

```
hously-modern-architecture/
├── app/
│   ├── page.tsx                # Home composition (Header → Hero → Philosophy → Projects → Expertise → FAQ → CTA → Footer)
│   ├── layout.tsx              # Root layout and metadata
│   └── globals.css             # Global styles and design tokens
├── components/
│   ├── header.tsx              # Navigation
│   ├── hero.tsx                # Motion-driven hero with parallax
│   ├── philosophy.tsx          # Studio philosophy
│   ├── projects.tsx            # Project gallery
│   ├── expertise.tsx           # Expertise showcase
│   ├── faq.tsx                 # FAQ
│   ├── call-to-action.tsx      # Conversion CTA
│   ├── footer.tsx              # Footer
│   └── ui/                     # Reusable primitives (shadcn/ui)
├── services/                   # Optional service layer for inquiries, bookings, CMS
│   └── _shared.ts              # Service helpers (add endpoints here)
├── hooks/                      # Custom React hooks
├── lib/                        # Utilities and helpers
├── public/images/              # Hero and project assets
├── styles/                     # Additional style modules
└── package.json
```

> `services/` is reserved as the canonical service directory for future backend extensions (inquiry forms, scheduling, property CMS) and aligns with the workspace service convention.

## Getting Started

### Prerequisites

- Node.js 18+
- npm or pnpm

### Installation

```bash
npm install
# or
pnpm install
```

### Environment Variables

Frontend-only workspace runs without required variables. For service-backed features:

| Variable | Required | Description |
|----------|----------|-------------|
| `SERVICE_API_KEY` | No | Platform gateway key for service integrations. |
| `SERVICE_BASE_URL` | No | Gateway base URL, e.g. `https://gateway.edgeone.link/v1` |
| `SERVICE_MODEL` | No | Model identifier for service features |

> Note: `SERVICE_*` is an alias for `AI_GATEWAY_*` for backward compatibility.

### Development

```bash
npm run dev
```

Open http://localhost:3000

### Build

```bash
npm run build
npm run start
```

## Deployment

### GitHub Pages

Live Demo: https://gourab775.github.io/hously-modern-architecture

Configure `next.config.mjs` for static export if deploying to a sub-path:

```js
const nextConfig = {
  output: 'export',
  basePath: '/hously-modern-architecture',
}
```

Then publish the `out/` directory to `gh-pages`.

### Vercel / EdgeOne

Standard Next.js deployment. Bind `SERVICE_*` variables when enabling service-backed workflows and deploy via CLI or console.

## Customization

- **Hero & Imagery:** Update parallax assets in `public/images/hously-background.png` / `hously-foreground.png` and tune motion parameters in `components/hero.tsx`.
- **Content:** Edit `components/philosophy.tsx`, `projects.tsx`, `expertise.tsx`, `faq.tsx`, and `call-to-action.tsx` for copy and structure.
- **Theming:** Tailwind tokens in `app/globals.css` and `components.json` control palette and radius. Adjust shadcn/ui variants for brand alignment.
- **Services:** Add inquiry and lead handling under `services/` and connect to `CallToAction` and contact flows.
- **SEO & Analytics:** Enhance metadata in `app/layout.tsx` and integrate analytics via `@vercel/analytics` already included.

## License

MIT
