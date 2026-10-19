---
name: codedvisuals-ai-model-picker
description: A model switcher that cycles through AI models and streams each one's answer with its speed, latency, and cost. The Model Picker visual in the AI category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# AI / Model Picker

A model switcher that cycles through AI models and streams each one's answer with its speed, latency, and cost.

- **Registry name:** `@codedvisuals/ai-model-picker`
- **Import path:** `@/components/codedvisuals/ai/model-picker`

## Install if it is not in the project yet

Look for `components/codedvisuals/ai/model-picker.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/ai-model-picker
```

This uses the private registry (one time setup) and installs Motion and lucide-react if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`), presentation modifiers (`gradient`, `isometric`), and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `prompt` | `string` | `"Summarize the Q3 report in one line."` |
| `models` | `Model[]` | see Default content below |
| `selected` | `number` | `0` |
| `glow` | `boolean` | `true` |
| `particles` | `boolean` | `true` |

## Types

```ts
interface Model {
  name: string;
  description: string;
  speed: string;
  latency: string;
  cost: 1 | 2 | 3;
  response: string;
  icon?: React.ReactNode;
}
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_MODELS: Model[] = [
  {
    name: "Claude Opus",
    description: "Most capable",
    speed: "48 tok/s",
    latency: "1.4s",
    cost: 3,
    response:
      "Revenue grew 18% on enterprise deals, churn fell to 2.1%, and the new onboarding flow doubled activation.",
    icon: <Brain />,
  },
  {
    name: "Claude Sonnet",
    description: "Fast and balanced",
    speed: "96 tok/s",
    latency: "0.7s",
    cost: 2,
    response:
      "Revenue rose 18%, churn dropped to 2.1%, and activation doubled after the onboarding update.",
    icon: <Sparkles />,
  },
  {
    name: "Claude Haiku",
    description: "Fastest, lowest cost",
    speed: "182 tok/s",
    latency: "0.3s",
    cost: 1,
    response: "Revenue up 18%, churn down, activation doubled.",
    icon: <Zap />,
  },
];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import AiModelPicker from "@/components/codedvisuals/ai/model-picker";
import { Feather, Gauge, Rocket, Telescope } from "lucide-react";

// default
<AiModelPicker />

// hover
<AiModelPicker hover />

// custom copy
<AiModelPicker
  prompt="Write a subject line for the launch email."
  models={[
    {
      name: "Nova Pro",
      description: "Deep reasoning",
      speed: "52 tok/s",
      latency: "1.2s",
      cost: 3,
      response: "Meet the new onboarding: set up your workspace in half the time.",
      icon: <Telescope />,
    },
    {
      name: "Nova",
      description: "Everyday tasks",
      speed: "110 tok/s",
      latency: "0.6s",
      cost: 2,
      response: "Onboarding just got twice as fast.",
      icon: <Rocket />,
    },
    {
      name: "Nova Lite",
      description: "High volume",
      speed: "240 tok/s",
      latency: "0.2s",
      cost: 1,
      response: "Faster onboarding is here.",
      icon: <Feather />,
    },
  ]}
/>

// starts on haiku
<AiModelPicker selected={2} />

// four models
<AiModelPicker
  models={[
    {
      name: "Claude Opus",
      description: "Most capable",
      speed: "48 tok/s",
      latency: "1.4s",
      cost: 3,
      response: "Revenue grew 18% on enterprise deals, churn fell to 2.1%, and the new onboarding flow doubled activation.",
    },
    {
      name: "Claude Sonnet",
      description: "Fast and balanced",
      speed: "96 tok/s",
      latency: "0.7s",
      cost: 2,
      response: "Revenue rose 18%, churn dropped to 2.1%, and activation doubled after the onboarding update.",
    },
    {
      name: "Claude Haiku",
      description: "Fastest, lowest cost",
      speed: "182 tok/s",
      latency: "0.3s",
      cost: 1,
      response: "Revenue up 18%, churn down, activation doubled.",
    },
    {
      name: "Auto",
      description: "Routes each prompt",
      speed: "Varies",
      latency: "0.5s",
      cost: 2,
      response: "Routed to Sonnet: revenue rose 18% and activation doubled.",
      icon: <Gauge />,
    },
  ]}
/>

// no glow
<AiModelPicker glow={false} />

// no particles
<AiModelPicker particles={false} />

// no glow · no particles
<AiModelPicker glow={false} particles={false} />
```
