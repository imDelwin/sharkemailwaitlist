# Shark — Brand Guidelines

> Track your sessions. Analyze your game. Share your journey.

---

## 1. Identity

**App Name**: Shark
**Full Name**: SharkPoker
**Category**: Social poker session tracker
**Aesthetic Inspiration**: Strava, Ramp, Apple
**Tone**: Bright, clean, premium, high-trust

Shark is a tool for serious players. The design should feel fast, data-driven, and social — like a fitness tracker for poker.

---

## 2. Logo & Icons

| Asset | Path |
|---|---|
| Primary logo | `public/brand/shark-logo.png` |
| Favicon (16/32px) | `public/favicon.ico`, `public/favicon.png` |
| App icons (PWA) | `public/icon-192.png`, `public/icon-512.png` |
| Apple touch icon | `public/apple-touch-icon.png` |

**Usage rules**:
- Maintain clear space equal to the logo height on all sides
- Do not recolor, stretch, or apply effects to the logo
- On dark backgrounds, use the light variant if available

---

## 3. Color Palette

All colors are defined as CSS variables in `src/index.css` using HSL format.

### Primary

| Name | Hex | HSL Variable | Usage |
|---|---|---|---|
| Shark Blue | `#2563EB` | `217 91% 53%` | Primary buttons, links, active states |
| Shark Blue Hover | `#1D4ED8` | `224 76% 48%` | Hover state for primary actions |
| Shark Blue Tint | `#EAF2FF` | `216 100% 96%` | Selected chips, accent backgrounds |

### Text

| Name | Hex | HSL Variable | Usage |
|---|---|---|---|
| Primary Text | `#0B1220` | `220 53% 8%` | Headings, body copy |
| Secondary Text | `#52657A` | `210 20% 40%` | Subtitles, supporting text |
| Tertiary Text | `#7B8FA6` | `212 18% 57%` | Timestamps, metadata, placeholders |

### Backgrounds

| Name | Hex | HSL Variable | Usage |
|---|---|---|---|
| Page Background | `#F7F9FC` | `216 33% 97%` | App background (off-white) |
| Card Surface | `#FFFFFF` | `0 0% 100%` | Cards, sheets, dialogs |
| Secondary Background | `#F1F4F9` | `216 33% 95%` | Muted sections, stat blocks |
| Border | `#E2EAF4` | `214 40% 92%` | Card borders, separators (blue-tinted) |

### Semantic

| Name | Hex | Usage |
|---|---|---|
| Profit Green | `#16A34A` | Positive P&L, win indicators |
| Profit Tint | `#EAF7EF` | Profit chip backgrounds |
| Loss Red | `#DC2626` | Negative P&L, loss indicators |
| Loss Tint | `#FDECEC` | Loss chip backgrounds |
| Orange Accent | `#F97316` | Notifications, highlights — use sparingly |

### Dark Mode

Dark mode preserves the same Shark Blue accent system. Backgrounds shift to deep navy:

| Token | HSL |
|---|---|
| Background | `222 47% 7%` |
| Card | `222 47% 10%` |
| Foreground | `220 14% 96%` |

---

## 4. Typography

### Typefaces

| Role | Font | Fallbacks |
|---|---|---|
| UI (primary) | Inter | `-apple-system`, `BlinkMacSystemFont`, `SF Pro Display`, `system-ui`, `sans-serif` |
| Monospace | SF Mono | `Menlo`, `Monaco`, `Consolas`, `monospace` |

### Weights

| Weight | Value | Usage |
|---|---|---|
| Bold | 700 | H1, H2, H3, key metrics |
| Semibold | 600 | H4–H6, buttons, emphasis |
| Regular | 400 | Body copy, descriptions |

### Scale

| Token | Size | Usage |
|---|---|---|
| 2xs | 11px / 0.6875rem | Fine print, badge labels |
| xs | 12px / 0.75rem | Meta, timestamps |
| sm | 14px / 0.875rem | Secondary text, card descriptions |
| base | 16px / 1rem | Body text |
| lg | 18px / 1.125rem | Section titles |
| xl | 20px / 1.25rem | Card titles |
| 2xl | 24px / 1.5rem | Page headings |

**Note**: Inputs use a minimum of 16px to prevent iOS auto-zoom.

### Tracking

- Headings: `-0.02em` (tighter)
- Subheadings: `-0.01em`
- Body / UI labels: `0` (normal)

---

## 5. Spacing & Shape

### Border Radius

| Token | Value | Usage |
|---|---|---|
| `--radius` | 16px | Cards, dialogs, primary containers |
| `--radius - 2px` | 14px | Medium components |
| `--radius - 4px` | 12px | Small components (badges, inputs) |
| `rounded-full` | 9999px | Pill buttons, avatar rings, chips |

### Shadows

| Name | Value | Usage |
|---|---|---|
| xs | `0 1px 2px 0 rgb(0 0 0 / 0.04)` | Hairline lift |
| sm | `0 1px 3px rgb(0 0 0 / 0.06), 0 1px 2px -1px rgb(0 0 0 / 0.04)` | Subtle elevation |
| card | `0 2px 8px -2px rgb(0 0 0 / 0.08), 0 1px 2px -1px rgb(0 0 0 / 0.04)` | Default card |
| hover | `0 8px 16px -4px rgb(0 0 0 / 0.10), 0 2px 4px -2px rgb(0 0 0 / 0.04)` | Elevated on interaction |

