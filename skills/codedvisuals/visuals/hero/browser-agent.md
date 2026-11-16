---
name: codedvisuals-hero-browser-agent
description: A wide isometric hero scene where an agent core gathers context, clicks through a stack of floating browser windows, then waits on an approval card until a human switches it on. The Browser Agent visual in the Hero category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Hero / Browser Agent

A wide isometric hero scene where an agent core gathers context, clicks through a stack of floating browser windows, then waits on an approval card until a human switches it on.

- **Registry name:** `@codedvisuals/hero-browser-agent`
- **Import path:** `@/components/codedvisuals/hero/browser-agent`

## Install if it is not in the project yet

Look for `components/codedvisuals/hero/browser-agent.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/hero-browser-agent
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `logo` | `React.ReactNode \| null` | see Default content below |
| `contexts` | `AgentContext[]` | see Default content below |
| `steps` | `BrowserStep[]` | see Default content below |
| `approval` | `ApprovalCard` | see Default content below |
| `glow` | `boolean` | `true` |
| `guides` | `boolean` | `true` |
| `showLabels` | `boolean` | `true` |

## Types

```ts
interface AgentContext {
  icon: LucideIcon;
  label: string;
  meta?: string;
  color?: string;
}

interface BrowserStep {
  search?: boolean;
  rows?: number;
  pick?: number;
}

interface ApprovalCard {
  icon?: LucideIcon;
  title: string;
  detail?: string;
  waitingLabel: string;
  approvedLabel: string;
  control: string;
}
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_LOGO: React.ReactNode = (
  <Bot className="size-8" strokeWidth={1.75} />
);

const DEFAULT_CONTEXTS: AgentContext[] = [
  { icon: FileText, label: "Notes", meta: "notes.md" },
  { icon: UserRound, label: "Profile", meta: "Size 42" },
  { icon: Wallet, label: "Budget", meta: "Under $120" },
];

const DEFAULT_STEPS: BrowserStep[] = [
  { search: true, rows: 3, pick: 0 },
  { rows: 3, pick: 1 },
  { rows: 3, pick: 2 },
];

const DEFAULT_APPROVAL: ApprovalCard = {
  icon: ShoppingCart,
  title: "Checkout",
  detail: "$84 at store.example",
  waitingLabel: "Waiting for approval",
  approvedLabel: "Approved",
  control: "Allow purchase",
};
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import HeroBrowserAgent from "@/components/codedvisuals/hero/browser-agent";
import { FileText, UserRound, Wallet } from "lucide-react";

// default
<HeroBrowserAgent />

// hover
<HeroBrowserAgent hover />

// minimal · no labels · no guides · no glow
<HeroBrowserAgent showLabels={false} guides={false} glow={false} />

// max steps · four windows
<HeroBrowserAgent
  contexts={[
    { icon: FileText, label: "Notes", meta: "notes.md" },
    { icon: UserRound, label: "Profile", meta: "Size 42" },
    { icon: Wallet, label: "Budget", meta: "Under $120" },
  ]}
  steps={[
    { search: true, rows: 3, pick: 0 },
    { rows: 3, pick: 1 },
    { rows: 3, pick: 2 },
    { search: true, rows: 2, pick: 1 },
  ]}
/>
```
