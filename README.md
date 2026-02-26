# Filtered-Regret-Sequencer

Abandoned prototype...

A single-file, browser-based drum machine that generates percussion from **one shared white noise source** routed into **six band-pass “lanes”**. Each lane is driven by a **16-step x0x sequencer** with probability, ratchets, accent, and per-lane loop length (last-step). Optional **MIDI clock sync** (master or slave).

No samples. No assets. Just noise, filters, and poor decisions.

---

## Features

- **One noise source** feeding **6 lanes**
- Per lane:
  - **Steep band-pass** via cascaded filters (approx “48 dB-ish” slope feel)
  - Controls: **Freq, Q, Width, Decay, Level, Pan, Division**
  - **16 steps** with always-visible controls
- Per step:
  - **On/Off**
  - **Probability**
  - **Ratchet (1–4)**
  - **Accent**
  - **Last step** (sets lane loop length; next clock after last goes to step 1)
- Master:
  - **Tempo** (20–300 BPM)
  - **Volume**
  - **Accent amount** (boost applied to accented steps across all lanes)
  - **Tempo-synced delay** (dry/wet, feedback, feel: straight/dotted/triplet; filtered + softclipped feedback)
  - **Start / Stop** (Stop resets all lanes to step 1)
- **Randomize**: randomizes **all lane params + steps** (activation, probability, ratchet, accent, last-step)

---

## Ranges / Limits

- **Filter frequency:** 60 Hz → 5 kHz  
- **Lane decay max:** 0 → 500 ms  
- **Delay wet:** 0 → 50%  
- **Delay feedback:** 0 → 30% (internally clamped; feedback path is band-pass filtered + softclipped)

---

## Running it

### Quick (no MIDI)
Just open the `.html` file in a modern browser and press **Start**.  
Audio will only start after a user gesture because browsers hate fun.

### With MIDI (recommended: serve over localhost/https)
Most browsers require a **secure context** for WebMIDI.

## MIDI Sync

The app supports three sync modes:

Internal: uses its own clock (tempo knob)

MIDI Master: sends MIDI Clock + Start/Stop to selected output

MIDI Slave: listens for MIDI Clock + Start/Stop from selected input

## Notes:

Use Chrome/Edge for the least pain.

If MIDI devices don’t show up, confirm you’re on https:// or localhost, and that the browser has permission.

## UI Notes

The interface is intentionally minimal and dense.

Each step is a vertical stack:

step activator

probability slider

ratchet

last

accent

Lanes wrap responsively so steps remain usable on small screens (down to 4 steps per row on mobile).

## Persistence

State is stored in localStorage automatically, so your bad patterns survive page refreshes.

## Built With

Web Audio API

Web MIDI API (optional)

## License

No rights reserved - Do what you want with it, if you break it, you have more pieces.
