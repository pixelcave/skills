---
name: codedvisuals-sections-prose
description: A long-form prose section with a heading, a blockquote, and body text. The Prose visual in the Sections category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Sections / Prose

A long-form prose section with a heading, a blockquote, and body text.

- **Registry name:** `@codedvisuals/sections-prose`
- **Import path:** `@/components/codedvisuals/sections/prose`

## Install if it is not in the project yet

Look for `components/codedvisuals/sections/prose.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/sections-prose
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`), presentation modifiers (`gradient`, `fadeOut`, `isometric`), and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `title` | `string` | `"Our story"` |

## Examples

Give the visual a sized container, then drop it in:

```tsx
import SectionsProse from "@/components/codedvisuals/sections/prose";

// default
<SectionsProse />

// fadeOut
<SectionsProse fadeOut />

// custom title · default
<SectionsProse title="Our approach" />

// custom title · isometric
<SectionsProse title="Terms" isometric />

// custom title · isometric · no gradient
<SectionsProse title="Better docs" gradient={false} isometric />
```
