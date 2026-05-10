---
title: Mastering with Trio TDR
updated: 2026-05-10
published: 2026-05-10
description: Mastering in Cakewalk Using TDR Plugins
image: ""
tags:
  - Cakewalk
  - Mixing
category: Cakewalk
draft: false
---
Here is your **complete advanced mixing blueprint** for Suno stems in **Cakewalk**, using the **TDR Trio** as the surgical core, augmented by Cakewalk’s **ProChannel** and routing architecture.

---

## **Part 1: Cakewalk Signal Flow Architecture**

Before touching a parameter, understand exactly where each plugin lives. Cakewalk gives you a hybrid analog/digital signal path :
```txt
[Clip] → [Clip FX] → [ProChannel] → [FX Bin] → [Send Buses] → [Master]
```

### **The Advanced Placement Rule**

|Stage|What Lives Here|Why|
|---|---|---|
|**ProChannel** (first)|**Console Emulator** + **PC4K/PC76/PC2A** + **ProChannel EQ**|Emulates the recording desk. Adds analog non-linearity _before_ your precision digital tools.|
|**FX Bin** (second)|**TDR Kotelnikov** → **TDR Nova** → **TDR SlickEQ** → **Panagement 2**|Your “outboard rack.” Kotelnikov levels, Nova fixes, SlickEQ colors, Panagement spaces.|
|**Send Buses** (parallel)|**BREVERB 2**, **Parallel Compression Bus**, **M/S Processing Bus**|Shared resources that keep the mix cohesive without destroying CPU.|

**Critical**: Never put spatial effects (reverb, Panagement) before the TDR trio. You want to control tone and dynamics _before_ you place the sound in the room.

---

## **Part 2: The TDR Trio — Advanced Concepts**

Before the stem-by-stem breakdown, master these four techniques:

### **1. Kotelnikov Dual Release (The Secret to Punch)**

Kotelnikov has **two release times** : - **Peak Release**: How fast it lets go of _transients_ (snare crack, pick attack, consonants). - **RMS Release**: How fast it lets go of _sustained energy_ (drum body, vocal note, synth pad).

**The Formula**: Set Peak Release **3–5x faster** than RMS Release. This keeps the “snap” while smoothing the “body.”

### **2. Nova as a Multiband Compressor / De-Esser**

Nova is not just an EQ. When you enable **Dynamic** on a band, it becomes a frequency-specific compressor. Use **narrow Q (2.0–3.0)** for surgical resonance removal, **wide Q (0.5–1.0)** for broad tonal shaping.

### **3. SlickEQ M/S Mode (Mid/Side)**

Enable the **M/S** button in SlickEQ. This splits processing into: - **Mid**: Center channel (mono information — kick, bass, lead vocal). - **Side**: Left-minus-right (stereo width — guitars, synth pads, room ambience).

**Advanced move**: Cut low frequencies in the **Side** channel to tighten the mix, and boost high frequencies in the **Side** channel to widen the “air.”

### **4. Delta Preview (Kotelnikov)**

Click the **Delta** button on Kotelnikov. You will hear _only_ what the compressor is removing. This prevents the “louder is better” trap and reveals exactly how much you’re crushing the transients .

---

## **Part 3: Stem-by-Stem Advanced Chains**

### **A. DRUMS (The Drum Bus)** 🥁

Suno drum stems are often dynamically flat and cymbal-heavy. This chain restores punch and removes AI harshness.

#### **ProChannel Chain**

|Module|Setting|Purpose|
|---|---|---|
|**Console Emulator**|**SSL** mode, Drive at 9 o’clock|Adds aggressive transient bite. SSL is punchy and modern .|
|**PC4K Compressor**|Ratio 2:1, Threshold -12 dB, Release Auto|Fast SSL-style bus glue. Tames the overhead spill before it hits the TDR chain.|
|**ProChannel EQ**|High-pass at 30 Hz, +1 dB at 10 kHz shelf|Remove sub-rumble; add pre-TDR air.|

#### **FX Bin: TDR Trio**

