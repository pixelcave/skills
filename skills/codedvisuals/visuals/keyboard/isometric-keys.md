---
name: codedvisuals-keyboard-isometric-keys
description: An isometric keyboard that types shortcuts on tactile keycaps that press down and spring back, with a pill naming each command. The Isometric Keys visual in the Keyboard category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Keyboard / Isometric Keys

An isometric keyboard that types shortcuts on tactile keycaps that press down and spring back, with a pill naming each command.

- **Registry name:** `@codedvisuals/keyboard-isometric-keys`
- **Import path:** `@/components/codedvisuals/keyboard/isometric-keys`

## Install if it is not in the project yet

Look for `components/codedvisuals/keyboard/isometric-keys.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/keyboard-isometric-keys
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `layout` | `KeyDef[][]` | see Default content below |
| `shortcuts` | `KeyShortcut[]` | see Default content below |
| `rounded` | `boolean` | `true` |
| `glow` | `boolean` | `true` |

## Types

```ts
type KeyDef = string | { label: string; width: number };

type KeyShortcut = { keys: string[]; label: string };
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_LAYOUT: KeyDef[][] = [
  [{ label: "⇪", width: 1.75 }, "A", "S", "D", "F"],
  [{ label: "⇧", width: 2.25 }, "Z", "X", "C", "V"],
  ["fn", "⌃", "⌥", { label: "⌘", width: 1.25 }, { label: "", width: 2 }],
];

const DEFAULT_SHORTCUTS: KeyShortcut[] = [
  { keys: ["⌘", "C"], label: "Copy" },
  { keys: ["⌘", "V"], label: "Paste" },
  { keys: ["⌘", "Z"], label: "Undo" },
  { keys: ["⌘", "⇧", "Z"], label: "Redo" },
];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import KeyboardIsometricKeys from "@/components/codedvisuals/keyboard/isometric-keys";

// default
<KeyboardIsometricKeys />

// hover
<KeyboardIsometricKeys hover />

// no glow
<KeyboardIsometricKeys glow={false} />

// custom shortcuts
<KeyboardIsometricKeys
  shortcuts={[
    { keys: ["⌘", "A"], label: "Select all" },
    { keys: ["⌘", "X"], label: "Cut" },
    { keys: ["⌘", "F"], label: "Find" },
    { keys: ["⌘", "S"], label: "Save" },
  ]}
/>

// tab row
<KeyboardIsometricKeys
  layout={[
    [
      { label: "⇥", width: 1.5 },
      "Q",
      "W",
      "E",
      "R",
    ],
    [
      { label: "⇪", width: 1.75 },
      "A",
      "S",
      "D",
      "F",
    ],
    [
      { label: "⇧", width: 2.25 },
      "Z",
      "X",
      "C",
      "V",
    ],
    [
      "fn",
      "⌃",
      "⌥",
      { label: "⌘", width: 1.25 },
      { label: "", width: 2 },
    ],
  ]}
  shortcuts={[
    { keys: ["⌘", "W"], label: "Close tab" },
    { keys: ["⌘", "R"], label: "Reload" },
    { keys: ["⌘", "⇧", "Z"], label: "Redo" },
    { keys: ["⌘", "Q"], label: "Quit" },
  ]}
/>

// square
<KeyboardIsometricKeys rounded={false} />
```
