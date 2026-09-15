# 🎛️ Korg NTS-1 Modular Web Suite

> **⚠️ STATO DEL PROGETTO: PROTOTIPO / BETA PUBBLICA**  
> Questa suite è un progetto sperimentale open-source in fase di prototipo attivo e test continuo. Tutte le funzionalità, le interfacce e i motori algoritmici sono soggetti a miglioramenti, ottimizzazioni e rifiniture.

---

## 📖 Panoramica

La **Korg NTS-1 Modular Web Suite** è un ecosistema modulare di 4 micro-web app a pagina singola indipendenti, collegate da un Hub Centrale, progettate per la composizione algoritmica, l'arrangiamento metrico, la sintesi hardware e la riproduzione continua (focalizzata su sessioni di disegno, pittura, studio e relax).

La suite si interfaccia via **Web MIDI API** con il sintetizzatore hardware monofonico **Korg NTS-1** e include un motore di sintesi integrato basato su **Web Audio API** per l'utilizzo immediato anche senza sintetizzatore collegato.

### 🌟 Filosofia di Sviluppo
- **Zero Build Tools & Zero NPM**: Nessun compilatore, nessun bundler (Vite, Webpack, ecc.), nessuna dipendenza node_modules.
- **Pure Vanilla Web**: Solo HTML5, Vanilla JavaScript, Web Audio API, Web MIDI API e Tailwind CSS (via CDN).
- **Massima Portabilità Cross-Device**: Funziona direttamente aprendo i file nel browser (Chrome, Edge, Opera o browser compatibili Web MIDI) su PC, Mac, tablet e dispositivi mobili.
- **Interoperabilità Totale**: Formati standard aperti (.abc, .json, .wav, .txt).

---

## 🗂️ Struttura del Progetto & Repository

```text
korg-nts1-web-sequencer/
├── index.html                  # Hub Centrale & Diagnostica MIDI (v1.0.0)
├── abc-generator/
│   └── index.html              # Micro-App 1: ABC Generator & Arranger (v1.8.1)
├── abc-player/
│   └── index.html              # Micro-App 2: Standalone Player & Infinite Radio (v1.7.2)
├── playlist-builder/
│   └── index.html              # Micro-App 3: Playlist Builder & Patch Studio (v1.1.0)
├── jukebox-player/
│   └── index.html              # Micro-App 4: Zen Jukebox & Focus Companion (v1.8.0)
├── README.md                   # Questa documentazione
└── LICENSE                     # Licenza d'uso open-source
```

---

## 🚀 Le 4 Micro-Web App della Suite

### 1. Hub Centrale (`index.html` — v1.0.0)
- **Router Rapido**: Accesso diretto e descrittivo a ciascuna delle 4 micro-applicazioni.
- **Diagnostica MIDI**: Rilevamento automatico porte di output, selettore canale, invio note di test e accordi.
- **Pulsante PANIC Globale**: Sweep di sicurezza anti-hang (All Sound Off, All Notes Off, Sustain Off).
- **Guida Hardware Sinottica**: Riferimento rapido ai 9 oscillatori (CC 53) e ai controller fisici.

### 2. ABC Generator & Arranger (`abc-generator/index.html` — v1.8.1)
- **Motore Metrico Multilingua**: Analisi fonetica e sillabica per **Italiano** (trapezio vocalico), **Inglese** (dittonghi dinamici) e **Toki Pona** (metrica a 5 vocali).
- **Auto-Regeneration Reattiva**: Ricalcolo istantaneo dello spartito ABC alla modifica di genere, mood, BPM o testo.
- **Stato Auto-Match / Manuale**: Protezione delle impostazioni manuali senza sovrascritture involontarie.
- **Esportazione Multiformato**: Download diretto in `.abc`, `.mid` (Standard MIDI Formato 0), `.json` e `.wav` (PCM 16-bit 44.1 kHz via OfflineAudioContext).

### 3. Standalone Player & Generative Radio (`abc-player/index.html` — v1.7.2)
- **Doppia Modalità Operativa**: Player drag-and-drop di singoli file (.abc/.json) e **Radio Generativa Infinita**.
- **Composizione Armonica Modale Dinamica**: Cambio accordi per sezione (Strofa, Ritornello, Bridge) basato su matrici di genere (Dorian, Eolian, Pentatoniche, Hirajoshi).
- **4 Algoritmi Melodici**: Markov Dinamico, Euclidean Rhythms, Arpeggiatore Armonico Multi-Pattern e Scalar Wave Flow.
- **Master Presets Globali**: *🎨 Focus Pittura*, *⚡ Synthwave*, *☕ Deep Lo-Fi*, *🧪 Experimental Sound* con feedback visivo reattivo.
- **Session History Playlist**: Registrazione automatica di tutti i brani generati ed export in `playlist_nts1.json` per il Jukebox.
- **Visualizer a 8 Modalità & Pad Matrix**: Griglia Launchpad 4x3 cromatica reattiva, paesaggi montani synthwave, onde fluide, mandala e geometria isometrica.
- **Focus Companion & Timer Gigante**: Timer Pomodoro (con fade-out e campana tibetana) o cronometro libero, visualizzabili a schermo intero (Tasto **T**) o in modalità Zen (Tasto **H**).