| Plugin         | Parameter          | Value                                               | Advanced Notes                                                                                  |
| -------------- | ------------------ | --------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **Kotelnikov** | Threshold          | -18 dB                                              | Aim for **3–5 dB of gain reduction** on the loudest snare hits.                                 |
|                | Ratio              | 2.2:1                                               | Just enough to tuck the drum bus together.                                                      |
|                | Peak Release       | 25 ms                                               | Lets the snare _crack_ through before clamping.                                                 |
|                | RMS Release        | 120 ms                                              | Smooths the tom rings and cymbal wash.                                                          |
|                | Sidechain HP       | 100 Hz                                              | Prevents the kick drum from ducking the entire drum bus .                                       |
|                | Stereo Link        | 85%                                                 | Allows slight independent L/R movement for width.                                               |
| **Nova**       | Band 1: Bell       | 400 Hz, Q 1.8, **Dynamic ON**, -4 dB, Thr -20 dB    | **Dynamic boxiness removal.** Only cuts when the snare/tom rings get muddy.                     |
|                | Band 2: Bell       | 3.2 kHz, Q 1.2, **Dynamic ON**, +2.5 dB, Thr -24 dB | **Crack injection.** Boosts stick attack only when the drum hits — prevents constant harshness. |
|                | Band 3: Bell       | 8 kHz, Q 2.5, **Dynamic ON**, -5 dB, Thr -22 dB     | **Cymbal harshness surgery.** Targets the “white noise” AI artifact in Suno cymbals.            |
|                | Band 4: High Shelf | 12 kHz, **Dynamic ON**, +1.5 dB, Thr -26 dB         | **Air control.** Only adds shimmer during loud passages.                                        |
| **SlickEQ**    | Mode               | **British**                                         | Aggressive, punchy midrange — perfect for alt-rock drums .                                      |
|                | Low Shelf          | +2 dB at 100 Hz                                     | Weight.                                                                                         |
|                | High Shelf         | +2 dB at 8 kHz                                      | Sheen.                                                                                          |
|                | Saturation         | **Silky**, Drive at 10 o’clock                      | Adds harmonic content without obvious distortion.                                               |
|                | **M/S Mode**       | **Side** channel only: Cut -2 dB at 250 Hz          | Removes side-channel mud; keeps the kick and snare center tight.                                |

#### **Cakewalk Send**

•         Send 15% to a **BREVERB 2 Bus** (Room, short tail) for drum room ambience.

---

### **B. BASS** 🎸

Suno bass is often boomy and lacks note definition. This chain tightens it without killing the low-end weight.

#### **ProChannel Chain**

|Module|Setting|Purpose|
|---|---|---|
|**Console Emulator**|**Neve** mode, Drive at 10 o’clock|Thick, warm low-end harmonics.|
|**PC76 Compressor**|Ratio 4:1, Attack Fast, Release Fast|1176-style “all buttons in” aggression. Grabs the bass and squeezes it .|
|**ProChannel EQ**|+2 dB at 80 Hz, -2 dB at 600 Hz|Pre-TDR shaping.|

#### **FX Bin: TDR Trio**

|Plugin|Parameter|Value|Advanced Notes|
|---|---|---|---|
|**Kotelnikov**|Threshold|-20 dB|Aim for **4–6 dB GR**. Bass needs to be solid.|
||Ratio|3.5:1|Aggressive. This is a foundation instrument.|
||Attack|12 ms|Lets the initial pluck/pick attack through for definition.|
||Peak Release|15 ms|Fast — prevents the note from losing attack.|
||RMS Release|180 ms|Medium — holds the sustain evenly.|
||Sidechain HP|**OFF** (0 Hz)|Let the sub-bass trigger the compressor. This creates “low-end pumping” which actually helps the bass lock with the kick.|
||Stereo Link|100%|Bass must be perfectly mono-compatible.|
|**Nova**|HP Filter|35 Hz, 24 dB/oct|Removes inaudible sub-rumble that eats headroom.|
||Band 1: Bell|200 Hz, Q 1.5, **Dynamic ON**, -5 dB, Thr -18 dB|**The Mud Killer.** Suno bass builds up here. Dynamic cut only when the note gets boomy.|
||Band 2: Bell|900 Hz, Q 1.8, **Dynamic ON**, +2 dB, Thr -22 dB|**String noise / Pick attack.** Only boosts when the note is dull, preventing constant “clickiness.”|
||Band 3: Low Pass|8 kHz, 12 dB/oct|Bass has no business above here.|
|**SlickEQ**|Mode|**American**|Punchy, clear low-end.|
||Low Shelf|+2 dB at 80 Hz|Reinforces weight after compression.|
||Bell|+2.5 dB at 1 kHz|Definition on small speakers (laptop, phone).|
||Saturation|**Deep**, Drive at 9 o’clock|**Odd harmonics.** This makes the bass audible on earbuds by creating phantom upper harmonics .|
||**M/S Mode**|**Side** channel: MUTE below 120 Hz|Ensures zero low-end information leaks to the sides. Bass stays center-locked.|

