---
name: codedvisuals-api-rate-limit
description: Request cubes dropping into an isometric quota tray until it fills, where the next one bounces off with a 429 before the limit drains and resets. The Rate Limit visual in the API category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# API / Rate Limit

Request cubes dropping into an isometric quota tray until it fills, where the next one bounces off with a 429 before the limit drains and resets.

- **Registry name:** `@codedvisuals/api-rate-limit`
- **Import path:** `@/components/codedvisuals/api/rate-limit`

## Install if it is not in the project yet

Look for `components/codedvisuals/api/rate-limit.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/api-rate-limit
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `capacity` | `number` | `6` |
| `methods` | `string[]` | see Default content below |
| `okLabel` | `string` | `"200 OK"` |
| `limitLabel` | `string` | `"429 Too many requests"` |
| `resetLabel` | `string` | `"Limit reset"` |
| `rounded` | `boolean` | `true` |
| `glow` | `boolean` | `true` |
| `showLabel` | `boolean` | `true` |

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_METHODS = ["GET", "POST", "GET", "PUT"];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import ApiRateLimit from "@/components/codedvisuals/api/rate-limit";

// default
<ApiRateLimit />

// hover
<ApiRateLimit hover />

// no glow
<ApiRateLimit glow={false} />

// custom copy
<ApiRateLimit okLabel="Accepted" limitLabel="Slow down" resetLabel="Quota refilled" />

// capacity 4
<ApiRateLimit capacity={4} />

// capacity 8 · custom methods
<ApiRateLimit capacity={8} methods={["GET", "POST", "PUT", "PATCH"]} />

// no label
<ApiRateLimit showLabel={false} />

// square
<ApiRateLimit rounded={false} />
```
