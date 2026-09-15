# 🎛️ Korg NTS-1 Modular Web Suite

> **⚠️ PROJECT STATUS: PROTOTYPE / PUBLIC BETA**  
> This suite is an experimental, open-source prototype undergoing active development and testing. Features, user interfaces, and algorithmic sound generation routines are subject to continuous improvements and refinements.

---

## 📖 Overview

The **Korg NTS-1 Modular Web Suite** is a client-side, zero-dependency ecosystem consisting of 4 independent single-page micro-web applications orchestrated by a Central Hub. It is designed for algorithmic composition, metric and phoneme-based lyric arranging, hardware synthesizer sound-shaping, and uninterrupted playback tailored for painting, drawing, reading, and deep focus sessions.

The suite interfaces directly with the **Korg NTS-1** digital synthesizer via the **Web MIDI API** and features an internal polyphonic/monophonic synthesis engine powered by the **Web Audio API** for standalone use without external hardware.

---

## 🌟 Development Philosophy

* **Zero Build Tools & Zero NPM**: No Webpack, Vite, rollup, or `node_modules`. Download or clone and run directly in any modern browser.
* **Vanilla Web Stack**: Built purely with HTML5, Vanilla JavaScript (ES6+), Web Audio API, Web MIDI API, and Tailwind CSS (via CDN).
* **Cross-Device Portability**: Runs natively on desktops, laptops, tablets, and mobile devices equipped with Web MIDI / Web Audio compliant browsers.
* **Open Interoperability**: Clean import/export workflows supporting open standards: `.abc` (sheet music notation), `.json` (hardware patch bundles & playlists), `.wav` (offline-rendered 16-bit 44.1 kHz PCM audio), and `.txt` (album tracklists).

---

## 🗂️ Repository Structure

```text
korg-nts1-web-sequencer/
├── index.html                  # Central Hub, Router & MIDI Diagnostics (v1.0.0)
│
├── abc-generator/
│   └── index.html              # Micro-App 1: ABC Generator & Arranger (v1.8.1)
│
├── abc-player/
│   └── index.html              # Micro-App 2: Standalone Player & Infinite Radio (v1.7.2)
│
├── playlist-builder/
│   └── index.html              # Micro-App 3: Playlist Builder & Patch Studio (v1.1.0)
│
├── jukebox-player/
│   └── index.html              # Micro-App 4: Zen Jukebox & Focus Companion (v1.8.0)
│
├── README.md                   # Italian Documentation
├── README_EN.md                # English Documentation
└── LICENSE                     # Open-source MIT License
```

---

## 🚀 The Micro-Web Applications

### 0. Central Hub (`index.html` — v1.0.0)
* **Unified Application Launcher**: Visual cards routing into each dedicated subdirectory with real-time API capability indicators.
* **Live MIDI Diagnostic Bench**: Automatic detection of connected hardware interfaces, output port selector, and channel assignment (Channels 1–4).
* **Hardware Sound Test**: Quick frequency triggers (C3, C4, C5) and test chords played locally and transmitted over MIDI.
* **Global Panic Button**: Sends MIDI CC 120 (All Sound Off), CC 123 (All Notes Off), CC 64 (Sustain Off), sweeps all 128 note-off commands, and silences internal voices.
* **NTS-1 Hardware Cheat Sheet**: Visual reference for all 9 custom and native oscillator types and physical controller CC assignments.

---

### 1. ABC Generator & Arranger (`abc-generator/index.html` — v1.8.1)
* **Multilingual Metric & Phoneme Engine**:
  * **Italian**: Vowel trapezoid analysis, tonic accents, and flowing cadence distribution.
  * **English**: Compound diphthong detection (`oo`, `ee`, `igh`, `ea`, `ow`, `ou`) with dynamic syllable durations.
  * **Toki Pona**: Pure 5-vowel, 9-consonant minimalist syllabic arrangement.
* **Reactive Live Auto-Regeneration**: Instantly recalculates and renders the entire ABC score upon any change in genre, mood, tempo, or lyrics.
* **Transparent Auto-Match / Manual State**: Retains custom user timbre and oscillator choices without accidental automated overrides.
* **Multi-Format Export**: One-click downloads for `.abc`, standard MIDI Form 0 (`.mid`), bundle interoperability (`.json`), and offline-rendered 16-bit 44.1 kHz PCM `.wav`.

---

