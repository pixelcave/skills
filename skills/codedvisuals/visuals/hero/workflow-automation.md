---
name: codedvisuals-hero-workflow-automation
description: A wide flat workflow canvas where a trigger card runs through step cards into a condition that alternates between its two branch actions. The Workflow Automation visual in the Hero category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Hero / Workflow Automation

A wide flat workflow canvas where a trigger card runs through step cards into a condition that alternates between its two branch actions.

- **Registry name:** `@codedvisuals/hero-workflow-automation`
- **Import path:** `@/components/codedvisuals/hero/workflow-automation`

## Install if it is not in the project yet

Look for `components/codedvisuals/hero/workflow-automation.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/hero-workflow-automation
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`), the presentation modifier (`isometric`), and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `start` | `FlowStep` | see Default content below |
| `steps` | `FlowStep[]` | see Default content below |
| `condition` | `FlowStep` | see Default content below |
| `branches` | `[FlowStep, FlowStep]` | see Default content below |
| `branchLabels` | `[string, string]` | see Default content below |
| `glow` | `boolean` | `true` |
| `guides` | `boolean` | `true` |
| `showLabels` | `boolean` | `true` |

## Types

```ts
interface FlowStep {
  icon: LucideIcon;
  label: string;
  meta?: string;
}
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_START: FlowStep = {
  icon: UserPlus,
  label: "New signup",
  meta: "Webhook trigger",
};

const DEFAULT_STEPS: FlowStep[] = [
  { icon: Sparkles, label: "Enrich profile", meta: "AI lookup" },
  { icon: Gauge, label: "Score lead", meta: "0 to 100" },
];

const DEFAULT_CONDITION: FlowStep = {
  icon: GitBranch,
  label: "Plan is Pro?",
  meta: "Condition",
};

const DEFAULT_BRANCHES: [FlowStep, FlowStep] = [
  { icon: MessageSquare, label: "Notify sales", meta: "Team channel" },
  { icon: Mail, label: "Start onboarding", meta: "Email series" },
];

const DEFAULT_BRANCH_LABELS: [string, string] = ["Yes", "No"];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import HeroWorkflowAutomation from "@/components/codedvisuals/hero/workflow-automation";
import { CreditCard, FileCheck, Package, Receipt, ShoppingCart, Truck, Users } from "lucide-react";

// default
<HeroWorkflowAutomation />

// hover
<HeroWorkflowAutomation hover />

// order fulfillment · custom content
<HeroWorkflowAutomation
  start={{ icon: ShoppingCart, label: "New order", meta: "Checkout" }}
  steps={[
    { icon: CreditCard, label: "Charge card", meta: "$128.00" },
    { icon: Receipt, label: "Send receipt", meta: "Email" },
  ]}
  condition={{ icon: Package, label: "In stock?", meta: "Inventory" }}
  branches={[
    { icon: Truck, label: "Ship today", meta: "Express" },
    { icon: Users, label: "Backorder", meta: "Notify customer" },
  ]}
  branchLabels={["In stock", "Sold out"]}
/>

// minimal · no labels · no guides · no glow
<HeroWorkflowAutomation showLabels={false} guides={false} glow={false} />

// max steps · three steps
<HeroWorkflowAutomation
  steps={[
    {
      icon: FileCheck,
      label: "Verify email",
      meta: "Double opt-in",
    },
    { icon: Users, label: "Enrich profile", meta: "AI lookup" },
    { icon: Receipt, label: "Score lead", meta: "0 to 100" },
  ]}
/>
```
