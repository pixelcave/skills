---
name: codedvisuals-hero-scaling-core
description: A wide flat hero scene where line pulses ride fanned lanes into a chip-like compute core and back out, while a status badge below it flips from scaling up to scaled. The Scaling Core visual in the Hero category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Hero / Scaling Core

A wide flat hero scene where line pulses ride fanned lanes into a chip-like compute core and back out, while a status badge below it flips from scaling up to scaled.

- **Registry name:** `@codedvisuals/hero-scaling-core`
- **Import path:** `@/components/codedvisuals/hero/scaling-core`

## Install if it is not in the project yet

Look for `components/codedvisuals/hero/scaling-core.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/hero-scaling-core
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `logo` | `React.ReactNode \| null` | see Default content below |
| `services` | `CoreService[]` | see Default content below |
| `statusLabel` | `string` | `"Autoscaling"` |
| `workingLabel` | `string` | `"Scaling up"` |
| `doneLabel` | `string` | `"Scaled to 8 nodes"` |
| `code` | `string` | `"01100010 01100101 01100101"` |
| `coreLabel` | `string` | `"CORE 01"` |
| `pulseColor` | `string \| string[]` | `"text-primary"` |
| `glow` | `boolean` | `true` |
| `guides` | `boolean` | `true` |
| `showLabels` | `boolean` | `true` |
| `showStatus` | `boolean` | `true` |

## Types

```ts
interface CoreService {
  icon: LucideIcon;
  label?: string;
}
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_LOGO: React.ReactNode = (
  <Layers className="size-8" strokeWidth={1.75} />
);

const DEFAULT_SERVICES: CoreService[] = [
  { icon: Database, label: "Postgres" },
  { icon: Box, label: "Workers" },
];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import HeroScalingCore from "@/components/codedvisuals/hero/scaling-core";
import { Cpu, Gauge, HardDrive } from "lucide-react";

// default
<HeroScalingCore />

// hover
<HeroScalingCore hover />

// ai inference · custom content
<HeroScalingCore
  statusLabel="Inference"
  workingLabel="Warming GPUs"
  doneLabel="Serving 1.2k req/s"
  services={[
    { icon: Cpu, label: "GPU pool" },
    { icon: HardDrive, label: "Model cache" },
  ]}
  code="01101001 01101110 01100110"
  coreLabel="GPU 04"
/>

// multicolor pulses
<HeroScalingCore
  pulseColor={["text-emerald-500", "text-blue-500", "text-orange-500", "text-violet-500", "text-rose-500", "text-sky-500", "text-amber-500"]}
/>

// emerald pulses
<HeroScalingCore pulseColor="text-emerald-500" />

// minimal · no labels · no status · no guides · no glow
<HeroScalingCore
  showLabels={false}
  showStatus={false}
  guides={false}
  glow={false}
/>

// max services · three tiles
<HeroScalingCore
  services={[
    { icon: Cpu, label: "Compute" },
    { icon: HardDrive, label: "Storage" },
    { icon: Gauge, label: "Rate limits" },
  ]}
/>
```
