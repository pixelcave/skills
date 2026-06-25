---
name: codedvisuals-geo-globe
description: A rotating globe of dotted continents with location markers and connection arcs that draw in. The Globe visual in the Geo category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Geo / Globe

A rotating globe of dotted continents with location markers and connection arcs that draw in.

- **Registry name:** `@codedvisuals/geo-globe`
- **Import path:** `@/components/codedvisuals/geo/globe`

## Install if it is not in the project yet

Look for `components/codedvisuals/geo/globe.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/geo-globe
```

This uses the private registry (one time setup) and installs Motion and lucide-react if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and presentation modifiers (`gradient`, `fadeOut`, `isometric`) plus `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `markers` | `Marker[]` | - |
| `arcs` | `boolean` | `true` |
| `arcPairs` | `[number, number][]` | - |
| `arcDrawIn` | `boolean` | `true` |
| `half` | `boolean` | `false` |
| `tilt` | `GlobeTilt` | `"top"` |
| `startAt` | `GlobeStart` | `"atlantic"` |
| `spinSpeed` | `number` | see Default content below |
| `wrapperClassName` | `string` | - |

## Types

```ts
interface Marker {
  lat: number;
  lng: number;
}

type GlobeTilt = "top" | "equator" | "bottom" | number;

type GlobeStart = GlobeRegion | number;

type GlobeRegion =
  | "americas"
  | "atlantic"
  | "europe"
  | "africa"
  | "asia"
  | "oceania"
  | "pacific";
```

## Default content

The values used when you do not pass the matching prop:

```ts
const CONFIG = {
  landSampleCount: 5400,
  fill: 0.94,
  padding: 6,
  dotRadius: 1,
  dotAlphaBuckets: 12,
  spinSpeed: -12,
  arcHeight: 0.32,
  arcSamples: 54,
  arcDotSpeed: 0.00016,
  arcTravel: 0.5,
  arcClipDepth: 0,
  pulseSpeed: 0.0038,
  activityEase: 220,
  arcDrawDuration: 850,
  arcStagger: 200,
  markerLimbBand: 0.2,
  frameStep: 1,
} as const;
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import GeoGlobe from "@/components/codedvisuals/geo/globe";

// default
<GeoGlobe />

// hover
<GeoGlobe hover />

// equator tilt
<GeoGlobe tilt="equator" />

// bottom tilt
<GeoGlobe tilt="bottom" />

// reverse spin
<GeoGlobe spinSpeed={12} />

// half
<GeoGlobe
  half
  arcs={false}
  spinSpeed={3}
  wrapperClassName="max-w-120"
/>

// start: americas
<GeoGlobe startAt="americas" />

// custom markers with arc pairs
<GeoGlobe
  markers={[
    { lat: 40.71, lng: -74.0 },
    { lat: 51.51, lng: -0.13 },
    { lat: 35.68, lng: 139.69 },
    { lat: -33.87, lng: 151.21 },
  ]}
  arcPairs={[
    [0, 1],
    [0, 2],
    [0, 3],
  ]}
/>
```
