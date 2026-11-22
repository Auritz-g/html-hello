---
name: Autonomous Operations Console
colors:
  surface: '#0b1326'
  surface-dim: '#0b1326'
  surface-bright: '#31394d'
  surface-container-lowest: '#060e20'
  surface-container-low: '#131b2e'
  surface-container: '#171f33'
  surface-container-high: '#222a3d'
  surface-container-highest: '#2d3449'
  on-surface: '#dae2fd'
  on-surface-variant: '#bdc8d1'
  inverse-surface: '#dae2fd'
  inverse-on-surface: '#283044'
  outline: '#87929a'
  outline-variant: '#3e484f'
  surface-tint: '#7bd0ff'
  primary: '#8ed5ff'
  on-primary: '#00354a'
  primary-container: '#38bdf8'
  on-primary-container: '#004965'
  inverse-primary: '#00668a'
  secondary: '#bdc2ff'
  on-secondary: '#131e8c'
  secondary-container: '#2f3aa3'
  on-secondary-container: '#a8afff'
  tertiary: '#4ee6aa'
  on-tertiary: '#003825'
  tertiary-container: '#22c990'
  on-tertiary-container: '#004e35'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#c4e7ff'
  primary-fixed-dim: '#7bd0ff'
  on-primary-fixed: '#001e2c'
  on-primary-fixed-variant: '#004c69'
  secondary-fixed: '#e0e0ff'
  secondary-fixed-dim: '#bdc2ff'
  on-secondary-fixed: '#000767'
  on-secondary-fixed-variant: '#2f3aa3'
  tertiary-fixed: '#68fcbf'
  tertiary-fixed-dim: '#45dfa4'
  on-tertiary-fixed: '#002114'
  on-tertiary-fixed-variant: '#005137'
  background: '#0b1326'
  on-background: '#dae2fd'
  surface-variant: '#2d3449'
typography:
  display-lg:
    fontFamily: Geist
    fontSize: 2.25rem
    fontWeight: '600'
    lineHeight: 2.75rem
    letterSpacing: -0.03em
  display-lg-mobile:
    fontFamily: Geist
    fontSize: 1.75rem
    fontWeight: '600'
    lineHeight: 2.25rem
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Geist
    fontSize: 1.5rem
    fontWeight: '600'
    lineHeight: 2rem
    letterSpacing: -0.02em
  headline-sm:
    fontFamily: Geist
    fontSize: 1.125rem
    fontWeight: '500'
    lineHeight: 1.5rem
    letterSpacing: -0.01em
  body-lg:
    fontFamily: Geist
    fontSize: 1rem
    fontWeight: '400'
    lineHeight: 1.5rem
    letterSpacing: 0em
  body-md:
    fontFamily: Geist
    fontSize: 0.875rem
    fontWeight: '400'
    lineHeight: 1.25rem
    letterSpacing: 0em
  body-sm:
    fontFamily: Geist
    fontSize: 0.75rem
    fontWeight: '400'
    lineHeight: 1rem
    letterSpacing: 0.01em
  metric-display:
    fontFamily: JetBrains Mono
    fontSize: 1.875rem
    fontWeight: '700'
    lineHeight: 2.25rem
    letterSpacing: -0.03em
  metric-display-mobile:
    fontFamily: JetBrains Mono
    fontSize: 1.5rem
    fontWeight: '700'
    lineHeight: 1.75rem
    letterSpacing: -0.02em
  code-md:
    fontFamily: JetBrains Mono
    fontSize: 0.8125rem
    fontWeight: '400'
    lineHeight: 1.25rem
    letterSpacing: 0em
  label-caps:
    fontFamily: JetBrains Mono
    fontSize: 0.6875rem
    fontWeight: '600'
    lineHeight: 0.875rem
    letterSpacing: 0.08em
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  gutter: 1rem
  gutter-lg: 1.5rem
  margin: 1rem
  margin-lg: 2rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 0.75rem
  space-lg: 1rem
  space-xl: 1.5rem
---

## Brand & Style

