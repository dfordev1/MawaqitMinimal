# Mawaqit Minimal — Code Analysis

## Overview
This project is a single-file web app (`home.html`) that computes daily prayer times from astronomical formulas and displays a live countdown to the next prayer.

## Architecture
- **UI layer (HTML/CSS):** Fullscreen minimalist display with two text elements:
  - Current/next prayer name (`#pname`)
  - Countdown (`#cd`)
- **Logic layer (JavaScript):**
  - Julian date and solar position approximations (`jd`, `sun`)
  - Hour-angle based prayer time calculation (`ha`, `getPrayers`)
  - Human-readable countdown formatting (`humanCountdown`)
  - Rendering and animation loop (`render`, `transitionName`, `applySky`)

## Key Behaviors
1. Calculates prayer times for fixed coordinates (Srinagar, India).
2. Selects the next prayer based on current local time.
3. Updates every second.
4. Changes background/foreground palette by upcoming prayer.
5. In the final 60 seconds, shifts to an emphasized fullscreen countdown mode.

## Strengths
- Extremely lightweight: no framework or build tooling.
- Fast first paint and deterministic behavior.
- Clear visual hierarchy and smooth transitions.

## Limitations
- Coordinates are hard-coded (not user-configurable).
- No explicit madhhab/calculation-method options.
- Uses single-day calculation at load; does not auto-recompute exactly at midnight.
- No offline persistence, accessibility controls, or localization.

## Recommended Improvements
- Recompute prayer schedule at date rollover.
- Add configurable location input (and optional geolocation fallback).
- Support multiple calculation methods and juristic settings.
- Extract inline styles/scripts into separate files for maintainability.
- Add a small validation test harness for time calculations.
