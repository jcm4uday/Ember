# Iteration 2 — Networked Audio Session

## Intent
Validate that Ember can reliably stream audio to a backend service and play
returned audio responses within a clearly bounded session.

This iteration exists to prove connectivity, timing, and session discipline —
not intelligence or robustness.

## Context & Constraints
- Communication occurs over WebSockets
- Sessions are explicitly initiated and short‑lived
- Wi‑Fi connectivity may be unstable or slow
- Backend behavior is intentionally minimal (echo or canned response)

Latency, clarity, and failure visibility are more important than throughput.

## Assumptions
- Audio can be chunked and streamed without noticeable degradation
- WebSocket connection setup time is acceptable for Ember’s interaction model
- Backend responses will be audio, not semantic instructions
- Network errors will be common and must be observable

These assumptions will be tested implicitly.

## Design Decisions
- Use a session‑scoped WebSocket connection:
  connect → stream → receive → disconnect
- Keep the protocol explicit and minimal:
  audio chunks + simple control messages
- Separate concerns:
  audio capture, streaming, and playback are distinct components
- Reflect network state transitions via LEDs

Simplicity is preferred over efficiency.

## Explicit Non‑Goals
- No speech recognition or intent handling
- No retry queues or offline buffering
- No persistent connections
- No attempt to hide network failures from the user

Failure should be visible, not masked.

## Implementation Notes
- Audio is captured locally and sent in fixed‑size chunks
- Each chunk includes minimal metadata (format, sequence)
- Backend responses are treated as opaque audio data
- Session teardown is explicit, even on error
- LED states reflect:
  connecting, streaming, receiving, error

Logging is prioritized over graceful recovery.

## Observations (Expected)
- Connection setup time contributes noticeably to perceived latency
- Chunk size has a visible impact on smoothness and responsiveness
- Network failures are more disruptive than audio issues
- Clear LED feedback significantly improves user understanding

These observations will guide later refinement.

## Risks & Open Questions
- What is the acceptable upper bound for round‑trip latency?
- Should audio be compressed in later iterations?
- How much protocol complexity is justified?
- How aggressively should sessions fail fast?

These questions are intentionally left open.

## Reflection
This iteration introduces uncertainty from outside the device.
Ember should remain calm and predictable, even when the network is not.

A session that fails clearly is preferable to one that fails silently.