### 2. Standalone Player & Generative Radio (`abc-player/index.html` — v1.7.2)
* **Dual Operation Modes**: Drag-and-drop file player (`.abc` / `.json`) and continuous **Infinite Generative Radio**.
* **Dynamic Multi-Chord Modal Engine**: Generates real musical progression matrices across Verse, Chorus, and Bridge sections (e.g., Dorian `i-IV-v-i`, Synthwave `i-VI-VII-v`, Pop `I-V-vi-IV`, Blues `I7-IV7-V7`), avoiding single-note monotony.
* **4 Algorithmic Melodic Generators**:
  * *Dynamic Markov*: Probabilistic interval steps anchored to active bar chords with cadence tonic resolution.
  * *Euclidean Rhythms*: Mathematically distributed syncopated pulse patterns.
  * *Harmonic Arpeggiator*: Multi-octave directional arpeggios over triads and seventh chords.
  * *Scalar Flow*: Ascending/descending melodic wave contours.
* **Instant Master Presets**: One-click global setups with active LED feedback:
  * 🎨 *Painting & Zen Focus* (warm oscillators, dorian lo-fi, long-form structures).
  * ⚡ *Synthwave & Retrowave* (saw/volca bass, 16th-note syncopations, aggressive filters).
  * ☕ *Deep Lo-Fi Study* (soft triangle/chords, relaxed BPM, jazz cadences).
  * 🧪 *Experimental Sound* (FM synthesis, Proba-B glitch, Hirajoshi modal scales).
* **Session Playlist Recorder**: Automatically registers all generated songs into session history with live track count, memory clear option, and one-click export into standard `playlist_nts1.json` format for the Jukebox.
* **8-Mode Reactive Visualizer**: Includes a 4x3 Launchpad chromatic Pad Matrix, Synthwave landscape, fluid waves, isometric geometry, oscilloscope, frequency bars, radial mandala, and cosmic nebula.
* **Giant Focus Tracker Overlay**: Integrated Pomodoro timer (with Tibetan singing bowl chime and smooth audio fade-out) and stopwatch, viewable in a high-visibility fullscreen overlay (Hotkey: **T**) and Zen edge-to-edge mode (Hotkey: **H**).

---

### 3. Playlist Builder Studio (`playlist-builder/index.html` — v1.1.0)
* **Bulk Drag-and-Drop Staging**: Import multiple `.json` and `.abc` files simultaneously.
* **Accurate Duration Engine**: Real-time per-track duration and cumulative playlist runtime calculation based on actual track BPM and ABC meter tokens.
* **Per-Track Hardware Patch Rack**: Edit individual Korg NTS-1 synthesizer parameters per track: Oscillator (CC 53), Shape (CC 54), Alt (CC 55), Cutoff (CC 43), Resonance (CC 44), Attack (CC 16), Release (CC 19), Delay Time (CC 30), and Reverb Mix (CC 35).
* **Single Track Downloads from List**: Dedicated inline actions to download individual tracks as `.abc`, `.json`, or offline-rendered `.wav`.
* **Tracklist Summary Tool**: Copy to clipboard or export a formatted `.txt` album tracklist with track numbering, genre, BPM, individual runtimes, and total album length.
* **Interoperable Playlist Export**: Saves unified bundles in `playlist_nts1.json` format.

---

### 4. Zen Jukebox Player (`jukebox-player/index.html` — v1.8.0)
* **Continuous Playback with Auto-Patch Switching**: Transmits complete CC parameter dumps to the Korg NTS-1 immediately before each track starts, transforming hardware timbre automatically between songs.
* **Flexible Playback Logic**: Sequential, Playlist Loop, Single Track Loop, and Random Shuffle.
* **Live Humanize Dice 🎲**: Real-time probabilistic micro-variations on velocity ($\pm 12$), gate factors, and random octave displacements ($\pm 12$).
* **Per-Track Export & Tracklist Summary**: Download `.abc`, `.json`, or render `.wav` for any item in the active playlist; copy or download album summaries in `.txt`.
* **True Edge-to-Edge Zen Mode**: Borderless fullscreen visualizer (Hotkey: **H** to hide HUD, **T** to toggle giant timer) with persistent status showing Title, Genre, BPM, Active Oscillator, and elapsed/total duration.

---

## 🎹 Korg NTS-1 Hardware Mapping

### The 9 Synthesis Engines (OSC Type — MIDI CC 53)