#### **Advanced Cakewalk Routing: Parallel Bass**

1.       Duplicate the Bass track.

2.       On the duplicate, bypass Kotelnikov and Nova. Keep only **SlickEQ** with **Deep** saturation cranked higher.

3.       Crush the duplicate with **PC76** (Ratio 8:1).

4.       Blend the duplicate back in at **-12 to -15 dB** under the main bass.

5.       Result: Tight, clean low-end + aggressive gritty texture.

---

### **C. GUITARS (Rhythm & Lead)** 🎸

Suno guitars are often too polite. This chain makes them aggressive, wide, and alive.

#### **ProChannel Chain**

|Module|Setting|Purpose|
|---|---|---|
|**Console Emulator**|**Trident A-Range**|Colorful, aggressive British preamp. Adds indie rock attitude .|
|**ProChannel EQ**|High-pass at 100 Hz, +1 dB at 6 kHz|Pre-tone shaping.|

#### **FX Bin: TDR Trio**

|Plugin|Parameter|Value|Advanced Notes|
|---|---|---|---|
|**Kotelnikov**|Threshold|-16 dB|Light leveling. Guitars need to breathe.|
||Ratio|1.8:1|Very gentle.|
||Attack|12 ms|Preserves the pick attack.|
||Peak Release|50 ms|Lets strums breathe.|
||RMS Release|150 ms|Smooths chord sustains.|
||Stereo Link|60%|Allows independent L/R movement. This is critical for indie rock width — if one side compresses more than the other, it creates subtle width modulation.|
|**Nova**|Band 1: Bell|200 Hz, Q 1.5, **Dynamic ON**, -3 dB, Thr -20 dB|Removes mud when strumming hard.|
||Band 2: Bell|3 kHz, Q 2.0, **Dynamic ON**, -4 dB, Thr -22 dB|**The Suno Harshness Notch.** AI guitars often whistle here.|
||Band 3: Bell|5 kHz, Q 2.5, **Dynamic ON**, -2 dB, Thr -24 dB|Tames digital fizz on distorted guitars.|
||Band 4: High Shelf|10 kHz, **Dynamic ON**, +3 dB, Thr -26 dB|**Dynamic air.** Only adds shimmer during loud passages.|
|**SlickEQ**|Mode|**British**|Aggressive midrange — the “indie rock” sound.|
||Low Shelf|+2 dB at 120 Hz|Body.|
||Bell|+2 dB at 2.5 kHz|Bite.|
||High Shelf|+3 dB at 8 kHz|Shimmer.|
||Saturation|**Silky**, Drive at 11 o’clock|Adds air and openness without grit.|
||**M/S Mode**|**Side** channel: +3 dB at 12 kHz shelf, **Mid** channel: -1 dB at 400 Hz|Widens the “air” while keeping the center guitar focused.|

#### **Cakewalk Send**

•         Send 20% to a **Hall Reverb Bus** (BREVERB 2, large hall, 2.5s tail).

•         Pan the reverb return slightly opposite to the dry guitar for width.

---

### **D. SYNTH / KEYBOARD** 🎹

Suno synths are often generic and dynamically static. This chain makes them evolve and breathe.

