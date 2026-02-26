# 🎛️ Noise Drum Wizard (V5)

An experimental, high-density web-audio drum machine that generates percussion entirely from filtered white noise. Built with the **Web Audio API**, it features a 6-lane sequencer, 4-pole resonant filters, and a tempo-synced feedback delay.



## ⚡ Key Features

### 4-Pole DSP Engine
Every sound is sculpted from pure white noise using high-precision filters.
* **48dB/octave filtering:** Four chained `BiquadFilterNodes` per lane create everything from sharp "pings" to industrial thuds.
* **Stereo Field:** Individual `StereoPannerNodes` per lane for wide, evolving textures.
* **Precision Envelopes:** Linear-to-exponential mapping supporting decays from 5ms clicks to 4-second ambient washes.

### High-Density Sequencer
* **Speed Divisions:** Set lanes to 1/16, 1/8, or 1/4 speed for complex polyrhythmic patterns.
* **Probability & Ratchets:** Per-step probability sliders and 1-4x ratcheting for glitch effects.
* **Pattern Evolution:** "Last Step" buttons allow for odd-meter loops (e.g., 7/16 or 5/8) per lane.
* **The Chaos Button:** A master randomizer that updates frequencies, steps, accents, and loop lengths instantly.

### Connectivity & FX
* **MIDI Clock Slave:** Sync to external hardware or DAWs (Ableton, Logic, etc.) via WebMIDI.
* **Dub Delay:** Tempo-synced feedback loop with a dedicated bandpass filter and safety-capped feedback gain.



---

## 🛠️ Control Reference

| Section | Control | Description |
| :--- | :--- | :--- |
| **Master** | `BPM` | Sets global tempo (40 - 240 BPM). |
| **Master** | `Accent` | Sets the volume multiplier for steps with 'A' active. |
| **Master** | `D-FB` | Delay Feedback - capped at 50% for musicality. |
| **Lane** | `Freq / Res` | Sets the center frequency and sharpness of the noise. |
| **Lane** | `MasterDec` | The global decay ceiling for the lane (up to 4s). |
| **Step** | `Decay %` | Multiplier of the Master Decay for that specific step. |
| **Step** | `A / L` | **A** (Accent) for volume boost, **L** (Last) to reset the loop. |

---

## 📥 Getting Started

1.  Clone the repository.
2.  Open `index.html` in any modern web browser (Chrome or Edge recommended for MIDI).
3.  Click **START** to initialize the Audio Context.

## Licence

No license - use it as you wish. If you break it, you have more pieces to play with.
