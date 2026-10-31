# DESIGN

## Identity
A time card for a working studio: quiet neutral surfaces with a slight green-grey tint, and
the project's own color as the only strong color. A running project's card fills with that
color, so you can see what's on the clock from across the room.

## Type
- UI: Familjen Grotesk (fallback: system-ui)
- Timers and figures: Martian Mono, `tabular-nums`

## Color
Tokens are defined on `:root`, with dark values under `prefers-color-scheme` and `[data-theme]`.
Project colors (cobalt, teal, violet, orange, rose, olive, amber) carry white text on a
running card and work as dots and chips in both themes.

## Accessibility
- Buttons are real `<button>`s with a visible focus ring.
- Number keys 1–9 toggle projects.
- Motion is limited to a pulsing dot on running cards, which is turned off under `prefers-reduced-motion`.