#### **ProChannel Chain**

|Module|Setting|Purpose|
|---|---|---|
|**Console Emulator**|**Neve**|Warmth for digital synths.|
|**PC2A T-Type**|Light gain reduction (2 dB)|Smooths the flat AI dynamics.|
|**ProChannel EQ**|High-pass at 120 Hz|Remove mud.|

#### **FX Bin: TDR Trio**

|Plugin|Parameter|Value|Advanced Notes|
|---|---|---|---|
|**Kotelnikov**|Threshold|-20 dB|Gentle.|
||Ratio|1.5:1|Very light — pads need to swell.|
||Attack|20 ms|Slow — lets the synth attack breathe.|
||Peak Release|80 ms|Medium.|
||RMS Release|250 ms|Long — holds the pad sustain smoothly.|
||Stereo Link|100%|Keep pads stable in the stereo field.|
|**Nova**|HP Filter|120 Hz|Clean up.|
||Band 1: Bell|300 Hz, Q 1.8, **Dynamic ON**, -4 dB, Thr -20 dB|Pad mud removal.|
||Band 2: Bell|2 kHz, Q 1.2, **Dynamic ON**, +2 dB, Thr -24 dB|Presence when the pad gets lost.|
||Band 3: High Shelf|12 kHz, **Dynamic ON**, +4 dB, Thr -28 dB|**Sparkle that breathes.**|
||**Sidechain**|Route **Lead Vocal** to Nova’s sidechain input|**Advanced:** Set Band 2 (2 kHz) to duck when the vocal is present. This creates automatic spectral space for the vocal without static EQ cuts.|
|**SlickEQ**|Mode|**German**|Smooth, expensive analog sound.|
||High Shelf|+3 dB at 16 kHz|Air beyond human hearing — adds perceived “dimension.”|
||Saturation|**Mellow**, Drive at 10 o’clock|Gentle warming.|
||**M/S Mode**|**Side** channel: +4 dB at 8 kHz|Makes the pad wrap around the listener.|

---

### **E. LEAD VOCAL** 🎤

The most critical chain. Suno vocals are flat, often harsh, and lack intimacy.

#### **ProChannel Chain**

|Module|Setting|Purpose|
|---|---|---|
|**Console Emulator**|**Neve**|Warmth and thickness.|
|**PC2A T-Type**|Gain reduction 3–4 dB|Optical smoothing. Catches the big peaks before they hit Kotelnikov .|
|**Style Dial “Smoother”**|30%|Cakewalk’s quick de-esser. Pre-tames sibilance.|
|**ProChannel EQ**|High-pass at 80 Hz, +1 dB at 8 kHz|Pre-tone.|

#### **FX Bin: TDR Trio**

|Plugin|Parameter|Value|Advanced Notes|
|---|---|---|---|
|**Kotelnikov**|Threshold|-22 dB|Aim for **3–5 dB GR**.|
||Ratio|2.5:1|Transparent leveling.|
||Attack|6 ms|Fast enough to catch peaks, slow enough for consonants.|
||Peak Release|40 ms|Natural vocal decay.|
||RMS Release|90 ms|Smooths phrases.|
||Sidechain HP|120 Hz|Prevents plosives (p/b sounds) from triggering compression.|
||Stereo Link|100%|Vocals are mono.|
|**Nova**|HP Filter|80 Hz|Remove rumble.|
||Band 1: Bell|200 Hz, Q 1.5, **Dynamic ON**, -4 dB, Thr -22 dB|**Proximity effect control.** Only cuts when the singer gets boomy.|
||Band 2: Bell|800 Hz, Q 1.8, **Dynamic ON**, -2.5 dB, Thr -20 dB|**Honk removal.** Suno AI often has a nasal resonance here.|
||Band 3: Bell|3.5 kHz, Q 1.0, **Dynamic ON**, +3 dB, Thr -26 dB|**Presence boost.** Only adds intelligibility when the vocal is quiet.|
||Band 4: Bell|8 kHz, Q 2.0, **Dynamic ON**, -3 dB, Thr -24 dB|**De-essing / Sibilance.** Targets “sss” and “shh” sounds.|
||Band 5: High Shelf|12 kHz, **Dynamic ON**, +4 dB, Thr -28 dB|**Breath/air.** Only opens up when the vocal is present.|
|**SlickEQ**|Mode|**American**|Clear, open, modern.|
||Tilt|Slightly up (+1 dB)|Adds overall air.|
||High Shelf|+2 dB at 10 kHz|Consistent air.|
||Saturation|**Silky**, Drive at 9 o’clock|Adds warmth and “analog tape” vocal quality.|

