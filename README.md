# Ember

Ember is a portable, power‑conscious voice companion built on Raspberry Pi.

It captures audio through a multi‑microphone array, streams short voice sessions to a backend service, plays spoken responses through an I2S speaker, and uses a subtle LED ring for visual feedback. Ember is designed to stay quiet by default, waking only when invited and returning to rest once its task is complete.

**Personality:**  
*Ember is a quiet companion that listens when invited, responds with care, and rests when its work is done.*

This repository explores Ember through small, iterative builds — starting with simple hardware validation and evolving toward a session‑based, battery‑friendly voice device.

Design notes are written as technical design journals.
They capture intent, decisions, and learning rather than final specifications.

ember/
├── README.md
├── docs/
│   ├── iterations/
│   │   ├── iteration-0-hardware-bringup.md
│   │   ├── iteration-1-local-voice-loop.md
│   │   ├── iteration-2-networked-session.md
│   │   └── iteration-3-power-aware-device.md
│   ├── architecture.md
│   └── design-philosophy.md
├── src/

