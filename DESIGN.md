---
name: Autonomous Operations Console
colors:
  surface: '#f8f9ff'
  surface-dim: '#cbdbf5'
  surface-bright: '#f8f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#eff4ff'
  surface-container: '#e5eeff'
  surface-container-high: '#dce9ff'
  surface-container-highest: '#d3e4fe'
  on-surface: '#0b1c30'
  on-surface-variant: '#45464d'
  inverse-surface: '#213145'
  inverse-on-surface: '#eaf1ff'
  outline: '#76777d'
  outline-variant: '#c6c6cd'
  surface-tint: '#565e74'
  primary: '#000000'
  on-primary: '#ffffff'
  primary-container: '#131b2e'
  on-primary-container: '#7c839b'
  inverse-primary: '#bec6e0'
  secondary: '#0051d5'
  on-secondary: '#ffffff'
  secondary-container: '#316bf3'
  on-secondary-container: '#fefcff'
  tertiary: '#000000'
  on-tertiary: '#ffffff'
  tertiary-container: '#341100'
  on-tertiary-container: '#d95f00'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#dae2fd'
  primary-fixed-dim: '#bec6e0'
  on-primary-fixed: '#131b2e'
  on-primary-fixed-variant: '#3f465c'
  secondary-fixed: '#dbe1ff'
  secondary-fixed-dim: '#b4c5ff'
  on-secondary-fixed: '#00174b'
  on-secondary-fixed-variant: '#003ea8'
  tertiary-fixed: '#ffdbca'
  tertiary-fixed-dim: '#ffb690'
  on-tertiary-fixed: '#341100'
  on-tertiary-fixed-variant: '#783200'
  background: '#f8f9ff'
  on-background: '#0b1c30'
  surface-variant: '#d3e4fe'
typography:
  display:
    fontFamily: Hanken Grotesk
    fontSize: 3rem
    fontWeight: '700'
    lineHeight: '1.15'
    letterSpacing: -0.03em
  headline-lg:
    fontFamily: Hanken Grotesk
    fontSize: 2rem
    fontWeight: '600'
    lineHeight: '1.25'
    letterSpacing: -0.02em
  headline-lg-mobile:
    fontFamily: Hanken Grotesk
    fontSize: 1.5rem
    fontWeight: '600'
    lineHeight: '1.3'
    letterSpacing: -0.015em
  headline-md:
    fontFamily: Hanken Grotesk
    fontSize: 1.25rem
    fontWeight: '600'
    lineHeight: '1.4'
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Hanken Grotesk
    fontSize: 1.125rem
    fontWeight: '600'
    lineHeight: '1.4'
    letterSpacing: -0.005em
  body-lg:
    fontFamily: Inter
    fontSize: 1rem
    fontWeight: '400'
    lineHeight: '1.5'
    letterSpacing: 0em
  body-md:
    fontFamily: Inter
    fontSize: 0.875rem
    fontWeight: '400'
    lineHeight: '1.5'
    letterSpacing: 0em
  body-sm:
    fontFamily: Inter
    fontSize: 0.75rem
    fontWeight: '400'
    lineHeight: '1.4'
    letterSpacing: 0.005em
  label-code:
    fontFamily: JetBrains Mono
    fontSize: 0.75rem
    fontWeight: '500'
    lineHeight: '1.25'
    letterSpacing: -0.01em
  label-badge:
    fontFamily: Inter
    fontSize: 0.6875rem
    fontWeight: '600'
    lineHeight: '1'
    letterSpacing: 0.02em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 1.5rem
  gutter-mobile: 1rem
  margin: 2rem
  margin-mobile: 1rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2rem
---

## Brand & Style

This design system targets enterprise orchestrators, engineering leaders, and operations managers monitoring fleets of autonomous AI agents. The aesthetic is anchored in **Corporate / Modern** minimalism with high-density data legibility, restrained visual noise, and precision instrument cues. 

