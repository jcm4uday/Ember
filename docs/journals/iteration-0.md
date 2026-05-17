## Iteration 0 Journal
### ALSA:
The Linux kernel’s built‑in audio driver layer that exposes microphones and speakers as devices you can open and read from.

Why this is ideal:

- No extra services running
- No latency overhead
- Device names are stable (hw:seeed4mic,0)
- Perfect for headless Pi setups

### ReSpeaker - Design decision
The Seeedstudio ReSpeaker 2-Mics Pi HAT is a dual-microphone expansion board for Raspberry Pi designed for AI and voice applications. You can build a more powerful and flexible voice product that integrates Amazon Alexa Voice Service, Google Assistant, and so on.

The reSpeaker 2-Mics Pi HAT is the voice user interface for Raspberry Pi Series, which has been equipped with 2 analog microphones and WM8960 Audio Codec for high-definition voice capture. Attach with NLU software algorithms and noise reduction algorithms, it has the abilities of Voice Activity Detection, Direction of Arrival, and Key Word Spotting, widely used in Voice Interaction applications.

[Seeed ReSpeaker Lite (2‑mic USB)](https://www.seeedstudio.com/ReSpeaker-2-Mics-Pi-HAT.html) it’s Seeed’s cheaper, simplified version.

Best for: simple voice capture, Home Assistant, small projects.

| Product                     | Mic Count | Interface | DSP / Beamforming | Pi HAT | Price Range | Best For |
|-----------------------------|-----------|-----------|--------------------|--------|-------------|----------|
| ReSpeaker 2‑Mic Pi HAT      | 2         | I2S       | No                 | Yes    | £10–£15     | Basic voice input on Pi |
| ReSpeaker 4‑Mic USB Array   | 4         | USB       | Yes                | No     | £40–£60     | Far‑field voice capture |
| Matrix Voice                | 7         | I2S/SPI   | Yes (FPGA)         | Yes    | £60–£90     | Advanced DSP + beamforming |
| MiniDSP UMA‑8               | 8         | USB       | Yes                | No     | £150–£200   | High‑quality multi‑mic capture |
| Adafruit Voice Bonnet       | 2         | I2S       | No                 | Yes    | £12–£20     | Simple Pi audio projects |
| Google AIY Voice Kit        | 2         | I2S       | No                 | Partial| £25–£40     | Beginner voice‑assistant kits |
| Keyestudio 2‑Mic Pi HAT     | 2         | I2S       | No                 | Yes    | £8–£12      | Budget Pi mic array |
| Anker PowerConf S3          | 6         | USB       | Yes                | No     | £80–£100    | Plug‑and‑play conference‑grade audio |

Ordered ReSpeaker 2‑Mic Pi HAT due to the price and use case. Have seen other ReSpeaker options that comes with ESP32 micro and firmware. In our case, firmware will be developed by us.
