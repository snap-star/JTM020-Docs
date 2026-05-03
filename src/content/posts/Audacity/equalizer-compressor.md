---
title: Audacity Equalizer & Compressor
updated: 2026-05-03
published: 2026-05-03
description: Guide using compressor in audacity
image: ""
tags:
  - Audacity
  - Guide
  - Panagement
  - TDR
category: Guides
draft: false
date: 2026-05-03
---
# **AUDACITY BUILT-IN COMPRESSOR**

Audacity's compressor is a straightforward wideband compressor with lookahead, attack, release, and knee controls [Audacity Manual](https://manual.audacityteam.org/man/compressor.html). It's perfect for **gain staging and taming peaks** before you get surgical with TDR Nova.

## **How to Think About It**

Use Audacity's compressor for **broad dynamic control**, then use TDR Nova for **frequency-specific problems**. This two-stage approach gives you clean, controlled dynamics without over-processing.

## **Instrument-by-Instrument Settings**

## **1. VOCALS** 
**Goal**: Consistent level, intimate but controlled

| Parameter        | Setting       | Why                                       |
| ---------------- | ------------- | ----------------------------------------- |
| **Threshold**    | -18 to -14 dB | Catch the loud peaks, leave quiet breaths |
| **Ratio**        | 3:1 to 4:1    | Natural compression, not squashed         |
| **Attack**       | 2-5 ms        | Let transients through for clarity        |
| **Release**      | 40-80 ms      | Natural decay, no pumping                 |
| **Lookahead**    | 10 ms         | Smooth out without distortion             |
| **Knee Width**   | 2-4 dB        | Soft transition into compression          |
| **Make-up Gain** | +3 to +6 dB   | Compensate for volume loss                |

> **Workflow**: Apply this first to even out the vocal performance. Then use TDR Nova to tame harsh frequencies (see below).

## **2. DRUMS** 
**Goal**: Punchy, consistent, controlled transients
**Kick Drum**:

| Parameter     | Setting                                |
| ------------- | -------------------------------------- |
| **Threshold** | -12 to -8 dB                           |
| **Ratio**     | 4:1 to 6:1                             |
| **Attack**    | 5-10 ms (let the beater click through) |
| **Release**   | 20-40 ms                               |
| **Lookahead** | 5-10 ms                                |

**Snare Drum:**

| Parameter     | Setting      |
| ------------- | ------------ |
| **Threshold** | -10 to -6 dB |
| **Ratio**     | 3:1 to 5:1   |
| **Attack**    | 2-5 ms       |
| **Release**   | 30-50 ms     |

**Overheads/Room Mics:**

| Parameter     | Setting       |
| ------------- | ------------- |
| **Threshold** | -20 to -16 dB |
| **Ratio**     | 2:1 to 3:1    |
| **Attack**    | 10-20 ms      |
| **Release**   | 80-150 ms     |
> **Pro Tip**: For the drum bus, try Audacity's **"Beefy Master"** preset as a starting point, then adjust threshold to taste [audacity manual](https://manual.audacityteam.org/man/compressor.html).

## **3. BASS**

**Goal**: Tight, solid, controlled low-end

| Parameter     | Setting       | Why                                    |
| ------------- | ------------- | -------------------------------------- |
| **Threshold** | -16 to -12 dB | Catch note-to-note inconsistencies     |
| **Ratio**     | 4:1 to 6:1    | Bass needs firm control                |
| **Attack**    | 5-10 ms       | Preserve the initial pluck/pick        |
| **Release**   | 40-80 ms      | Match the tempo—shorter for fast songs |
| **Lookahead** | 5-10 ms       | Prevent distortion on low notes        |
| **Knee**      | 3-5 dB        | Smooth compression for sustained notes |

:::important
**Important**: Bass compression is about **consistency**, not loudness. If you hear pumping, raise the threshold or lengthen the release.
:::

## **4. GUITARS** 

**Goal**: Even strumming, controlled dynamics
**Rhythm Guitars (Clean/Indie):**

| Parameter     | Setting       |
| ------------- | ------------- |
| **Threshold** | -18 to -14 dB |
| **Ratio**     | 2:1 to 3:1    |
| **Attack**    | 5-10 ms       |
| **Release**   | 50-100 ms     |


**Distorted/Lead Guitars:**

| Parameter     | Setting      |
| ------------- | ------------ |
| **Threshold** | -12 to -8 dB |
| **Ratio**     | 3:1 to 4:1   |
| **Attack**    | 2-5 ms       |
| **Release**   | 40-80 ms     |

## **5. SYNTH & KEYBOARD** 

**Goal**: Controlled but expressive
**Synth Pads:**

| Parameter     | Setting       |
| ------------- | ------------- |
| **Threshold** | -20 to -16 dB |
| **Ratio**     | 2:1 to 3:1    |
| **Attack**    | 10-20 ms      |
| **Release**   | 100-200 ms    |

**Arpeggiators/Leads:**