The interface evokes control, stability, and high operational throughput. Rather than generic SaaS neon or consumer-grade playful abstractions, the visual atmosphere communicates mission-critical software: clean vertical rhythms, balanced hierarchy, and distinct visual feedback for real-time autonomous execution states.

## Colors

The palette is rooted in a structured slate architecture, offering pure operational contrast between foreground glyphs and underlying surfaces.

- **Base Canvas & Text:** Light mode defaults to `#f8fafc` (slate-50) canvas with `#0f172a` (slate-900) primary text. Dark mode inverts to `#020617` / `#0f172a` (slate-950/900) canvas with `#f8fafc` (slate-50) text.
- **Accents:** 
  - Primary execution actions leverage `#0f172a` for authoritative, grounded CTAs.
  - Interactive highlights and analytics leverage `#2563eb` (blue-600).
  - Provisioning alerts, utilization spikes, and dynamic metrics use `#f97316` (orange-500).
- **Functional Status Tokens:**
  - **Healthy / Running:** `#16a34a` (green-600)
  - **Terminated / Critical:** `#dc2626` (red-600)
  - **Degraded / Queue Paused:** `#eab308` (yellow-500)
  - **Provisioning / Scaling:** `#f97316` (orange-500)
  - **Idle / Awaiting Task:** `#2563eb` (blue-600)
  - **Decommissioned / Offline:** `#64748b` (slate-500)

Never use saturated decorative gradients behind operational metrics. Keep color strictly assigned to state attribution, priority cues, and directional telemetry.

## Typography

The typography pairs **Hanken Grotesk** for clean, low-contrast structural headers, **Inter** for neutral, utilitarian body copy and interactive UI elements, and **JetBrains Mono** for model parameters, agent IDs, token meters, and JSON logs.

- **Tabular Figures:** All numeric displays (metrics, latencies, cost values, table counts) must enable font feature settings `'tnum'` (tabular figures) to prevent visual jitter during live telemetry refreshes.
- **Hierarchy Enforcers:** Header weights stay clamped between 600 and 700. Never exceed 700 weight to prevent visual blunting. Label tags and status badges are rendered in uppercase or title-cased tight geometry.

## Layout & Spacing

The layout is built on a responsive 12-column fluid grid system bounded by persistent shell scaffolding:
- **Collapsible Sidebar:** Fixed 260px expanded width; collapses down to 68px icon-only rail on desktop. Auto-drawer overlay below 1024px viewport width.
- **Top Utility Bar:** Fixed 60px height holding environment context, active workspace switcher, system heartbeats, and user credentials.
- **Canvas Scaling:**
  - **Desktop (1024px+):** 12-column grid, 24px (`space-lg`) gutters, 32px (`space-xl`) outer page padding.
  - **Tablet (768px - 1023px):** 6-column grid, 16px (`space-md`) gutters, 24px (`space-lg`) outer margins.
  - **Mobile (<768px):** Single-column stacked flow, 16px horizontal margins, 12px vertical gaps between interactive units.

## Elevation & Depth

Visual separation relies on a combination of low-contrast hairline borders (`slate-200` in light mode, `slate-800` in dark mode) and tiered ambient shadows tinted with slate. Avoid saturated drop shadows.

- **Flat/Subsurface (Base):** Cards sit flush on canvas with a 1px border (`slate-200` / `slate-800`).
- **Low Elevation (`shadow-sm`):** `0 1px 2px 0 rgb(15 23 42 / 0.05)`. Applied to resting metric cards, standard filter bars, and inactive panels.
- **Medium Elevation (`shadow-md`):** `0 4px 6px -1px rgb(15 23 42 / 0.08), 0 2px 4px -2px rgb(15 23 42 / 0.05)`. Used for interactive card states, focused table rows, and popovers.
- **High Elevation (`shadow-lg`):** `0 10px 15px -3px rgb(15 23 42 / 0.08), 0 4px 6px -4px rgb(15 23 42 / 0.04)`. Applied to flyout side panels, dropdown menus, and command palettes.
- **Modal Elevation (`shadow-xl`):** `0 20px 25px -5px rgb(15 23 42 / 0.1), 0 8px 10px -6px rgb(15 23 42 / 0.06)`. Reserved strictly for modal dialogs and agent provisioning overlays.

