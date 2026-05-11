# Iteration 1 — Local Voice Loop

## Intent
Validate a complete, local voice interaction loop without any networking.
This iteration exists to understand audio latency, quality, and basic interaction flow.

## Context & Constraints
- No backend connectivity
- Interaction triggered explicitly (button or manual trigger)
- Audio capture and playback occur on the same device
- Visual feedback limited to simple LED states

The device is still treated as a development platform, not a product.

## Assumptions
- Audio capture and playback can occur sequentially without contention
- Latency introduced by local buffering will be acceptable
- A simple interaction loop is sufficient to evaluate user feel

## Design Decisions
- Use a fixed recording window for simplicity
- Trigger recording explicitly rather than continuously listening
- Represent device state using minimal LED signals
- Keep all logic in a single execution flow

## Explicit Non‑Goals
- No speech recognition or interpretation
- No background listening
- No power optimization
- No concurrency beyond what is required for audio I/O

## Implementation Notes
- Audio is captured for a short, fixed duration
- Playback begins immediately after capture completes
- LEDs indicate listening and playback states only
- Errors are surfaced via logs, not user‑facing signals

## Observations
- Perceived latency may feel longer than expected
- Audio quality issues are easier to notice without networking noise
- LED timing must not interfere with audio playback

## Risks & Open Questions
- Will the fixed recording window feel restrictive?
- Is sequential capture/playback sufficient for later iterations?
- Should LED updates be fully non‑blocking?

## Reflection
This iteration should make Ember feel tangible for the first time.
Even without intelligence, the interaction should feel deliberate and calm.