### 4. Playlist Builder Studio (`playlist-builder/index.html` — v1.1.0)
- **Assemblatore Drag-and-Drop**: Caricamento in blocco di file `.json` e `.abc`.
- **Calcolo Durate Automatico**: Calcolo preciso delle durate al secondo per traccia e minutaggio cumulativo della scaletta.
- **Rack Hardware NTS-1 per Traccia**: Configurazione individuale di oscillatore (CC 53), Shape, Alt, Cutoff, Risonanza, Attack, Release, Delay e Riverbero.
- **Download Singolo Brano**: Scarica qualsiasi brano della scaletta in formato `.abc`, `.json` o audio renderizzato `.wav`.
- **Sommario Tracklist Disco**: Copia negli appunti o download in `.txt` della scaletta formattata tipo album.
- **Export Scaletta Jukebox**: Esportazione bundle interoperabile `playlist_nts1.json`.

### 5. Zen Jukebox Player (`jukebox-player/index.html` — v1.8.0)
- **Riproduzione Continua & Auto-Patch Switch**: Riprogrammazione timbrica automatica del Korg NTS-1 a ogni passaggio di brano.
- **Modalità di Esecuzione**: Sequenziale, Loop Playlist, Loop Singolo Traccia, Shuffle casuale.
- **Dado Humanize 🎲**: Micro-variazioni probabilistiche dal vivo su velocity, gate e salti d'ottava.
- **Download Singoli & Tracklist Album**: Download diretto di `.abc`, `.json` e `.wav` per ogni traccia dell'elenco, con copia/export della tracklist formattata in `.txt`.
- **Zen Mode True Edge-to-Edge**: Esperienza immersiva a schermo intero senza bordi, visualizer audio-reattivo e HUD semitrasparente.

---

## 🎹 Mappatura Hardware Korg NTS-1

### I 9 Motori di Sintesi (OSC Type — MIDI CC 53)
| CC 53 | Display | Nome Esteso | Carattere Sonoro Tipico |
| :---: | :---: | :--- | :--- |
| **0** | `SAW` | **Sawtooth** | Lead taglienti, bassi synthwave e rock |
| **16** | `tr 1` | **Triangle** | Caldo, vellutato, suoni jazz, flautati e lo-fi |
| **32** | `S9r` | **Square** | Onda quadra vintage, chiptune 8-bit, punk |
| **48** | `UPN` | **VPM (FM)** | Sintesi a modulazione di fase, campane, toni metallici |
| **64** | `WAVES` | **Waves** | Wavetable armonica, pad ed evoluzioni ambientali |
| **76** | `Volcano` | **Volca Bass** | 3 oscillatori analogici, acid bass e retrowave |
| **88** | `Chords` | **chord-osc** | Accordi polifonici su architettura monofonica |
| **100** | `Proba-b` | **Proba-B** | Generatore probabilistico, variazioni glitch e IDM |
| **112** | `J6` | **J6 (Juno-6)** | Emulazione Roland Juno con sub-oscillatore e chorus |

### Parametri CC Fisici
- **Knob A (OSC Shape)**: CC 54 (0–127)
- **Knob B (OSC Alt)**: CC 55 (0–127)
- **FILTER Cutoff**: CC 43 | **FILTER Resonance**: CC 44
- **EG Attack**: CC 16 | **EG Release**: CC 19
- **MOD FX Depth**: CC 29 | **DELAY Time**: CC 30 | **REVERB Mix**: CC 35
- **PANIC / Anti-Hang**: CC 120 (All Sound Off), CC 123 (All Notes Off), CC 64 (Sustain Off) + sweep su tutti i 128 tasti.

---

## 💾 Formati Dati Interoperabili

### 1. Pacchetto Traccia Singola (`.json`)
```json
{
  "generator": "Korg NTS-1 Suite - Infinite Radio",
  "version": "1.7.2",
  "timestamp": "2026-09-15T22:30:00.000Z",
  "metadata": {
    "title": "Radio - Chill Lo-Fi Study",
    "composer": "NTS-1 Infinite Radio",
    "meter": "4/4",
    "notes": "Generato con algoritmo markov"
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

### 2. Pacchetto Scaletta Multi-Traccia (`playlist_nts1.json`)
```json
{
  "type": "korg_nts1_playlist",
  "version": "1.0.0",
  "generator": "Korg NTS-1 Suite - Playlist Builder",
  "timestamp": "2026-09-15T18:30:00.000Z",
  "title": "Sessione Pittura NTS-1",
  "totalTracks": 2,
  "tracks": [
    {
      "title": "Midnight City Highway",
      "composer": "Autore",
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

## 🛠️ Requisiti di Sistema & Configurazione

1. **Browser Supportati**: Google Chrome, Microsoft Edge, Opera, Brave o qualsiasi browser basato su Chromium con supporto abilitato per **Web MIDI API** e **Web Audio API**.
2. **Collegamento Hardware (Opzionale)**:
   - Collega il tuo Korg NTS-1 al computer via porta Micro-USB (supporto MIDI-over-USB standard) o tramite interfaccia USB-MIDI su jack 3.5mm TRS Type-A.
   - All'apertura della suite nel browser, consenti l'accesso ai dispositivi MIDI quando richiesto.
3. **Uso Standalone (Senza Hardware)**:
   - Seleziona dal menu a tendina dell'Uscita Audio l'opzione **"Solo Casse PC / Mobile"** per ascoltare la musica tramite il sintetizzatore interno Web Audio.

---

## 📄 Licenza

Distribuito con licenza open-source MIT. Sentiti libero di utilizzare, modificare e contribuire allo sviluppo.