---
name: codedvisuals-sections-location
description: A location section with a street map, a location pin, and an address row. The Location visual in the Sections category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Sections / Location

A location section with a street map, a location pin, and an address row.

- **Registry name:** `@codedvisuals/sections-location`
- **Import path:** `@/components/codedvisuals/sections/location`

## Install if it is not in the project yet

Look for `components/codedvisuals/sections/location.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/sections-location
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`), presentation modifiers (`gradient`, `fadeOut`, `isometric`), and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `title` | `string` | `"Find us"` |

## Examples

Give the visual a sized container, then drop it in:

```tsx
import SectionsLocation from "@/components/codedvisuals/sections/location";

// default
<SectionsLocation />

// fadeOut
<SectionsLocation fadeOut />

// custom title · default
<SectionsLocation title="Visit our studio" />

// custom title · isometric
<SectionsLocation title="Our offices" isometric />

// custom title · isometric · no gradient
<SectionsLocation title="Come say hello in Lisbon" gradient={false} isometric />
```
