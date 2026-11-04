---
name: codedvisuals-hero-agent-hub
description: A wide isometric hero scene where an AI agent core calls a ring of tool blocks in turn, sending pulses out and back as each one works. The Agent Hub visual in the Hero category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Hero / Agent Hub

A wide isometric hero scene where an AI agent core calls a ring of tool blocks in turn, sending pulses out and back as each one works.

- **Registry name:** `@codedvisuals/hero-agent-hub`
- **Import path:** `@/components/codedvisuals/hero/agent-hub`

## Install if it is not in the project yet

Look for `components/codedvisuals/hero/agent-hub.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/hero-agent-hub
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `logo` | `React.ReactNode \| null` | see Default content below |
| `tools` | `AgentTool[]` | see Default content below |
| `actionLabel` | `string` | `"Working…"` |
| `glow` | `boolean` | `true` |
| `guides` | `boolean` | `true` |
| `showLabels` | `boolean` | `true` |

## Types

```ts
interface AgentTool {
  icon: LucideIcon;
  label: string;
  meta?: string;
  action?: string;
  color?: string;
}
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_LOGO: React.ReactNode = (
  <BrainCircuit className="size-10" strokeWidth={1.75} />
);

const DEFAULT_TOOLS: AgentTool[] = [
  {
    icon: GitPullRequest,
    label: "Code",
    meta: "PR #212",
    action: "Opening PR…",
  },
  {
    icon: MessageSquare,
    label: "Chat",
    meta: "3 replies",
    action: "Posting…",
  },
  {
    icon: CalendarDays,
    label: "Calendar",
    meta: "Fri 10:00",
    action: "Booking…",
  },
  {
    icon: Database,
    label: "Database",
    meta: "1.2k rows",
    action: "Querying…",
  },
  {
    icon: FileText,
    label: "Docs",
    meta: "Spec v3",
    action: "Writing…",
  },
  {
    icon: Globe,
    label: "Browser",
    meta: "8 sources",
    action: "Searching…",
  },
];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import HeroAgentHub from "@/components/codedvisuals/hero/agent-hub";
import { CalendarDays, Database, FileText, GitPullRequest, Globe, Mail, MessageSquare, Users } from "lucide-react";

// default
<HeroAgentHub />

// hover
<HeroAgentHub hover />

// minimal · no labels · no guides · no glow
<HeroAgentHub showLabels={false} guides={false} glow={false} />

// max tools · eight tools
<HeroAgentHub
  tools={[
    {
      icon: GitPullRequest,
      label: "Code",
      meta: "PR #212",
      action: "Opening PR…",
    },
    {
      icon: MessageSquare,
      label: "Chat",
      meta: "3 replies",
      action: "Posting…",
    },
    {
      icon: CalendarDays,
      label: "Calendar",
      meta: "Fri 10:00",
      action: "Booking…",
    },
    {
      icon: Database,
      label: "Database",
      meta: "1.2k rows",
      action: "Querying…",
    },
    {
      icon: FileText,
      label: "Docs",
      meta: "Spec v3",
      action: "Writing…",
    },
    {
      icon: Globe,
      label: "Browser",
      meta: "8 sources",
      action: "Searching…",
    },
    {
      icon: Mail,
      label: "Email",
      meta: "Reply sent",
      action: "Drafting…",
    },
    {
      icon: Users,
      label: "CRM",
      meta: "Lead updated",
      action: "Syncing…",
    },
  ]}
/>
```
