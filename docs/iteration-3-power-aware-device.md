# Iteration 3 — Power‑Aware Device

## Intent
Transform Ember into a realistic, battery‑friendly device by making power a
first‑class design concern.

## Context & Constraints
- Device operates on battery power
- Sessions must be short and intentional
- Idle behavior matters more than peak performance
- Hardware resources should be released aggressively

## Assumptions
- Most time will be spent idle
- Users will tolerate short wake‑up delays
- Power savings justify reduced responsiveness

## Design Decisions
- Introduce an explicit session lifecycle
- Initialize audio and networking only when needed
- Tear down resources immediately after use
- Limit LED brightness, duration, and frequency

## Explicit Non‑Goals
- No always‑listening behavior
- No advanced power‑state orchestration
- No background updates or syncing
- No attempt at maximum battery life

## Implementation Notes
- Battery state is read and logged
- Subsystems are activated lazily
- LEDs default to off unless needed
- Session boundaries are clearly defined in code

## Observations
- Power savings are most noticeable during idle
- Frequent initialization adds complexity but improves clarity
- Reduced LED usage significantly improves perceived calmness

## Risks & Open Questions
- How aggressive should teardown be?
- Are there race conditions during rapid wake/sleep?
- What power trade‑offs are acceptable for UX improvements?

## Reflection
This iteration defines Ember’s character.
Restraint becomes a feature, not a limitation.
