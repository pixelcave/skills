---
name: codedvisuals-ai-thinking
description: A reasoning panel that streams its thinking steps, collapses into a summary, then streams the final answer. The Thinking visual in the AI category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# AI / Thinking

A reasoning panel that streams its thinking steps, collapses into a summary, then streams the final answer.

- **Registry name:** `@codedvisuals/ai-thinking`
- **Import path:** `@/components/codedvisuals/ai/thinking`

## Install if it is not in the project yet

Look for `components/codedvisuals/ai/thinking.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/ai-thinking
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`), presentation modifiers (`gradient`, `isometric`), and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `prompt` | `string` | `"Why did churn drop in Q3?"` |
| `steps` | `string[]` | see Default content below |
| `answer` | `string` | `"Churn fell to 2.1% mainly because the new onboarding flow doubled first-week activation. Cancellations citing setup problems dropped 40%."` |
| `duration` | `string` | `"8s"` |
| `collapse` | `boolean` | `true` |
| `glow` | `boolean` | `true` |
| `particles` | `boolean` | `true` |

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_STEPS = [
  "Pulling Q3 churn by cohort and plan",
  "Lining it up with the onboarding release date",
  "Reading cancel reasons in support tickets",
  "Ruling out seasonality against last year",
];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import AiThinking from "@/components/codedvisuals/ai/thinking";

// default
<AiThinking />

// hover
<AiThinking hover />

// code · custom copy
<AiThinking
  prompt="Why is the checkout test failing?"
  steps={["Reading the failing test output", "Tracing the tax total back to the cart", "Finding where rounding happens twice"]}
  answer="Tax is rounded per line and again on the total, so carts with many items drift by a cent. Round once, on the final total."
  duration="5s"
/>

// research · custom copy
<AiThinking
  prompt="Which plan should a 20 person team pick?"
  steps={["Comparing seat limits across plans", "Checking which plans include SSO", "Estimating yearly cost for 20 seats", "Weighing support response times", "Picking the best value"]}
  answer="Go with Team. It covers 25 seats with SSO and priority support, and costs 30% less than Business for the same features you need."
  duration="12s"
/>

// no collapse
<AiThinking collapse={false} />

// no collapse · isometric
<AiThinking collapse={false} isometric />

// no glow
<AiThinking glow={false} />

// no particles
<AiThinking particles={false} />

// no glow · no particles
<AiThinking glow={false} particles={false} />
```
