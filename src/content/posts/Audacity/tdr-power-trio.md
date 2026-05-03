---
title: The complete TDR "power trio" for mixing
updated: 2026-05-03
published: ""
description: Here's how Kotelnikov and SlickEQ differ from Nova
image: ""
tags:
  - Audacity
  - Guide
  - TDR
category: Guides
draft: false
date: 2026-05-03
---
# **The TDR Power Trio: What Each One Does**

| Plugin              | Type                   | Best For                                      | Character                                 |
| ------------------- | ---------------------- | --------------------------------------------- | ----------------------------------------- |
| **TDR Nova**        | Parallel Dynamic EQ    | Fixing problems, taming resonances, de-essing | Transparent, surgical, reacts to dynamics |
| **TDR Kotelnikov**  | Wideband Compressor    | Glue, leveling, controlling dynamics          | Transparent, precise, "stealthy"          |
| **TDR VOS SlickEQ** | Static EQ + Saturation | Tone shaping, adding color/air, analog vibe   | Musical, warm, adds harmonic mojo         |

**The golden rule**: Nova _fixes_ problems. Kotelnikov _controls_ dynamics. SlickEQ _colors_ and _shapes_ tone [gearspace.com](https://gearspace.com/board/music-computers/1215143-tokyo-dawns-tdr-nova-eq-vs-slick-eq.html).

## **1. TDR Kotelnikov — The Transparent Glue** 

Kotelnikov is a **mastering-grade wideband compressor**. Unlike Audacity's built-in compressor (which is basic), Kotelnikov is designed to control dynamics **without changing your tone**.

### **Key Features That Matter for Your Mix**

| Feature                 | What It Does                                                            | Why You Care                                     |
| ----------------------- | ----------------------------------------------------------------------- | ------------------------------------------------ |
| **Dual Release**        | Separate controls for Peak (fast transients) and RMS (sustained energy) | Snare crack stays punchy while body gets smooth  |
| **Sidechain High-Pass** | Prevents bass/kick from triggering compression                          | Stops low-end pumping on mix bus                 |
| **Stereo Linking**      | Controls how L/R channels interact                                      | Preserves your wide indie guitar stereo image    |
| **Delta Preview**       | Hears ONLY what the compressor is removing                              | Helps you avoid over-compression                 |
### **Where to Use It in Your Suno Mix**

**A. Mix Bus (Best Use)** — Add glue without killing the indie vibe

- **Threshold**: -18 to -24 dB
- **Ratio**: 1.5:1 to 2:1
- **Peak Release**: 40–80 ms (lets transients breathe)
- **RMS Release**: 150–250 ms (smooths the body)
- **Sidechain HP**: 80–100 Hz (prevents bass from ducking the whole mix)
- **Gain Reduction**: Aim for **1–3 dB max** on the loudest chorus[](https://www.michaelmusco.com/2026/03/tdr-kotelnikov-review.html)
    

**B. Drum Bus** — Tighten Suno's sometimes "fluffy" drum stems

- **Ratio**: 2:1
- **Peak Release**: 20–40 ms
- **RMS Release**: 100–150 ms
- **Sidechain HP**: Flat or 60 Hz (let the kick control the glue)
    

**C. Vocal** — After Audacity compressor, before Nova

- Use Kotelnikov for **gentle leveling** (2–4 dB reduction)
- Then use Nova for **frequency-specific** de-essing and tone shaping

**D. Bass** — Control the "boom" without killing the note

- **Ratio**: 3:1
- **Sidechain HP**: Flat (let the low end trigger compression for tightness)
- **Peak Release**: 10–30 ms

### **What NOT to Use It For**

- **Individual harshness removal** → Use Nova instead (Kotelnikov is wideband, not frequency-specific)
- **Adding color/saturation** → Use SlickEQ instead (Kotelnikov is proudly transparent)

## **2. TDR VOS SlickEQ — The Tone Shaper** 🎨

SlickEQ is a **musical static EQ** with built-in analog saturation. While Nova is surgical and dynamic, SlickEQ is about **vibe, character, and broad tone moves**

### **Key Features**

| Feature                    | What It Does                                                                               |
| -------------------------- | ------------------------------------------------------------------------------------------ |
| **4 EQ Modes**             | American (broad, punchy), British (aggressive mids), German (smooth), Soviet (edgy)        |
| **Saturation Stages**      | Linear (clean), Silky (open/air), Mellow (subtle warmth), Deep (odd harmonics, dimension)  |
| **Auto-Gain**              | Automatically compensates loudness when you boost/cut                                      |
| **M/S Mode**               | Process Mid and Side separately (great for indie width)                                    |
| **High Shelf up to 40kHz** | Adds "air" beyond human hearing that affects perceived brightness                          |

### **Where to Use It in Your Suno Mix**

**A. Guitars — Add Indie Rock "Mojo"**

- **Mode**: British or American
- **Low**: +2 dB at 100 Hz (girth)
- **Mid**: -1 to -2 dB at 400 Hz (remove boxiness)
- **High**: +3 dB at 8 kHz (shimmer)
- **Saturation**: **Silky** or **Deep** at low drive (adds harmonic richness)
- **Why**: Suno guitars can sound sterile; SlickEQ brings analog life
    

**B. Synth/Keyboard — Warm Up Digital Tones**

- **Mode**: German (smooth, expensive sounding)
- **Low**: High-pass at 80–120 Hz (remove mud)
- **High**: Shelf +2 to +4 dB at 12–16 kHz (air)
- **Saturation**: **Mellow** (subtle warming without obvious distortion)
    

**C. Bass — Add Grit and Definition**

- **Mode**: American
- **Low**: +2 dB at 80 Hz (weight)
- **Mid**: +2 dB at 800 Hz–1 kHz (string/pick attack)
- **Saturation**: **Deep** (adds odd harmonics that help bass cut through on small speakers)
    

**D. Mix Bus — Subtle Mastering Polish**

- **Mode**: German or American
- **Low**: +0.5 to +1 dB at 60 Hz (sub weight)
- **High**: +1 dB shelf at 12–16 kHz (mastering air)
- **Saturation**: **Silky** at very low drive (barely audible, just "opens" the mix)
- **Auto-Gain**: ON (essential for fair A/B comparison)
    

### **SlickEQ vs Nova: When to Choose Which?**

| Task                                                    | Use         | Why                                                   |
| ------------------------------------------------------- | ----------- | ----------------------------------------------------- |
| Harsh cymbal at 8 kHz that only appears on loud crashes | **Nova**    | Dynamic EQ only cuts when the harshness happens       |
| Guitar needs overall brightness and warmth              | **SlickEQ** | Static boost + saturation adds consistent character   |
| Vocal has a resonant peak at 3 kHz on certain words     | **Nova**    | Dynamic cut targets the problem precisely             |
| Mix needs "air" and analog glue on the master           | **SlickEQ** | High shelf to 40kHz + subtle saturation               |
| Bass has inconsistent low-end build-up                  | **Nova**    | Dynamic cut at 200 Hz that moves with the performance |
| Drums need overall punch and low-end weight             | **SlickEQ** | Broad low shelf + British mode aggression             |

## **3. Recommended Signal Chain for Your Suno Stems**

Now that you have all three TDR plugins, here's the optimal order:

### **Per-Track Chain**


```txt
[Suno Stem]
    ↓
[Audacity Compressor] — Basic punch/control (from earlier guide)
    ↓
[TDR Kotelnikov] — ONLY if the stem needs more transparent leveling
    ↓
[TDR Nova] — Fix harshness, dynamic resonances, de-essing
    ↓
[TDR SlickEQ] — Tone shaping, saturation, broad EQ moves
    ↓
[Panagement 2] — Stereo placement and reverb (always LAST)
```
### **Why This Order?**

1. **Compress first** (Audacity/Kotelnikov) to even out dynamics
2. **Fix with Nova** so dynamic thresholds are consistent
3. **Color with SlickEQ** so saturation doesn't get dynamically chopped by Nova
4. **Space with Panagement** so reverb isn't compressed or EQ'd unnaturally

## **4. Mix Bus Chain (The "Glue" Stage)**

On your **master track** in Audacity:


```txt
[TDR Kotelnikov] — Gentle bus compression (1.5:1, 1–2 dB GR)
    ↓
[TDR Nova] — Dynamic master EQ (tame harsh build-ups during loud choruses)
    ↓
[TDR SlickEQ] — Mastering tone (subtle air, Mellow saturation)
    ↓
[Audacity Limiter] — Catch peaks at -1 dBFS (if needed)
```
**Kotelnikov Mix Bus Settings**:

- Threshold: -20 dB
- Ratio: 1.5:1
- Peak Release: 60 ms
- RMS Release: 200 ms
- Stereo Link: 100%
- Sidechain HP: 80 Hz

## **5. Quick-Start Presets for Your Suno Project**

### **Indie Rock Guitar (Rhythm)**

1. **SlickEQ**: British mode, Low +2 dB @ 120 Hz, High +3 dB @ 6 kHz, Saturation: Silky
2. **Nova**: Dynamic cut -3 dB @ 3 kHz (tames AI harshness)
3. **Kotelnikov**: Skip (guitars need to breathe)

### **Suno Synth Pad**

1. **Nova**: Dynamic cut -4 dB @ 250 Hz, High shelf +2 dB @ 10 kHz
2. **SlickEQ**: German mode, High shelf +3 dB @ 12 kHz, Saturation: Mellow
3. **Kotelnikov**: Very gentle (2:1, 1 dB GR) if the pad swells unevenly
    
### **Drum Bus**

1. **Kotelnikov**: 2:1, Peak 30 ms, RMS 120 ms, Sidechain HP 80 Hz
2. **Nova**: Dynamic cut -3 dB @ 400 Hz, Dynamic boost +2 dB @ 3 kHz
3. **SlickEQ**: Skip (keep drums clean unless you want vintage vibe)

## **Summary: Which Plugin for Which Problem?**

| Problem                                     | Plugin                | Setting                           |
| ------------------------------------------- | --------------------- | --------------------------------- |
| "This cymbal hurts my ears on loud crashes" | **Nova**              | Dynamic bell cut @ 8 kHz          |
| "The mix feels flat and lifeless"           | **Kotelnikov**        | 1.5:1 mix bus compression         |
| "Suno guitars sound too digital/sterile"    | **SlickEQ**           | British mode + Silky saturation   |
| "Vocal has harsh 'esses' and whistling"     | **Nova**              | Dynamic cut @ 5–8 kHz             |
| "Bass lacks warmth and presence"            | **SlickEQ**           | Deep saturation + 800 Hz boost    |
| "The chorus gets muddy and harsh"           | **Kotelnikov + Nova** | Bus glue + dynamic 400 Hz cut     |
| "I want analog tape/vibe on the master"     | **SlickEQ**           | Mellow saturation, gentle shelves |

**Bottom line**: You now have a complete professional mixing toolkit from one developer. **Nova** is your doctor (fixes problems), **Kotelnikov** is your accountant (controls levels transparently), and **SlickEQ** is your artist (adds color and vibe). Use them together, and your Suno stems will sound like a real band in a real room.