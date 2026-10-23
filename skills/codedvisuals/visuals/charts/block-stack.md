---
name: codedvisuals-charts-block-stack
description: An isometric bar chart whose columns grow as blocks drop onto them, each landing squashing the stack with a springy bounce. The Block Stack visual in the Charts category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Charts / Block Stack

An isometric bar chart whose columns grow as blocks drop onto them, each landing squashing the stack with a springy bounce.

- **Registry name:** `@codedvisuals/charts-block-stack`
- **Import path:** `@/components/codedvisuals/charts/block-stack`

## Install if it is not in the project yet

Look for `components/codedvisuals/charts/block-stack.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/charts-block-stack
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `data` | `number[]` | see Default content below |
| `colors` | `string[]` | - |
| `label` | `string` | `"Growth"` |
| `rounded` | `boolean` | `true` |
| `glow` | `boolean` | `true` |
| `showLabel` | `boolean` | `true` |

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_DATA = [2, 4, 3, 5, 6];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import ChartsBlockStack from "@/components/codedvisuals/charts/block-stack";

// default
<ChartsBlockStack />

// hover
<ChartsBlockStack hover />

// no glow
<ChartsBlockStack glow={false} />

// custom label
<ChartsBlockStack label="Revenue" />

// palette colors
<ChartsBlockStack
  colors={["--color-sky-500", "--color-indigo-500", "--color-violet-500", "--color-fuchsia-500", "--color-rose-500"]}
/>

// custom data
<ChartsBlockStack data={[6, 4, 5, 2, 3, 1]} />

// no label
<ChartsBlockStack showLabel={false} />

// square
<ChartsBlockStack rounded={false} />
```
