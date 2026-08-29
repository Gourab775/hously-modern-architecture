# Hously â€” Modern Architecture Studio

Elegant full-stack workspace for architecture studios, property showcases, and design portfolios with immersive hero motion, curated project galleries, and enterprise-ready deployment.

**Live Demo:** https://hously-modern-architecture.vercel.app

**Category:** Architecture / Real Estate

**Stack:** Next.js 16 Â· React 19 Â· TypeScript Â· Tailwind CSS v4 Â· Radix UI Â· shadcn/ui

## Overview

Hously presents modern architecture with editorial precision. The workspace combines a motion-driven hero with parallax foreground/background layering, philosophy and expertise narratives, project collections, FAQ, and conversion-focused calls to action. Built on a clean Next.js App Router foundation with a comprehensive Radix + shadcn/ui component system, it delivers a premium brand experience that scales from portfolio showcase to full property platform with service-backed extensions.

## Features

- **Immersive Motion Hero** â€” Scroll-driven parallax with foreground/background depth, 3D transforms, and touch + wheel handling for cinematic entry.
- **Curated Project Gallery** â€” Dedicated `Projects` section for showcasing architectural work with consistent visual language.
- **Narrative Sections** â€” `Philosophy`, `Expertise`, `FAQ`, and `CallToAction` modules for storytelling and lead conversion.
- **Design System Excellence** â€” Full Radix UI suite, shadcn/ui, and Tailwind tokens for accessible, themeable components.
- **Performance & Deployment Ready** â€” Optimized Next.js build, type-safe codebase, and static/hosted deployment flexibility.

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
â”œâ”€â”€ app/
â”‚   â”œâ”€â”€ page.tsx                # Home composition (Header â†’ Hero â†’ Philosophy â†’ Projects â†’ Expertise â†’ FAQ â†’ CTA â†’ Footer)
â”‚   â”œâ”€â”€ layout.tsx              # Root layout and metadata
â”‚   â””â”€â”€ globals.css             # Global styles and design tokens
â”œâ”€â”€ components/
â”‚   â”œâ”€â”€ header.tsx              # Navigation
â”‚   â”œâ”€â”€ hero.tsx                # Motion-driven hero with parallax
â”‚   â”œâ”€â”€ philosophy.tsx          # Studio philosophy
â”‚   â”œâ”€â”€ projects.tsx            # Project gallery
â”‚   â”œâ”€â”€ expertise.tsx           # Expertise showcase
â”‚   â”œâ”€â”€ faq.tsx                 # FAQ
â”‚   â”œâ”€â”€ call-to-action.tsx      # Conversion CTA
â”‚   â”œâ”€â”€ footer.tsx              # Footer
â”‚   â””â”€â”€ ui/                     # Reusable primitives (shadcn/ui)
â”œâ”€â”€ services/                   # Optional service layer for inquiries, bookings, CMS
â”‚   â””â”€â”€ _shared.ts              # Service helpers (add endpoints here)
â”œâ”€â”€ hooks/                      # Custom React hooks
â”œâ”€â”€ lib/                        # Utilities and helpers
â”œâ”€â”€ public/images/              # Hero and project assets
â”œâ”€â”€ styles/                     # Additional style modules
â””â”€â”€ package.json
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

Live Demo: https://hously-modern-architecture.vercel.app

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