Dark mode shadows are more pronounced (~3–5× opacity) to maintain perceived depth.

---

## 6. Components

### Buttons

- **Shape**: Pill (`rounded-full`)
- **Font**: 14px semibold
- **Sizes**: lg `h-11 px-6` / default `h-10 px-5` / sm `h-8 px-4` / icon `h-10 w-10`

| Variant | Background | Text | Use |
|---|---|---|---|
| Default | Shark Blue | White | Primary actions |
| Outline | White | Primary text | Secondary actions |
| Secondary | Secondary bg | Primary text | Neutral actions |
| Ghost | Transparent | Primary text | Tertiary actions |
| Destructive | Loss Red | White | Irreversible actions |
| Link | Transparent | Shark Blue + underline | Inline links |

### Cards

- Background: white
- Border: 1px `--border` (blue-tinted)
- Border radius: 16px
- Shadow: `shadow-card`
- Padding: `p-6` (default), `p-3` (stat cards)

### Chips & Pills

| Variant | Background | Text | Usage |
|---|---|---|---|
| Selected | Blue tint | Shark Blue, semibold | Active filter |
| Profit | Profit tint | Profit green | Positive sessions |
| Loss | Loss tint | Loss red | Negative sessions |
| Neutral | Secondary bg | Secondary text | Default state |

### Financial Display

- Always use `src/lib/formatMoney.ts` — never format currency inline
- Profit values: `text-profit` (green), prefix `+`
- Loss values: `text-loss` (red), prefix `-`
- Neutral zero: secondary text, no prefix

---

## 7. Iconography

**Library**: [Lucide React](https://lucide.dev/) — used for all product UI icons.

| Context | Icon color |
|---|---|
| Default UI | Primary text / secondary text |
| Meta / timestamps | `hsl(217 60% 65%)` (blue-tinted gray) |
| Profit indicators | Profit green |
| Loss indicators | Loss red |
| Notifications | Orange accent |

Icon sizes follow the containing text size. Use `strokeWidth={1.5}` for a refined appearance on larger icons.

---

## 8. Motion & Animation

### Principles

- Animations should feel **native and physical**, not decorative
- Duration: 120–300ms range; nothing slower than 300ms for UI transitions
- Easing: `cubic-bezier(0.25, 0.46, 0.45, 0.94)` (ease-out) for enters; `ease-in` for exits
- Respect `prefers-reduced-motion`

### Core Animations

| Name | Behavior | Duration |
|---|---|---|
| `fade-in` | Opacity 0 → 1 | 150ms ease-out |
| `slide-up` | translateY(8px) → 0 + fade | 200ms ease-out |
| `scale-in` | scale(0.98) → 1 + fade | 120ms ease-out |
| Page transition | Fade + slide up 6px | 200ms |
| Sheet enter | translateY(100%) → 0 | 300ms `cubic-bezier(0.32, 0.72, 0, 1)` |
| Sheet exit | 0 → translateY(100%) + fade | 250ms |

### Interaction Feedback

- Touch targets: `touch-action: manipulation`, `-webkit-tap-highlight-color: transparent`
- Press states: CSS transform via `Pressable` component (scale/opacity) — **not** global `:active` rules
- Hover: subtle shadow elevation + color transition

---

## 9. Layout & Platform

### Mobile-First

- Primary target: iOS (Capacitor standalone app)
- Routing: `HashRouter` — do not change (required for iOS back-swipe)
- Page transitions disabled in standalone/PWA mode (OS handles swipe navigation)

### Safe Areas (iOS)

| Variable | Value |
|---|---|
| `--safe-bottom` | `env(safe-area-inset-bottom, 0px)` |
| `--safe-top` | `env(safe-area-inset-top, 0px)` |
| `--tabbar-h` | 49px |
| `--composer-h` | 56px |

All bottom-anchored UI (tab bar, CTAs, sheets) must account for `--safe-bottom`.

### Navigation

- Bottom tab bar, Strava-style with active underline (2px Shark Blue)
- Tabs use `border-b-2 border-primary` pattern for the active indicator

---

## 10. Voice & Writing Style

- **Concise**: Labels, headers, and tooltips should be as short as possible
- **Direct**: "Add session", not "Click here to add a new session"
- **Data-forward**: Lead with numbers where possible ("$1,240 profit this month")
- **Friendly but not casual**: Avoid slang; poker players are competitive and serious
- **Present tense**: "3 sessions this week", not "You have logged 3 sessions"

---

## 11. Do's & Don'ts

| Do | Don't |
|---|---|
| Use Shark Blue for primary interactive elements | Use multiple competing accent colors |
| Pair green/red only with financial data | Use semantic colors decoratively |
| Use pill-shaped buttons | Use squared-off buttons |
| Keep shadows subtle and purposeful | Stack multiple shadows on one element |
| Blue-tint borders and separators | Use pure gray (`#E5E7EB`) borders |
| Format all money via `formatMoney.ts` | Inline currency formatting |
| Use Lucide icons consistently | Mix icon libraries |
| Respect safe areas on iOS | Let UI bleed into the home indicator zone |
