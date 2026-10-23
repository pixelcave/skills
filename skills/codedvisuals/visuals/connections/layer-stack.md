---
name: codedvisuals-connections-layer-stack
description: Pipeline steps as isometric slabs that drop onto each other one by one, squashing the stack until the release ships and lifts away. The Layer Stack visual in the Connections category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Connections / Layer Stack

Pipeline steps as isometric slabs that drop onto each other one by one, squashing the stack until the release ships and lifts away.

- **Registry name:** `@codedvisuals/connections-layer-stack`
- **Import path:** `@/components/codedvisuals/connections/layer-stack`

## Install if it is not in the project yet

Look for `components/codedvisuals/connections/layer-stack.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/connections-layer-stack
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `steps` | `LayerStep[]` | see Default content below |
| `doneLabel` | `string` | `"Deployed v2.4"` |
| `rounded` | `boolean` | `true` |
| `glow` | `boolean` | `true` |
| `showLabel` | `boolean` | `true` |
| `showIcons` | `boolean` | `true` |

## Types

```ts
type LayerStep = { label: string; icon?: React.ElementType };
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_STEPS: LayerStep[] = [
  { label: "Code", icon: Code },
  { label: "Build", icon: Hammer },
  { label: "Test", icon: FlaskConical },
  { label: "Deploy", icon: Rocket },
];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import ConnectionsLayerStack from "@/components/codedvisuals/connections/layer-stack";
import { Database, Package, ShieldCheck, Upload, Zap } from "lucide-react";

// default
<ConnectionsLayerStack />

// hover
<ConnectionsLayerStack hover />

// no glow
<ConnectionsLayerStack glow={false} />

// custom label
<ConnectionsLayerStack doneLabel="Live in production" />

// custom steps
<ConnectionsLayerStack
  steps={[
    { label: "Bundle", icon: Package },
    { label: "Scan", icon: ShieldCheck },
    { label: "Upload", icon: Upload },
  ]}
  doneLabel="Release ready"
/>

// five steps
<ConnectionsLayerStack
  steps={[
    { label: "Install", icon: Package },
    { label: "Migrate", icon: Database },
    { label: "Audit", icon: ShieldCheck },
    { label: "Upload", icon: Upload },
    { label: "Warm up", icon: Zap },
  ]}
/>

// no label
<ConnectionsLayerStack showLabel={false} />

// text only
<ConnectionsLayerStack showIcons={false} />

// square
<ConnectionsLayerStack rounded={false} />
```
