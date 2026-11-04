---
name: codedvisuals-hero-software-factory
description: A wide isometric hero scene where asset blocks feed a processor along circuit traces that merge into one shipped product. The Software Factory visual in the Hero category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Hero / Software Factory

A wide isometric hero scene where asset blocks feed a processor along circuit traces that merge into one shipped product.

- **Registry name:** `@codedvisuals/hero-software-factory`
- **Import path:** `@/components/codedvisuals/hero/software-factory`

## Install if it is not in the project yet

Look for `components/codedvisuals/hero/software-factory.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/hero-software-factory
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `logo` | `React.ReactNode \| null` | see Default content below |
| `inputs` | `FactoryItem[]` | see Default content below |
| `output` | `FactoryItem` | see Default content below |
| `buildingLabel` | `string` | `"Building…"` |
| `glow` | `boolean` | `true` |
| `guides` | `boolean` | `true` |
| `showLabels` | `boolean` | `true` |

## Types

```ts
interface FactoryItem {
  icon: LucideIcon;
  label: string;
  meta?: string;
  color?: string;
}
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_LOGO: React.ReactNode = (
  <Zap className="size-10" strokeWidth={1.75} />
);

const DEFAULT_INPUTS: FactoryItem[] = [
  {
    icon: PenTool,
    label: "Designs",
    meta: "24 frames",
    color: "text-violet-500",
  },
  { icon: FileText, label: "Specs", meta: "8 docs", color: "text-sky-500" },
  { icon: Bug, label: "Issues", meta: "36 open", color: "text-amber-500" },
  {
    icon: Database,
    label: "Data",
    meta: "12 tables",
    color: "text-emerald-500",
  },
];

const DEFAULT_OUTPUT: FactoryItem = {
  icon: Rocket,
  label: "Shipped",
  meta: "v2.4 live",
};
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import HeroSoftwareFactory from "@/components/codedvisuals/hero/software-factory";
import { Bug, Database, FileText, MessageSquare, PenTool, Users } from "lucide-react";

// default
<HeroSoftwareFactory />

// hover
<HeroSoftwareFactory hover />

// minimal · no labels · no guides · no glow
<HeroSoftwareFactory showLabels={false} guides={false} glow={false} />

// max inputs · six sources
<HeroSoftwareFactory
  inputs={[
    {
      icon: PenTool,
      label: "Designs",
      meta: "24 frames",
      color: "text-violet-500",
    },
    {
      icon: FileText,
      label: "Specs",
      meta: "8 docs",
      color: "text-sky-500",
    },
    {
      icon: MessageSquare,
      label: "Feedback",
      meta: "112 notes",
      color: "text-pink-500",
    },
    {
      icon: Bug,
      label: "Issues",
      meta: "36 open",
      color: "text-amber-500",
    },
    {
      icon: Database,
      label: "Data",
      meta: "12 tables",
      color: "text-emerald-500",
    },
    {
      icon: Users,
      label: "Research",
      meta: "9 interviews",
      color: "text-indigo-500",
    },
  ]}
/>
```