This design system delivers a mission-critical, enterprise-grade control center tailored for autonomous systems, infrastructure orchestration, and real-time telemetry oversight. The visual posture is calibrated for extreme operational clarity, low eye strain over long observation windows, and hyper-dense data consumption without sensory fatigue. 

The aesthetic is precision-engineered Modern Technical Minimalism blended with subtle cybernetic luminescence. High-contrast textual hierarchies provide effortless scanability across thousands of parallel metrics, while muted structural containment keeps attention focused entirely on machine states, anomaly detections, and algorithmic decisions. UI elements rely on fine structural delineation, atmospheric depth, and targeted spectral glows to prioritize human operator interventions.

## Colors

The palette is rooted in an abyss-depth slate schema designed specifically for low-light command center environments.

### Core Canvas & Structural Planes
- **Base Canvas (`slate-950`):** `#020617` serves as the singular canvas ground, absorbing visual noise and establishing maximum dynamic contrast for foreground data.
- **Surface & Cards (`slate-900`):** `#0F172A` defines containers, data tables, analytical modules, and persistent docks.
- **Interactive Surfaces & Hover (`slate-800`):** `#1E293B` provides visual state confirmation for hover states, selected rows, active tabs, and tertiary controls.
- **Borders & Dividers:** `#1E293B` creates clean, hairline structural grids with optional elevated borders using `#334155` for active card focus.

### Typography & Content
- **Primary Text (`slate-50`):** `#F8FAFC` for high-priority metrics, headers, critical alerts, and primary controls.
- **Secondary Text (`slate-400`):** `#94A3B8` for axis labels, table metadata, units, timestamps, and secondary descriptors.
- **Muted Data (`slate-600`):** `#475569` for disabled states, structural graph grids, and inactive indicators.

### Luminescent Accents & Telemetry
- **Primary Accent (Electric Sky):** `#38BDF8` signals autonomous thread activity, active pathways, and primary interactive affordances.
- **Secondary Accent (Neural Indigo):** `#818CF8` designates automated model inference, machine-learning pipeline clusters, and computational workloads.
- **Operational Status Indicators:**
  - **Nominal / Healthy (`emerald-400`):** `#34D399`
  - **Attention / Degradation (`amber-400`):** `#FBBF24`
  - **Critical Failure / Override (`rose-500`):** `#F43F5E`

## Typography

The typography strategy leverages **Geist** for crisp, neutral interface navigation and **JetBrains Mono** for all operational metrics, coordinates, status codes, and terminal outputs.

- **Numerical Uniformity:** All telemetry data points, sensor readouts, latency values, and tabular rows must use the monospaced label family to prevent layout jittering during real-time data streaming.
- **Categorical Precision:** `label-caps` must be applied in full uppercase for system subheadings, column keys, process IDs, and state chips to establish a structured, instrumentation-like hierarchy.
- **Weight Restraint:** Weights are restricted primarily to Regular (`400`) and Medium/Semi-Bold (`500`/`600`), reserving Bold (`700`) exclusively for primary numeric readouts.

## Layout & Spacing

The architecture enforces a strict 12-column fluid grid system engineered for ultra-dense monitor arrays and mobile failover devices.

### Layout Mechanics
- **Desktop (1440px+):** 12 columns with `1.5rem` gutters and `2rem` outer margins. Accommodates persistent left-rail telemetry, central visualizer canvas, and multi-tiered right-hand diagnostic panels.
- **Tablet / Workstation Auxiliary (768px - 1439px):** 8 columns with `1rem` gutters and `1.5rem` margins. Right diagnostic panels collapse into a drawer or bottom sheet.
- **Mobile (Below 768px):** 4 columns with `0.75rem` gutters and `1rem` margins. Modules reflow vertically in an absolute single-column stack with persistent status indicators anchored to the viewport header.

### Spatial Rhythm
Internal component layouts strictly follow a 4px incremental baseline (`space-xs: 4px`, `space-sm: 8px`, `space-md: 12px`, `space-lg: 16px`, `space-xl: 24px`). Compact row layouts (padding: `space-xs` vertical, `space-sm` horizontal) maximize viewport efficiency for mission-critical monitoring panels.