| CC 53 Value | Display | Full Name | Type | Typical Sound Character |
| :---: | :---: | :--- | :---: | :--- |
| **0** | `SAW` | **Sawtooth** | Native | Bright, harmonic-rich, cutting leads & punchy bass |
| **16** | `tr 1` | **Triangle** | Native | Warm, smooth, mellow jazz, woodwinds & relaxing tones |
| **32** | `S9r` | **Square** | Native | Hollow vintage pulse, 8-bit chiptune & aggressive punk |
| **48** | `UPN` | **VPM (FM)** | Native | Phase modulation synthesis, metallic textures & bells |
| **64** | `WAVES` | **Waves** | Pre-installed | Harmonic wavetable, evolving ambient soundscapes & pads |
| **76** | `Volcano` | **Volca Bass** | Custom (*tweeeeeak*) | Triple-oscillator analog emulation, acid & retrowave |
| **88** | `Chords` | **chord-osc** | Custom (*hypercubed*) | Polyphonic chords on a monophonic engine (Knob A = chord) |
| **100** | `Proba-b` | **Proba-B** | Custom (*tweeeeeak*) | Stochastic/probabilistic generator, glitch & IDM textures |
| **112** | `J6` | **J6 (Juno-6)** | Custom (*tweeeeeak*) | Roland Juno emulation with sub-oscillator & lush chorus |

### Physical Controller MIDI CC Mapping

* **OSC Shape (Knob A)**: MIDI CC 54 (0–127)
* **OSC Alt (Knob B)**: MIDI CC 55 (0–127)
* **FILTER Cutoff**: MIDI CC 43 | **FILTER Resonance**: MIDI CC 44
* **EG Attack**: MIDI CC 16 | **EG Release**: MIDI CC 19
* **MOD FX Depth**: MIDI CC 29 | **DELAY Time**: MIDI CC 30 | **REVERB Mix**: MIDI CC 35
* **PANIC / Anti-Hang**: CC 120 (All Sound Off), CC 123 (All Notes Off), CC 64 (Sustain Off) + full 128-key Note-Off sweep.

---

## 💾 Interoperable Data Formats

### 1. Single Track Bundle (`.json`)
```json
{
  "generator": "Korg NTS-1 Suite - Infinite Radio",
  "version": "1.7.2",
  "timestamp": "2026-09-15T22:30:00.000Z",
  "metadata": {
    "title": "Radio - Chill Lo-Fi Study",
    "composer": "NTS-1 Infinite Radio",
    "meter": "4/4",
    "notes": "Generated with dynamic markov algorithm"
  },
  "genre": "lofi_study",
  "mood": "dreamy",
  "bpm": 78,
  "mainOsc": "16",
  "chorusOsc": "88",
  "patch": {
    "osc": 16,
    "shape": 64,
    "alt": 32,
    "cutoff": 75,
    "resonance": 20,
    "attack": 10,
    "release": 45,
    "delayTime": 25,
    "reverbMix": 30
  },
  "abcCode": "X: 1\nT: Radio - Chill Lo-Fi Study\nM: 4/4\nL: 1/8\nQ: 78\nK: C\n..."
}
```

### 2. Multi-Track Playlist Bundle (`playlist_nts1.json`)
```json
{
  "type": "korg_nts1_playlist",
  "version": "1.0.0",
  "generator": "Korg NTS-1 Suite - Playlist Builder",
  "timestamp": "2026-09-15T18:30:00.000Z",
  "title": "Painting Session NTS-1",
  "totalTracks": 2,
  "tracks": [
    {
      "title": "Midnight City Highway",
      "composer": "Author",
      "genre": "synthwave",
      "bpm": 125,
      "patch": {
        "osc": 76,
        "shape": 80,
        "alt": 35,
        "cutoff": 85,
        "resonance": 25,
        "attack": 5,
        "release": 40,
        "delayTime": 25,
        "reverbMix": 35
      },
      "abcCode": "X: 1\nT: Midnight City Highway\n..."
    }
  ]
}
```

---

## 🛠️ System Requirements & Setup

1. **Supported Browsers**: Google Chrome, Microsoft Edge, Opera, Brave, or any Chromium-based browser supporting **Web MIDI API** and **Web Audio API**.
2. **Hardware Connection (Optional)**:
   * Connect your Korg NTS-1 to your computer via Micro-USB (standard MIDI-over-USB class-compliant interface) or through an external USB-MIDI interface plugged into the 3.5mm TRS Type-A MIDI IN jack.
   * Allow browser permissions for MIDI devices when prompted.
3. **Standalone Operation (Without Hardware)**:
   * Switch the audio output dropdown to **"Internal Speakers Only"** to audition the music via the built-in Web Audio synthesis engine.

---

## 📄 License

Released under the open-source [MIT License](LICENSE). Feel free to use, modify, study, and contribute.