## Shapes

The design system maintains a balanced **Rounded (Level 2)** geometry:
- Default elements (buttons, inputs, status badges): `0.5rem` (8px).
- Surface cards and table outer wraps: `0.75rem` (12px).
- Modal overlays and slide-out sheets: `1rem` (16px).
- Small functional tags and pill counters: full capsule radius (`9999px`) where appropriate.

Sharp 0px edges are restricted only to embedded code blocks and terminal logs to maintain raw technical utility.

## Components

### Metric Cards
- **Base Surface:** Background `white` / dark `slate-900`, 1px border `slate-200` / `slate-800`, `shadow-sm`.
- **Accent Indicator:** A solid 4px wide left border inset along the vertical edge:
  - Active Compute: `#2563eb` (blue-600)
  - Monthly Spend/Rate: `#f97316` (orange-500)
  - Fleet Uptime: `#16a34a` (green-600)
  - Errors/Failures: `#dc2626` (red-600)
- **Inner Content:** Upper row displays metric title (12px uppercase slate-500) and optional icon. Primary value rendered in `Hanken Grotesk` 28px bold tabular numbers, with secondary trend percentage beneath.

### Tables & Data Grids
- **Header:** Sticky top, 40px height, background `slate-100/60` / dark `slate-900/60`, text 11px uppercase `slate-500`, border-bottom 1px solid `slate-200` / `slate-800`.
- **Row Styling:** Row height 48px to 56px. Transition on hover: background shifts to `slate-50` / dark `slate-800/50`.
- **Selection:** Checked rows receive `slate-100` / dark `slate-800` tint and 2px left border in `blue-600`.

### Status Badges
- **Form Factor:** Height 22px, padding 2px 8px, border-radius `9999px`, font size 11px, weight 600.
- **Variants:**
  - *Active:* `bg-green-50 text-green-700 border-green-200` (dark: `bg-green-950/40 text-green-400 border-green-800`)
  - *Error:* `bg-red-50 text-red-700 border-red-200` (dark: `bg-red-950/40 text-red-400 border-red-800`)
  - *Warning:* `bg-yellow-50 text-yellow-700 border-yellow-200` (dark: `bg-yellow-950/40 text-yellow-400 border-yellow-800`)
  - *Provisioning:* `bg-orange-50 text-orange-700 border-orange-200` (dark: `bg-orange-950/40 text-orange-400 border-orange-800`)
  - *Idle:* `bg-blue-50 text-blue-700 border-blue-200` (dark: `bg-blue-950/40 text-blue-400 border-blue-800`)
  - *Decommissioned:* `bg-slate-100 text-slate-600 border-slate-200` (dark: `bg-slate-800 text-slate-400 border-slate-700`)
- Badges include a 6px centered pulse indicator for live operational states.

### Buttons & Inputs
- **Primary Buttons:** `bg-slate-900 hover:bg-slate-800 text-white` (dark: `bg-slate-50 hover:bg-slate-200 text-slate-900`), 36px height, rounded-md, font size 14px, medium weight.
- **Secondary Buttons:** `bg-white hover:bg-slate-50 border border-slate-300 text-slate-700` (dark: `bg-slate-900 hover:bg-slate-800 border-slate-700 text-slate-200`).
- **Inputs:** 36px height, background `white` / dark `slate-900`, border 1px `slate-300` / dark `slate-700`. Focus state: 1px border `blue-600` with an outer ring of `2px solid rgba(37, 99, 235, 0.2)`.

### Collapsible Sidebar
- Compact mode: Displays central icon with high-contrast active pill indicator.
- Expanded mode: Icon alongside 14px medium labels, sub-group collapsible accordions, and a bottom docked workspace-tier badge with quick-switch controls.