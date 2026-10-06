---
kind: pattern
---

# Bottom action bar

## Purpose

Pins the primary (and optional secondary) action to the bottom of a screen so it stays reachable while content scrolls.

## Composed of

- [Button](../components/button.md) — primary required; secondary optional

## Layout

- Full-width bar, padding `space.16`, gap `space.8` between buttons.
- Primary is full-width if it is the only action; if two actions, secondary left / primary right on LTR.
- Safe-area inset on devices with home indicators.

## Rules

- One primary action in the bar.
- Do not hide the bar behind keyboards without a way to submit (move bar above keyboard or provide an equivalent).
- Disabled primary still visible; explain why above the bar or in helper text.
