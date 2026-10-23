---
name: codedvisuals-tasks-sort-lanes
description: Task cubes gliding across isometric To do, In progress, and Done lanes, each landing with a springy press while lane counts tick over. The Sort Lanes visual in the Tasks category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Tasks / Sort Lanes

Task cubes gliding across isometric To do, In progress, and Done lanes, each landing with a springy press while lane counts tick over.

- **Registry name:** `@codedvisuals/tasks-sort-lanes`
- **Import path:** `@/components/codedvisuals/tasks/sort-lanes`

## Install if it is not in the project yet

Look for `components/codedvisuals/tasks/sort-lanes.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/tasks-sort-lanes
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `icons` | `React.ElementType[]` | see Default content below |
| `lanes` | `string[]` | see Default content below |
| `rounded` | `boolean` | `true` |
| `glow` | `boolean` | `true` |
| `showLabels` | `boolean` | `true` |

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_ICONS: React.ElementType[] = [PenTool, Bug, Rocket, Mail];

const DEFAULT_LANES = ["To do", "In progress", "Done"];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import TasksSortLanes from "@/components/codedvisuals/tasks/sort-lanes";
import { CreditCard, Database, Globe, Megaphone } from "lucide-react";

// default
<TasksSortLanes />

// hover
<TasksSortLanes hover />

// no glow
<TasksSortLanes glow={false} />

// custom lanes
<TasksSortLanes lanes={["Backlog", "Review", "Shipped"]} />

// custom icons
<TasksSortLanes icons={[Globe, Database, CreditCard, Megaphone]} />

// three tasks
<TasksSortLanes icons={[Globe, Database, CreditCard]} />

// no labels
<TasksSortLanes showLabels={false} />

// square
<TasksSortLanes rounded={false} />
```