## Elevation & Depth

This system avoids soft, blurred, light-mode shadows in favor of precise **tonal layering**, **hairline edge definition**, and **luminescent atmospheric backdrops**.

### Depth Layers
- **Floor 0 (Canvas):** `#020617` — Ground environment.
- **Floor 1 (Containers & Panels):** `#0F172A` with a 1px solid border of `#1E293B`.
- **Floor 2 (Floating Popovers & Modals):** `#1E293B` with a 1px solid border of `#334155` and a deep, low-opacity drop shadow (`box-shadow: 0 16px 32px -8px rgba(0, 0, 0, 0.6)`).

### Luminescent Accents (Glow Engine)
Key indicators and active node nodes utilize directional optical diffusion rather than heavy physical elevations:
- **Active Node / Healthy Glow:** `0 0 12px -2px rgba(52, 211, 153, 0.35)`
- **AI / Primary Processing Focus:** `0 0 16px -2px rgba(56, 189, 248, 0.4)`
- **Critical Alert Beacon:** `0 0 20px -1px rgba(244, 63, 94, 0.5)`

## Shapes

The design system maintains a strict **Soft (`1`)** roundedness profile to project an architectural, instrument-like feel. 

- **Standard Elements (Buttons, Inputs, Metric Cells):** `0.25rem` (4px).
- **Cards, Panels, and Data Modules:** `0.5rem` (8px).
- **Floating Modals and Command Palettes:** `0.75rem` (12px).
- **Pill Shapes:** Strictly prohibited for general UI; reserved exclusively for circular network state nodes and real-time status micro-badges (using `9999px`).

## Components

### Buttons
- **Primary:** Background `#38BDF8`, text `#020617`, font weight `500`. Hover state triggers background `#7DD3FC` with a soft cyan edge radiance (`0 0 12px rgba(56, 189, 248, 0.4)`).
- **Secondary:** Background `#0F172A`, 1px solid border `#1E293B`, text `#F8FAFC`. Hover switches background to `#1E293B` and border to `#334155`.
- **Destructive / Abort:** Background `#F43F5E`, text `#FFFFFF`. Hover state: `#FB7185` with red edge radiance.
- **Sizing:** Compact padding (`0.375rem 0.75rem`), height 32px for enterprise dashboard density.

### Chips & Telemetry Badges
- Constructed with `#0F172A` fill and a 1px hairline border corresponding to the metric’s state color at 30% opacity.
- Incorporates a 6px circular pulse dot preceding text rendered in `label-caps`. 
- Padding: `0.125rem 0.5rem`.

### Input Fields & Search Bars
- Background: `#020617` inset within `#0F172A` cards; 1px solid border `#1E293B`.
- Typography: `body-md` in `#F8FAFC` with placeholder text in `#475569`.
- Focus state: Border transitions to `#38BDF8` with a subtle inset cyan glow (`0 0 0 1px #38BDF8`). Monospaced styling applied to command-line prompts and query syntax.

### Data Tables & Lists
- Table Header: Text in `label-caps`, secondary color `#94A3B8`, bottom border 1px solid `#1E293B`, no alternating row backgrounds.
- Row States: Default background transparent; hover background `#1E293B` with immediate 0ms transition. Active/Selected row indicated by a 2px left border strip of `#38BDF8`.
- Cell Padding: `0.5rem 0.75rem` strictly aligned to standard spacing bounds.

### Cards & Module Containers
- Solid `#0F172A` fill bounded by a 1px `#1E293B` hairline border.
- Header bands are delineated by a 1px horizontal separator in `#1E293B`, housing the module title in `headline-sm` alongside action icons and status counters.

### Checkboxes & Switch Controls
- Checkbox: 14x14px square, 2px radius, `#020617` background, 1px border `#334155`. Checked state fills with `#38BDF8` featuring an ink-slate check icon.
- Toggles: 28x16px track in `#1E293B` with a 12px circular pip in `#94A3B8`. Active switch track transitions to `#0369A1` with the pip turning `#38BDF8` and shifting 12px right.