| Parameter     | Setting       |
| ------------- | ------------- |
| **Threshold** | -16 to -12 dB |
| **Ratio**     | 3:1 to 4:1    |
| **Attack**    | 2-5 ms        |
| **Release**   | 40-80 ms      |

# **TDR NOVA — THE SURGICAL TOOL**
TDR Nova is a **parallel dynamic equalizer** [TDR Nova](https://www.tokyodawn.net/tdr-nova/music/). This means it can act as:

- A normal parametric EQ
- A dynamic EQ (compression only when frequencies get too loud)
- A multiband compresso
- A wideband compressor

**The key concept**: Each of the 4 bands has its own **dynamics processor** that only acts when that frequency range exceeds the threshold [TokyoDawn - Manuals](https://www.tokyodawn.net/labs/Nova/Manual.pdf).

## **Understanding the Interface**

| Section                     | What It Does                                      |
| --------------------------- | ------------------------------------------------- |
| **HP/LP Filters**           | High-pass and Low-pass filters (6-24 dB/octave)   |
| **Bands 1-4**               | 4 parametric bands (Bell, Low-shelf, High-shelf)  |
| **W-Band**                  | The "rest" of the signal not covered by bands     |
| **Threshold Button**        | Activates dynamics processing for that band       |
| **Split Button**            | Makes the band use its own independent compressor |
| **Sticky Mode** (Alt+Click) | Band ignores W-Band compression                   |

## **Instrument-by-Instrument TDR Nova Settings**

## **1. VOCALS** 

**Start with these bands:**

| Band          | Type       | Frequency  | Q         | Gain        | Dynamics                          |
| ------------- | ---------- | ---------- | --------- | ----------- | --------------------------------- |
| **HP Filter** | High-pass  | 80-100 Hz  | 12 dB/oct | —           | Off                               |
| **Band 1**    | Bell       | 200-250 Hz | 1.5       | -2 to -4 dB | **ON** (tame muddiness when loud) |
| **Band 2**    | Bell       | 2.5-4 kHz  | 2.0       | +2 to +4 dB | Off (presence boost)              |
| **Band 3**    | Bell       | 5-8 kHz    | 2.5       | -3 to -5 dB | **ON** (de-ess harsh sibilance)   |
| **Band 4**    | High-shelf | 12-16 kHz  | —         | +2 to +3 dB | Off (air/sheen)                   |
**Dynamic Settings for Problem Bands:**

- **Band 1 (Mud)**: Threshold -20 dB, Ratio 2:1, Attack 10ms, Release 100ms
- **Band 3 (Sibilance)**: Threshold -18 dB, Ratio 3:1, Attack 5ms, Release 50ms

:::note[Why Dynamic?]
The mud and harshness only get tamed when the singer gets loud on those specific notes. During quiet passages, the full tone remains natural.
:::

## **2. DRUMS** 

**Kick Drum:**

| Band          | Type      | Frequency  | Gain        | Dynamics                  |
| ------------- | --------- | ---------- | ----------- | ------------------------- |
| **HP Filter** | High-pass | 30-40 Hz   | —           | Off                       |
| **Band 1**    | Bell      | 50-60 Hz   | +3 to +5 dB | Off (sub boost)           |
| **Band 2**    | Bell      | 300-400 Hz | -3 to -5 dB | **ON** (boxiness control) |
| **Band 3**    | Bell      | 2-4 kHz    | +2 to +4 dB | Off (beater click)        |
| **Band 4**    | Low-pass  | 10-12 kHz  | —           | Off                       |
:::note[Dynamic on Band 2:]
**Dynamic on Band 2**: Threshold -22 dB, Ratio 2:1 — only cuts the boxiness when it gets excessive.
:::

**Snare Drum:**

| Band       | Type       | Frequency    | Gain        | Dynamics              |
| ---------- | ---------- | ------------ | ----------- | --------------------- |
| **Band 1** | Bell       | 150-200 Hz   | +2 to +3 dB | Off (body)            |
| **Band 2** | Bell       | 800 Hz-1 kHz | -2 to -3 dB | **ON** (ring control) |
| **Band 3** | Bell       | 3-5 kHz      | +3 to +5 dB | Off (crack)           |
| **Band 4** | High-shelf | 8-10 kHz     | +2 dB       | Off (brightness)      |

:::note[Drum Bus]
**Drum Bus (All Drums Together):** 
Use TDR Nova as a **multiband compressor**:
- Load preset **"4 Band Dyn"**
- Adjust thresholds so each band barely moves on the loudest hits
- This glues the kit together while preserving punch
:::

## **3. BASS** 

| Band          | Type       | Frequency      | Gain        | Dynamics                   |
| ------------- | ---------- | -------------- | ----------- | -------------------------- |
| **HP Filter** | High-pass  | 40-50 Hz       | —           | Off                        |
| **Band 1**    | Bell       | 80-100 Hz      | +2 to +4 dB | Off (fundamental)          |
| **Band 2**    | Bell       | 200-300 Hz     | -2 to -3 dB | **ON** (mud control)       |
| **Band 3**    | Bell       | 800 Hz-1.2 kHz | +2 to +3 dB | Off (definition)           |
| **Band 4**    | High-shelf | 4-6 kHz        | +3 to +5 dB | Off (string noise/clarity) |

:::note[Dynamic on Band 2:]
**Dynamic on Band 2**: Threshold -20 dB, Ratio 2:1 — only cuts when the low-mids get too thick.
:::

## **4. GUITARS** 

**Rhythm Guitars (Indie Jangle):**

| Band          | Type       | Frequency  | Gain        | Dynamics       |
| ------------- | ---------- | ---------- | ----------- | -------------- |
| **HP Filter** | High-pass  | 100-120 Hz | —           | Off            |
| **Band 1**    | Bell       | 200-300 Hz | -2 to -3 dB | **ON** (mud)   |
| **Band 2**    | Bell       | 1-2 kHz    | +1 to +2 dB | Off (presence) |
| **Band 3**    | Bell       | 3-4 kHz    | +2 to +3 dB | Off (bite)     |
| **Band 4**    | High-shelf | 8-10 kHz   | +2 to +4 dB | Off (shimmer)  |

**Lead/Texture Guitars:**

| Band       | Type | Frequency  | Gain        | Dynamics                |
| ---------- | ---- | ---------- | ----------- | ----------------------- |
| **Band 1** | Bell | 250-400 Hz | -3 to -4 dB | **ON**                  |
| **Band 2** | Bell | 2-3 kHz    | +2 to +4 dB | Off (cut through)       |
| **Band 3** | Bell | 4-6 kHz    | -2 to -3 dB | **ON** (tame harshness) |

## **5. SYNTH & KEYBOARD** 

**Synth Pads:**

| Band          | Type       | Frequency  | Gain  | Dynamics  |
| ------------- | ---------- | ---------- | ----- | --------- |
| **HP Filter** | High-pass  | 80-100 Hz  | —     | Off       |
| **Band 1**    | Bell       | 200-300 Hz | -2 dB | **ON**    |
| **Band 2**    | Bell       | 1-2 kHz    | +2 dB | Off       |
| **Band 3**    | Bell       | 4-5 kHz    | +3 dB | Off (air) |
| **Band 4**    | High-shelf | 10 kHz     | +4 dB | Off       |
**Arpeggiators:**

| Band       | Type | Frequency  | Gain  | Dynamics                        |
| ---------- | ---- | ---------- | ----- | ------------------------------- |
| **Band 1** | Bell | 300-500 Hz | -2 dB | **ON**                          |
| **Band 2** | Bell | 2-4 kHz    | +3 dB | Off (clarity)                   |
| **Band 3** | Bell | 6-8 kHz    | -3 dB | **ON** (tame digital harshness) |

## **THE COMBINED WORKFLOW**

Here's the recommended signal chain for each track:

:::important[Recomended:]
1. Audacity Compressor (broad dynamic control)
2. TDR Nova (surgical EQ and dynamic EQ)
3. Panagement 2 (stereo width and reverb)
:::

### **Step-by-Step Process:**

1. **Apply Audacity Compressor** first to even out the performance
2. **Listen for problems**: "The vocal gets muddy when loud" or "The snare ring is annoying on hard hits
3. **Open TDR Nova** and use the **spectrum analyzer** (blue display) to see where the problem frequencies are
4. **Set a band** on the problem frequency
5. **Click the Threshold button** to activate dynamics
6. **Adjust the threshold** so the yellow gain reduction meter only moves on the problematic notes
7. **Use the "EL Bypass"** button to A/B test (equal loudness bypass)

## **Pro Tips for Indie/Alt Rock**

### **1. The "Pumping Bass" Trick**
On the bass track, use TDR Nova's **W-Band** with fast attack/release as a subtle compressor, while keeping Band 1 (lows) in **Sticky Mode** (Alt+Click). This compresses the mids/highs for consistency while leaving the sub-bass untouched for maximum impact
### **2. Vocal De-essing Without a De-esser**
Instead of buying a de-esser, use TDR Nova Band 3 at 5-8 kHz with:

- Threshold: -20 dB
- Ratio: 3:1
- Attack: 5ms
- Release: 50ms

This only cuts the "sss" and "shh" sounds when they happe
### **3. Drum Bus "Crispiness"**
Load the **"LF Density"** preset on your drum bus. It dynamically boosts low-end when the kick hits and controls the overall density.

### **4. Parallel Compression with TDR Nova**
Set the **Dry Mix** knob to 50-70%. This blends the compressed signal with the original, giving you the punch of compression while retaining transients. Perfect for drums.


# **AUDACITY COMPRESSOR: Stem-by-Stem Settings**

Audacity's compressor is a straightforward **downward compressor**—it reduces peaks so you can turn everything up. The key is using different **attack/release times** for each instrument to shape the transients[audacity manual](https://manual.audacityteam.org/man/compressor.html)

### **1. DRUMS**

**Goal**: Punchy, controlled, but not lifeless

| Parameter        | Setting       | Why                                                   |
| ---------------- | ------------- | ----------------------------------------------------- |
| **Threshold**    | -18 to -24 dB | Catch most of the drum hits without over-compressing  |
| **Ratio**        | 3:1 to 4:1    | Moderate—keep the snare crack alive                   |
| **Attack**       | 2-5 ms        | Let the transient (stick hit) through before clamping |
| **Release**      | 40-80 ms      | Fast enough to recover before next hit                |
| **Knee**         | 3-6 dB        | Smooth transition, natural sound                      |
| **Make-up Gain** | +3 to +6 dB   | Bring back the level you compressed                   |
| **Lookahead**    | 1-2 ms        | Catch peaks without distortion                        |

:::tip
**Pro Tip**: If the kick and snare feel "squashed," increase attack to 8-10 ms. For more "room sound," slow release to 100-150 ms.
:::

### **2. BASS** 
**Goal**: Tight, consistent low-end that sits in the pocket

| Parameter        | Setting       | Why                                               |
| ---------------- | ------------- | ------------------------------------------------- |
| **Threshold**    | -20 to -26 dB | Bass is usually the loudest element in Suno stems |
| **Ratio**        | 4:1 to 6:1    | More aggressive—bass needs to be solid            |
| **Attack**       | 10-20 ms      | Let the initial pluck/pick attack through         |
| **Release**      | 80-150 ms     | Medium—prevent pumping but keep it tight          |
| **Knee**         | 6-10 dB       | Very soft knee for smooth bass riding             |
| **Make-up Gain** | +4 to +8 dB   | Bass often needs level boost after compression    |
|                  |               |                                                   |
|                  |               |                                                   |
|                  |               |                                                   |

:::tip
**Pro Tip**: If you hear the bass "breathing" (pumping), increase release to 200+ ms. For synth bass, use a faster attack (5-8 ms) to control the sub-bass boom.
:::

### **3. GUITAR** 

**Goal**: Even strums, controlled dynamics, maintain "air"

| Parameter        | Setting        | Why                                             |
| ---------------- | -------------- | ----------------------------------------------- |
| **Threshold**    | -16 to -22 dB  | Catch the loud strums                           |
| **Ratio**        | 2.5:1 to 3.5:1 | Light—guitars need to breathe in indie/alt rock |
| **Attack**       | 5-10 ms        | Preserve pick attack                            |
| **Release**      | 60-120 ms      | Medium—let chords ring naturally                |
| **Knee**         | 3-6 dB         | Natural transition                              |
| **Make-up Gain** | +2 to +5 dB    | Subtle level adjustment                         |
|                  |                |                                                 |

:::tip
**Pro Tip**: For clean/ambient guitars, use a slower attack (15 ms) and higher ratio (4:1) to create a "swelling" effect. For distorted guitars, compression is often unnecessary—Suno's AI usually compresses them already.
:::

### **4. SYNTH/KEYBOARD** 

**Goal**: Controlled pads, punchy leads, no muddiness

| Parameter        | Setting       | Why                                         |
| ---------------- | ------------- | ------------------------------------------- |
| **Threshold**    | -18 to -24 dB | Synths can have wide dynamic swings in Suno |
| **Ratio**        | 2:1 to 3:1    | Gentle—synths are already fairly consistent |
| **Attack**       | 5-15 ms       | Let the initial synth transient through     |
| **Release**      | 100-200 ms    | Slower—synths have long sustain             |
| **Knee**         | 6 dB          | Smooth for pad sounds                       |
| **Make-up Gain** | +2 to +4 dB   | Subtle boost                                |
|                  |               |                                             |

:::tip
**Pro Tip**: For arpeggiated synths, use a fast attack (2-3 ms) and medium release (50 ms) to even out the "machine gun" effect. For pads, slow attack (20 ms) lets the swell come through.
:::

### **5. VOCAL (Lead)** 

**Goal**: Intimate, upfront, every word audible

| Parameter        | Setting       | Why                                                    |
| ---------------- | ------------- | ------------------------------------------------------ |
| **Threshold**    | -20 to -26 dB | Catch all but the quietest whispers                    |
| **Ratio**        | 3:1 to 5:1    | Moderate—indie vocals need dynamics, not robot voice   |
| **Attack**       | 3-8 ms        | Fast enough to catch peaks, slow enough for consonants |
| **Release**      | 50-100 ms     | Medium—natural vocal decay                             |
| **Knee**         | 6-10 dB       | Soft knee for transparent compression                  |
| **Make-up Gain** | +4 to +8 dB   | Bring vocal forward in the mix                         |
|                  |               |                                                        |

:::tip
**Pro Tip**: Suno vocals can sound "flat" dynamically. Use **2-stage compression**: light compression here (3:1), then TDR Nova for dynamic EQ control (see below). If the vocal sounds "squashed," raise threshold to -16 dB and lower ratio to 2.5:1.
:::

### **6. BACKING VOCALS** 
**Goal**: Blend with lead, add width without competing

| Parameter        | Setting       | Why                                         |
| ---------------- | ------------- | ------------------------------------------- |
| **Threshold**    | -18 to -22 dB | Slightly more aggressive than lead          |
| **Ratio**        | 3:1 to 4:1    | More controlled—backing vox should sit back |
| **Attack**       | 5-10 ms       | Standard                                    |
| **Release**      | 80-150 ms     | Slightly longer for blend                   |
| **Make-up Gain** | +3 to +5 dB   | Level to sit under lead                     |

### **7. OTHERS/PERCUSSION** 
**Goal**: Tame sharp transients, add glue

| Parameter        | Setting       | Why                                   |
| ---------------- | ------------- | ------------------------------------- |
| **Threshold**    | -16 to -20 dB | Percussion can be peaky in Suno       |
| **Ratio**        | 2:1 to 3:1    | Light—keep the "live" feel            |
| **Attack**       | 1-3 ms        | Very fast—catch sharp percussion hits |
| **Release**      | 30-60 ms      | Fast—percussion is transient-heavy    |
| **Make-up Gain** | +2 to +4 dB   | Subtle                                |


# **TDR NOVA: Dynamic EQ Strategies**

TDR Nova is a **parallel dynamic equalizer**—it can act as a standard EQ, dynamic EQ, multiband compressor, or wideband compressor. For Suno stems, we'll use it to fix AI artifacts and add polish.

## **Key Concept: Dynamic vs Static EQ**

- **Static EQ**: Always cuts/boosts (like a normal EQ)
- **Dynamic EQ**: Only cuts/boosts when the frequency gets loud (like a smart compressor)

### **1. VOCAL (Lead) — "Air & Clarity" Setup** 

Suno vocals often sound slightly muffled or have harsh "AI sibilance." Use TDR Nova to add air dynamically.
**Band Setup** (4 dynamic bands + HP/LP):

| Band          | Type       | Freq    | Q        | Gain        | Dynamic | Threshold | Ratio | Attack | Release |
| ------------- | ---------- | ------- | -------- | ----------- | ------- | --------- | ----- | ------ | ------- |
| **HP Filter** | High Pass  | 80 Hz   | 24dB/oct | —           | OFF     | —         | —     | —      | —       |
| **Band 1**    | Bell       | 200 Hz  | 1.2      | -2 to -4 dB | **ON**  | -24 dB    | 2:1   | 20 ms  | 150 ms  |
| **Band 2**    | Bell       | 800 Hz  | 1.5      | -1 to -2 dB | **ON**  | -22 dB    | 1.5:1 | 15 ms  | 100 ms  |
| **Band 3**    | Bell       | 3.5 kHz | 0.8      | +2 to +4 dB | **ON**  | -26 dB    | 2:1   | 5 ms   | 80 ms   |
| **Band 4**    | High Shelf | 10 kHz  | —        | +3 to +6 dB | **ON**  | -28 dB    | 2:1   | 2 ms   | 100 ms  |


**What this does**:

- **HP Filter**: Removes rumble and mud from Suno's low-end buildup[tokdo dawn records](https://docs.tokyodawn.net/that-high-end-air/)
- **Band 1 (200 Hz)**: Dynamically reduces "boxiness" only when the vocal gets loud
- **Band 2 (800 Hz)**: Tames the "honk" that AI vocals often have
- **Band 3 (3.5 kHz)**: Adds presence and intelligibility dynamically
- **Band 4 (10 kHz)**: Adds "air" and breathiness only when the vocal is present
    
:::tip
**Pro Tip**: Set the spectrum analyzer to **"Out"** to see what the EQ is actually doing after dynamic processing.
:::

### **2. BASS — "Tight Low-End" Setup** 

Suno bass can be boomy or lack definition.

| Band          | Type      | Freq   | Q        | Gain        | Dynamic | Threshold | Ratio |
| ------------- | --------- | ------ | -------- | ----------- | ------- | --------- | ----- |
| **HP Filter** | High Pass | 35 Hz  | 24dB/oct | —           | OFF     | —         | —     |
| **Band 1**    | Bell      | 60 Hz  | 1.0      | +2 to +3 dB | OFF     | —         | —     |
| **Band 2**    | Bell      | 250 Hz | 1.2      | -3 to -5 dB | **ON**  | -20 dB    | 3:1   |
| **Band 3**    | Bell      | 800 Hz | 1.5      | +2 to +3 dB | OFF     | —         | —     |
| **Band 4**    | Low Pass  | 8 kHz  | 12dB/oct | —           | OFF     | —         | —     |


**What this does**:

- **60 Hz boost**: Adds sub-weight (only if your speakers can reproduce it)
- **250 Hz dynamic cut**: Removes "mud" only when the bass gets loud—keeps it clear in the mix
- **800 Hz boost**: Adds "string noise" and definition for indie rock clarity

### **3. DRUMS — "Punch & Crack" Setup** 

| Band          | Type       | Freq   | Q        | Gain        | Dynamic | Threshold | Ratio |
| ------------- | ---------- | ------ | -------- | ----------- | ------- | --------- | ----- |
| **HP Filter** | High Pass  | 30 Hz  | 24dB/oct | —           | OFF     | —         | —     |
| **Band 1**    | Bell       | 100 Hz | 1.0      | +2 dB       | OFF     | —         | —     |
| **Band 2**    | Bell       | 400 Hz | 1.5      | -2 to -3 dB | **ON**  | -22 dB    | 2:1   |
| **Band 3**    | Bell       | 3 kHz  | 0.8      | +2 to +4 dB | **ON**  | -24 dB    | 2:1   |
| **Band 4**    | High Shelf | 10 kHz | —        | +2 dB       | OFF     | —         | —     |

**What this does**:

- **100 Hz**: Boost kick drum weight
- **400 Hz dynamic cut**: Removes "boxiness" from snare/tom rings only when loud
- **3 kHz dynamic boost**: Adds "crack" to snare and "stick" to cymbals only when they hit—prevents harshness during quiet passages

### **4. GUITAR — "Shimmer & Body" Setup** 

| Band          | Type       | Freq    | Q        | Gain        | Dynamic | Threshold | Ratio |
| ------------- | ---------- | ------- | -------- | ----------- | ------- | --------- | ----- |
| **HP Filter** | High Pass  | 100 Hz  | 12dB/oct | —           | OFF     | —         | —     |
| **Band 1**    | Bell       | 200 Hz  | 1.2      | -2 dB       | **ON**  | -20 dB    | 1.5:1 |
| **Band 2**    | Bell       | 2.5 kHz | 1.0      | +2 to +3 dB | OFF     | —         | —     |
| **Band 3**    | High Shelf | 8 kHz   | —        | +3 dB       | **ON**  | -26 dB    | 2:1   |

**What this does**:

- **200 Hz dynamic cut**: Removes mud when strumming hard
- **2.5 kHz**: Adds "bite" and presence for indie rock
- **8 kHz dynamic shelf**: Adds shimmer/air only when the guitar is playing—prevents hiss during stops

### **5. SYNTH/PAD — "Space & Definition" Setup** 

| Band          | Type       | Freq   | Q        | Gain  | Dynamic | Threshold | Ratio |
| ------------- | ---------- | ------ | -------- | ----- | ------- | --------- | ----- |
| **HP Filter** | High Pass  | 120 Hz | 12dB/oct | —     | OFF     | —         | —     |
| **Band 1**    | Bell       | 300 Hz | 1.5      | -3 dB | **ON**  | -22 dB    | 2:1   |
| **Band 2**    | Bell       | 2 kHz  | 1.0      | +2 dB | OFF     | —         | —     |
| **Band 3**    | High Shelf | 12 kHz | —        | +4 dB | **ON**  | -28 dB    | 1.5:1 |

**What this does**:

- **300 Hz dynamic cut**: Removes "mud" from chord pads when they get loud
- **12 kHz dynamic shelf**: Adds "air" and sparkle that moves with the music—creates an evolving texture

### **6. MASTER BUS — "Glue & Polish" Setup** 

Use TDR Nova on your **master track** (after all individual processing) to glue the Suno stems together.

| Band       | Type       | Freq   | Q   | Gain        | Dynamic | Threshold | Ratio |
| ---------- | ---------- | ------ | --- | ----------- | ------- | --------- | ----- |
| **Band 1** | Bell       | 100 Hz | 0.8 | +1 dB       | OFF     | —         | —     |
| **Band 2** | Bell       | 400 Hz | 1.2 | -1 dB       | **ON**  | -20 dB    | 1.5:1 |
| **Band 3** | Bell       | 3 kHz  | 0.8 | +1 dB       | OFF     | —         | —     |
| **Band 4** | High Shelf | 12 kHz | —   | +1 to +2 dB | OFF     | —         | —     |
:::note[Wideband Compressor:]
**Wideband Compressor** (at the bottom of TDR Nova):

- **Threshold**: -18 dB
- **Ratio**: 1.5:1
- **Attack**: 10 ms
- **Release**: 100 ms
:::
    
:::warning[What This Does :]
- Gentle wideband compression glues the mix
- Dynamic cut at 400 Hz prevents "muddy build-up" during loud choruses
- Subtle high-shelf adds "mastering polish"
:::

:::tip[**Recommended Signal Chain per Track**]
For each stem, process in this order:
1. **Audacity Compressor** — Control dynamics, add punch
2. **TDR Nova** — Shape tone, fix frequency buildups dynamically
3. **Panagement 2** — Position in stereo field and add reverb (from previous guide)
:::

:::note[Why this order?]
Compress first to even out levels so TDR Nova's dynamic thresholds work consistently. Then place in the stereo field last so reverb and spatial effects don't get compressed unnaturally.
:::

## **Suno-Specific Troubleshooting**

| Problem                | Cause                             | Solution                                                         |
| ---------------------- | --------------------------------- | ---------------------------------------------------------------- |
| Vocals sound "robotic" | Over-compression in AI generation | Use light compression (2:1) and boost 8-12 kHz air with TDR Nova |
| Drums lack punch       | AI flattened transients           | Use fast attack (2 ms) in Audacity compressor to add "snap"      |
| Bass sounds "boomy"    | AI boosted sub-bass               | HP filter at 35-50 Hz, dynamic cut at 200-250 Hz                 |
| Guitars sound "thin"   | AI high-passed too aggressively   | Boost 100-200 Hz slightly, add 8 kHz air                         |
| Mix sounds "flat"      | No dynamic variation              | Use TDR Nova's dynamic bands to create "moving" EQ               |
| Harsh "digital" highs  | AI artifacts                      | Dynamic cut at 3-5 kHz with TDR Nova, gentle                     |


## **Quick Start: Copy-Paste Settings**

**Vocal Chain**:

1. Audacity Compressor: Threshold -22, Ratio 3.5:1, Attack 5ms, Release 80ms, Knee 6dB
2. TDR Nova: HP 80Hz, cut 200Hz dynamic, cut 800Hz dynamic, boost 3.5kHz dynamic, shelf 10kHz dynamic
3. Panagement 2: Center front, Width 90%, Wood reverb, 20% wet
    

**Drum Chain**:

1. Audacity Compressor: Threshold -20, Ratio 3:1, Attack 3ms, Release 60ms
2. TDR Nova: HP 30Hz, boost 100Hz, cut 400Hz dynamic, boost 3kHz dynamic
3. Panagement 2: Back center, Width 130%, Concrete reverb, 20% wet

# **TDR Nova Output Gain: The Complete Guide**

### **Understanding the "Output" Knob**

TDR Nova's **Output** control (at the bottom right of the interface) serves two purposes:

1. **Make-up Gain**: Compensates for level reduction caused by EQ cuts and dynamic compression
2. **Level Matching**: Lets you A/B compare with/without the plugin at equal loudness

## **How to Set Output Gain Correctly**

### **The "Gain Match" Method (Recommended)**

This is the professional way to set output gain:

| Step | Action                                                        | Why                                                |
| ---- | ------------------------------------------------------------- | -------------------------------------------------- |
| 1    | Bypass TDR Nova                                               | Hear the "before" sound                            |
| 2    | Note the peak level in Audacity's meter                       | Baseline reference                                 |
| 3    | Enable TDR Nova with your EQ settings                         | Hear the "after" sound                             |
| 4    | Adjust **Output** until peak level matches the bypassed level | Fair comparison                                    |
| 5    | Toggle bypass on/off repeatedly                               | EQ decisions should be based on tone, not loudness |

:::tip
**Pro Tip**: Our ears naturally prefer louder sounds. If your processed signal is even 1 dB louder, you'll think it sounds "better" when it might just be louder. Always match levels!
:::

## **Output Gain by Stem (Practical Settings)**

Based on the EQ settings I gave you earlier, here are **starting output gain values**:

| Stem                  | Typical Output Gain | Why                                                     |
| --------------------- | ------------------- | ------------------------------------------------------- |
| **Lead Vocal**        | **+2 to +4 dB**     | Heavy dynamic cuts at 200Hz/800Hz reduce overall level  |
| **Backing Vocal**     | **+1 to +3 dB**     | Similar to lead but less aggressive processing          |
| **Bass**              | **+1 to +2 dB**     | Moderate cuts, but sub-bass boost adds energy           |
| **Drums**             | **+2 to +4 dB**     | Dynamic cuts at 400Hz + boost at 3kHz often net neutral |
| **Guitar**            | **+2 to +5 dB**     | Heavy dynamic cuts at 200Hz need compensation           |
| **Synth/Keyboard**    | **+2 to +4 dB**     | HP filter + dynamic cuts reduce overall level           |
| **Percussion/Others** | **+1 to +3 dB**     | Light processing, minimal compensation                  |
## **The "Auto-Gain" Trick in TDR Nova**

TDR Nova has a **hidden auto-gain feature**:

1. Right-click on the **Output** knob
2. Select **"Auto"** or **"Gain Match"** (depending on your version)
3. Nova will automatically calculate output gain based on your EQ curve
    

**When to use it**: Quick starting point, but always verify by ear. **When NOT to use it**: If you're intentionally using Nova for creative gain reduction (like a limiter).

## **Output Gain vs. Wideband Compressor**

TDR Nova has **two** output-related controls at the bottom:

| Control                           | Function                                    | Typical Setting              |
| --------------------------------- | ------------------------------------------- | ---------------------------- |
| **Output**                        | Overall make-up gain after EQ               | +2 to +4 dB (varies by stem) |
| **Wideband Compressor Threshold** | Triggers compression across entire spectrum | -18 to -24 dB                |

:::important
**Important**: If you're using the **Wideband Compressor** (the "WBC" section), it will reduce overall level. You'll need **more output gain** to compensate:
:::

| Scenario                 | Output Gain Adjustment |
| ------------------------ | ---------------------- |
| EQ only (no WBC)         | +2 to +4 dB            |
| EQ + WBC at 1.5:1        | +3 to +6 dB            |
| EQ + WBC at 3:1          | +5 to +8 dB            |
| Heavy dynamic cuts + WBC | +6 to +10 dB           |

## **Gain Staging: The Full Chain**

Here's how output gain fits into your complete signal chain:


```txt
[Suno Stem] → [Audacity Compressor] → [TDR Nova] → [Panagement 2] → [Master Bus]

Level: -12 dBFS → -12 dBFS (make-up) → -12 dBFS (output matched) → -12 dBFS → -6 dBFS

```

**Target Levels**:

- **After each plugin**: Peak around **-12 to -6 dBFS**
- **Before Panagement 2**: Leave **3-6 dB headroom** for reverb tails
- **Master Bus input**: Peak around **-6 dBFS** (leave room for mastering)

## **Practical Example: Lead Vocal Chain**

Let's walk through setting output gain for a lead vocal:

### **Step 1**: Apply Audacity Compressor

- Threshold: -22 dB, Ratio 3.5:1, Make-up Gain: +5 dB
- **Result**: Vocal now peaks at -10 dBFS (was -15 dBFS)
    

### **Step 2**: Apply TDR Nova

- HP 80Hz: Removes some low-end energy
- Dynamic cut 200Hz: Reduces level during loud passages
- Dynamic cut 800Hz: Reduces "honk" during loud passages
- Dynamic boost 3.5kHz: Adds presence
- Dynamic shelf 10kHz: Adds air
    

**Net effect**: The cuts often outweigh the boosts, so overall level drops by 2-4 dB.

### **Step 3**: Set TDR Nova Output

- Start with **+3 dB**
- Play the loudest section of the song
- Adjust until peaks match the level **before** TDR Nova was added
- Final setting might be **+2 to +5 dB** depending on how aggressive your cuts are
    

### **Step 4**: Verify with Panagement 2

- Add Panagement 2 with reverb (20% wet)
- Reverb adds energy, so you might need to **reduce** TDR Nova output by 1-2 dB to prevent clipping


## **Common Mistakes to Avoid**

| Mistake                          | What Happens                                  | Fix                                      |
| -------------------------------- | --------------------------------------------- | ---------------------------------------- |
| **Output too high**              | Clipping, distortion, harsh sound             | Reduce output, check Audacity meter      |
| **Output too low**               | Signal too quiet, noise floor becomes audible | Increase output, check gain staging      |
| **Not gain-matching**            | Can't objectively judge if EQ helps           | Always A/B at equal loudness             |
| **Forgetting reverb headroom**   | Panagement 2 reverb causes clipping           | Leave -3 to -6 dB before spatial effects |
| **Different output per section** | Verse sounds different from chorus            | Set output based on loudest section      |


## **Quick Reference: Output Gain Calculator**

Use this formula as a starting point:


```txt
Output Gain = (Sum of all EQ cuts in dB) × 0.5 + (WBC gain reduction) × 0.7
```

| Example                                  | Calculation           | Output Gain |
| ---------------------------------------- | --------------------- | ----------- |
| 200Hz cut -3dB, 800Hz cut -2dB, no WBC   | (5 × 0.5) + 0         | **+2.5 dB** |
| 250Hz cut -4dB, WBC reducing 2dB         | (4 × 0.5) + (2 × 0.7) | **+3.4 dB** |
| Heavy cuts: -8dB total, WBC reducing 4dB | (8 × 0.5) + (4 × 0.7) | **+6.8 dB** |

## **Master Bus Output Gain**

On your **master track**, TDR Nova output should be set differently:


| Goal                              | Output Setting                             |
| --------------------------------- | ------------------------------------------ |
| **Mixing** (before mastering)     | Match input level, peak at -6 dBFS         |
| **Self-mastering**                | +1 to +2 dB, then add a limiter after Nova |
| **Sending to mastering engineer** | -1 to -3 dB, conservative headroom         |

:::note
**Master Bus Rule**: Never let your master peak above **-1 dBFS** (true peak). Many streaming platforms reject files that clip.
:::

## **Audacity Meter Setup**
To accurately set output gain, configure your meters:

1. **View > Toolbars > Show Recording Meter** (and Playback Meter)
2. Right-click meter → **"Gradient"** or **"RMS + Peak"*
3. Watch the **peak level** (the thin line, not the average)

**Green zone**: -18 to -12 dBFS (safe) **Yellow zone**: -12 to -6 dBFS (caution) **Red zone**: Above -6 dBFS (danger of clipping)


## **Summary Table: Complete Settings**

| Stem           | TDR Nova Output | Wideband Comp | Final Peak Target |
| -------------- | --------------- | ------------- | ----------------- |
| Lead Vocal     | +3 dB           | Off or 1.5:1  | -12 dBFS          |
| Backing Vocal  | +2 dB           | Off           | -14 dBFS          |
| Bass           | +1 dB           | Off           | -12 dBFS          |
| Drums          | +3 dB           | Off           | -10 dBFS          |
| Guitar         | +3 dB           | Off           | -12 dBFS          |
| Synth          | +3 dB           | Off           | -14 dBFS          |
| Percussion     | +2 dB           | Off           | -14 dBFS          |
| **Master Bus** | **0 to +1 dB**  | **1.5:1**     | **-6 dBFS**       |