#### **Cakewalk Send**

•         Send 18% to a **Plate Reverb Bus** (BREVERB 2, Plate, 1.8s tail, 25ms pre-delay).

•         Send 8% to a **Stereo Delay Bus** (Cakewalk Sonitus Delay, 1/8th note, 20% feedback, high-passed at 400 Hz).

---

### **F. BACKING VOCALS** 🎤🎤

Must sit _under_ the lead, wide and diffuse.

#### **FX Bin: TDR Trio**

|Plugin|Parameter|Value|Advanced Notes|
|---|---|---|---|
|**Kotelnikov**|Threshold|-18 dB|More aggressive than lead.|
||Ratio|3:1|Keeps them controlled and “small.”|
||Peak Release|30 ms|Tight.|
||RMS Release|120 ms|Smooth.|
|**Nova**|Band 1: Bell|2.5 kHz, Q 1.5, **Dynamic ON**, -3 dB, Thr -20 dB|**Masking prevention.** Ducks the frequency range where the lead vocal lives.|
||Band 2: High Shelf|10 kHz, **Dynamic ON**, +3 dB, Thr -26 dB|Air.|
|**SlickEQ**|Mode|**German**|Smooth, background texture.|
||High Shelf|+3 dB at 12 kHz|Sheen.|
||**M/S Mode**|**Mid** channel: -2 dB at 1 kHz|Pulls the center back so the lead vocal sits on top.|

---

### **G. PERCUSSION / OTHERS** 🪘

Suno percussion often has sharp, digital transients.

#### **FX Bin: TDR Trio**

|Plugin|Parameter|Value|Advanced Notes|
|---|---|---|---|
|**Kotelnikov**|Threshold|-16 dB|Fast, tight control.|
||Ratio|2.5:1|Moderate.|
||Attack|2 ms|Very fast — catches sharp percussion hits.|
||Peak Release|20 ms|Fast recovery.|
||RMS Release|60 ms|Tight.|
|**Nova**|Band 1: Bell|5 kHz, Q 2.5, **Dynamic ON**, -5 dB, Thr -20 dB|Tames harsh “tick” and “click” sounds.|
||Band 2: High Shelf|12 kHz, **Dynamic ON**, -2 dB, Thr -24 dB|Removes digital fizz.|
|**SlickEQ**|Mode|**British**|Adds character to dull percussion.|
||Saturation|**Deep**, very low drive|Subtle grit.|

---

## **Part 4: Master Bus — The Final Polish**

Insert this chain on your **Master Bus** in Cakewalk:

|Order|Plugin|Settings|Purpose|
|---|---|---|---|
|1|**ProChannel Console Emulator**|**SSL**, Drive at 9 o’clock|Analog mix bus glue .|
|2|**TDR Kotelnikov**|Thr -20 dB, Ratio **1.5:1**, Peak 60 ms, RMS 200 ms, SC HP **80 Hz**, Stereo Link 100%|**The Glue.** 1–2 dB of gain reduction max. Use **Delta** to verify you’re not crushing the mix .|
|3|**TDR Nova**|Band 1: Dynamic cut -1.5 dB @ **400 Hz** (Q 1.2, Thr -18 dB)|Catches muddy build-up during loud choruses.|
|||Band 2: Dynamic shelf +1 dB @ **12 kHz** (Thr -24 dB)|Mastering air.|
|||Wideband Comp: Thr -24 dB, Ratio 1.2:1|Ultra-gentle overall smoothing.|
|4|**TDR SlickEQ**|Mode: **German**, Low +0.5 dB @ 60 Hz, High shelf +1 dB @ **16 kHz**, Saturation: **Mellow** @ minimum drive|Mastering tone. The 16 kHz shelf adds “sheen” without harshness. **Auto Gain: ON** .|
|5|**Cakewalk Concrete Limiter**|Threshold -1.0 dB, gentle|Catches inter-sample peaks. Enable **2x Oversampling** (right-click plugin → Enable for Render) .|

