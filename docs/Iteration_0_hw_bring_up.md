# Iteration 0 — Hardware Bring‑Up

## Intent
Validate that Ember’s core hardware components can be reliably controlled from Python.
This iteration exists to establish confidence in the physical and driver layer before any
user experience or system behavior is introduced.

## Context & Constraints
- Target platform is Raspberry Pi 4
- Development is done directly on the device
- Audio input via ReSpeaker 4‑mic array
- Audio output via I2S DAC and speaker
- Visual feedback via a WS2812B LED ring

At this stage, stability and observability are more important than performance or elegance.

## Assumptions
- The microphone array will expose a stable ALSA capture device
- I2S audio playback can coexist with microphone capture
- WS2812B LEDs can be driven from userspace without strict timing constraints at low LED counts
- Python is sufficient for all control paths in this iteration

These assumptions are expected to be challenged later.

## Design Decisions
- Interact with audio devices directly through ALSA rather than higher‑level audio servers
- Keep all hardware interactions explicit and manually triggered
- Avoid background services or auto‑start behavior
- Prefer simple, blocking calls over concurrency

The goal is clarity, not throughput.

## Explicit Non‑Goals
- No networking of any kind
- No power management or battery awareness
- No persistent services or system integration
- No attempt at a cohesive user experience

If something feels “product‑like” here, it is likely premature.

## Implementation Notes
- Audio capture is tested with short, fixed‑length recordings
- Audio playback uses a known test sound for repeatability
- LED control is limited to basic color changes and on/off states
- Each subsystem is exercised independently before being combined

The implementation favors testability over reuse.

## Observations
- Audio devices may enumerate differently across reboots
- Volume levels vary more than expected between playback tests
- LED updates are visually responsive, even with simple blocking calls

These observations suggest the need for more explicit device identification and
calibration in later iterations.

## Risks & Open Questions
- How reliable is long‑term ALSA device identification?
- Will audio capture and playback conflict under sustained use?
- At what LED count or update rate does timing become an issue?

These questions are intentionally deferred.

## Reflection
Iteration 0 felt intentionally uneventful.
That calm is reassuring.

Nothing happens unless Ember is explicitly asked to act.
This aligns with Ember’s guiding principle:

> *“Ember is a quiet companion that listens when invited, responds with care, and rests when its work is done.”*
