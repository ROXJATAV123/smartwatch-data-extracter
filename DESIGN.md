# Design Brief: Smart Data Extender

## Tone & Purpose
Technical data visualization dashboard for Bluetooth device debugging, GPS tracking, and comprehensive media/communication data extraction. Terminal UI and hex editor aesthetic with split-view raw-data/readable-preview pattern. Clinical-professional, precision-focused.

## Visual Identity
Deep technical dark theme (0.08 OKLCH L) with cyan/violet accents and 6 distinctive panel color indicators. Monospace mono typography for raw data, geometric sans-serif for UI labels. Stacked card layers with technical borders, no decorative effects.

## Color Palette
| Role | OKLCH | Usage |
|------|-------|-------|
| Background | 0.08 0 0 | Deep charcoal page foundation |
| Card | 0.12 0 0 | Elevated data container |
| Foreground | 0.95 0 0 | Primary text, high contrast |
| Accent | 0.75 0.18 142 | Cyan highlights, Bluetooth/GPS |
| Primary | 0.55 0.15 247 | Buttons, interactive (violet) |
| Muted | 0.2 0 0 | Secondary text, disabled |
| Border | 0.22 0.05 240 | Technical grid, dividers |
| Accent-Video | 0.7 0.16 32 | Video panel tab indicator (orange) |
| Accent-Audio | 0.75 0.17 142 | Audio panel tab (green-cyan) |
| Accent-Image | 0.68 0.21 310 | Image panel tab (magenta) |
| Accent-Call | 0.72 0.17 84 | Call Logs tab (amber-yellow) |
| Accent-Message | 0.68 0.18 178 | Message Logs tab (teal) |
| Accent-Notification | 0.6 0.21 20 | Notifications tab (red) |

## Typography
| Layer | Font | Scale | Weight | Purpose |
|-------|------|-------|--------|----------|
| Display | General Sans | 28–32px | 700 | Page titles |
| Body | General Sans | 14–16px | 400–500 | UI labels, nav |
| Mono | JetBrains Mono | 10–13px | 400 | Raw data, hex values |

## Structural Zones
| Zone | Treatment | Depth |
|------|-----------|-------|
| Header | bg-card, border-b border-border, tabs with colored underline | +1 |
| Content Split | Left hex/binary 35%, Right preview 65% | 0 |
| Sidebar | bg-background, border-r/l, sticky | 0 |
| Footer | bg-muted/10, border-t | -1 |

## Component Patterns
- **Hex Dump:** `hex-row` wraps bytes; `hex-cell` with accent text, row offsets
- **Split-View:** Left monospace raw data (hex/decimal/binary), right readable preview
- **Panel Tabs:** Each tab color-coded with distinctive accent; icon + label
- **Data Cells:** Uniform px-2/py-1, rounded-sm, subtle hover states
- **Status Indicators:** Pulse animation on active connection/stream

## Panels (8 total)
| Panel | Icon | Accent | Split View |
|-------|------|--------|------------|
| Bluetooth | ⚡ | Cyan | GATT tree left, device tree right |
| GPS | 📍 | Cyan | Hex dump left, map/coords right |
| Video | 🎬 | Orange | MP4 metadata left, player right |
| Audio | 🎵 | Green | MP3 metadata left, player right |
| Image | 🖼️ | Magenta | JPEG/PNG metadata left, thumbnail right |
| Call Logs | ☎️ | Amber | Byte dump left, call records right |
| Message Logs | 💬 | Teal | Message bytes left, message table right |
| Notifications | 🔔 | Red | Raw notification bytes left, notification list right |

## Spatial Composition
- **Density:** Compact 0.5rem gutters; technical density
- **Rhythm:** 2rem section gaps; 1rem intra-section; 4px cell padding
- **Split ratio:** 35% hex/raw left, 65% preview right

## Motion & Interaction
- **Transitions:** cubic-bezier(0.4, 0, 0.2, 1) for 0.3s
- **Status Pulse:** `animate-pulse` on active streams
- **Hover:** Byte cells → bg-accent/10; service nodes brighten
- **Tab Active:** Colored bottom border (panel accent color)

## Constraints
- No generic chart libraries; custom technical visualization
- No decorative gradients or blur; clarity required
- No shadows; rely on borders and color contrast
- Monospace strictly for byte values and technical data
- Panel colors used only for tab identification + highlights, never full backgrounds

## Signature Detail
**Bit-level precision + panel identity:** Every byte hex/decimal/binary with offsets. Each panel has distinctive tab accent color. Split-view shows raw bytes left, human-readable preview right. Live streams with timestamps and data rates.

## Assets
- Fonts: JetBrains Mono (data), General Sans (UI)
- Icons: Simple Unicode emoji in tabs
- No images; pure data visualization