**Target**: Peak at **-1.0 dBFS**, integrated loudness around **-14 LUFS** (streaming standard).

---

## **Part 5: Advanced Cakewalk Techniques**

### **1. Parallel Compression (New York Style)**

1.       Create a **Bus** named “Parallel Crush.”

2.       On your Drum Bus, add a **Send** to “Parallel Crush” (pre-fader, unity gain).

3.       On “Parallel Crush,” insert **Kotelnikov** with aggressive settings: Ratio **6:1**, Thr -30 dB, fast attack, fast release.

4.       Crush the drums to death, then blend the bus back in at **-15 to -20 dB** under the main drum bus.

5.       Result: Massive drum punch while retaining the natural transients on the main bus.

### **2. Sidechain Ducking (Vocal Priority)**

1.       On your **Synth Bus**, insert **TDR Nova**.

2.       In Nova, set **Band 2** (2 kHz) to **Dynamic Cut**.

3.       Click the **Sidechain** button in Nova’s toolbar.

4.       In Cakewalk’s track routing, set the synth track’s sidechain input to receive from the **Lead Vocal** track.

5.       Now, whenever the vocal sings, the synth automatically dips at 2 kHz — creating spectral space without static EQ.

### **3. M/S Mastering with SlickEQ**

1.       On the **Master Bus**, insert **SlickEQ** last in the chain.

2.       Enable **M/S** mode.

3.       **Mid channel**: Slight boost at 100 Hz (center weight), slight cut at 400 Hz (center clarity).

4.       **Side channel**: Boost +2 dB at 12 kHz (wide air), cut -2 dB at 200 Hz (tight sides).

5.       Result: The mix feels wider and more expensive, but the center stays solid.

### **4. Automation of TDR Parameters**

Use Cakewalk’s **Automation Lanes** to change settings between Verse and Chorus: - **Kotelnikov Threshold**: Lower threshold (more compression) in verses for intimacy, raise in choruses for power. - **Nova Band Gains**: Automate the 3.5 kHz presence boost to increase during choruses. - **SlickEQ Saturation Drive**: Increase drive slightly during the chorus for more aggression.

### **5. The “Delta Check” Routine**

Before finalizing any track: 1. Solo the track. 2. On **Kotelnikov**, enable **Delta**. Listen to what you’re removing. 3. On **Nova**, temporarily set the band to **Static** (Dynamic OFF) at the same cut value. Listen to how unnatural it sounds. Re-enable Dynamic to appreciate the difference. 4. On **SlickEQ**, enable **Auto Gain** and toggle bypass. Judge the tone, not the loudness.

---

## **Part 6: Suno-Specific Surgery Guide**

|Suno Artifact|The Fix|Plugin & Setting|
|---|---|---|
|**Cymbal “white noise” hiss**|Dynamic high-frequency taming|Nova: -5 dB @ 8 kHz, Q 2.5, Dynamic ON|
|**Vocal “robot” flatness**|Serial compression + saturation|PC2A → Kotelnikov → SlickEQ (Silky)|
|**Synth “digital whistle”**|Notch + dynamic control|Nova: -4 dB @ 3 kHz, Q 3.0, Dynamic ON|
|**Bass “one-note boom”**|Dynamic mud cut + Deep saturation|Nova: -5 dB @ 200 Hz dynamic; SlickEQ: Deep|
|**Guitar “plastic” tone**|British mode + Trident emulation|ProChannel Trident → SlickEQ British|
|**Overall “AI flatness”**|Console Emulator on every track + M/S air|ProChannel SSL/Neve on all tracks; SlickEQ M/S on master|