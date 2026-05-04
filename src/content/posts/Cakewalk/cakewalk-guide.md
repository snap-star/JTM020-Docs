---
title: Cakewalk Guide
updated: 2026-05-04
published: 2026-05-04
description: A Complete Guide how to mix audio in cakewalk
image: ""
tags:
  - Cakewalk
  - Guide
category: Cakewalk
draft: false
---
# **Cakewalk Project Setup for Suno Stems**

## **Step 1: Import & Organize**

1. Drag your Suno stems into Cakewalk
2. **Color-code tracks**: Vocals (red), Guitars (green), Bass (blue), Drums (orange), Synths (purple)
3. Set **Track Faders** to unity (0 dB) and use **Clip Gain** (right-click clip → Clip Properties → Volume) to rough-balance before plugins
    
## **Step 2: Understand Signal Flow**

Cakewalk gives you **three** places to process audio [Cakewalk Discus](https://discuss.cakewalk.com/topic/76576-prochannel/):

```txt
[Clip] → [Clip FX] → [ProChannel] → [FX Bin] → [Fader] → [Bus]
```

:::tip[Recommended:]
**Workflow for your mix**:
- **ProChannel**: Use for Cakewalk's console emulation + channel strip (EQ/compression)
- **FX Bin**: Use for TDR plugins + spatial effects (Panagement 2)
- **Why**: ProChannel emulates an analog console channel; FX Bin is your "outboard gear" rack
:::

# **The TDR Trio + Cakewalk Stock Plugin Chains**

## **1. DRUMS**

:::note[Goal]
Punchy, controlled, with room ambience
:::

| Stage          | Plugin                                  | Settings                                                            | Purpose                                 |
| -------------- | --------------------------------------- | ------------------------------------------------------------------- | --------------------------------------- |
| **ProChannel** | **Console Emulator** (SSL or Neve mode) | Drive: subtle                                                       | Adds analog glue to digital Suno drums  |
| **ProChannel** | **PC4K Compressor** (SSL-style)         | Ratio 2:1, Threshold -10 dB, Release Auto                           | Fast, punchy drum bus compression       |
| **FX Bin**     | **TDR Kotelnikov**                      | Ratio 2:1, Peak 30ms, RMS 100ms, SC HP 80Hz                         | Transparent leveling                    |
| **FX Bin**     | **TDR Nova**                            | Dynamic cut -3dB @ 400Hz, Dynamic boost +2dB @ 3kHz                 | Tame boxiness, add crack                |
| **FX Bin**     | **TDR SlickEQ**                         | British mode, Low +2dB @ 100Hz, High +2dB @ 8kHz, Saturation: Silky | Drum tone shaping                       |
| **Send Bus**   | **BREVERB 2** (Cakewalk stock)          | Room or Hall, 15-20% wet                                            | Algorithmic reverb—excellent quality    |

:::tip[Cakewalk Tip:]
Use the **Style Dial "Shaper"** on drum overheads for quick transient shaping if the snare needs more snap [admiralbumblebee.com](https://www.admiralbumblebee.com/music/2018/12/22/Cakewalk-Part-1-Almost-Everything.html).
:::

## **2. BASS** 

:::note[Goal:]
Tight, solid low-end that sits in the pocket
:::

| Stage          | Plugin                           | Settings                                   | Purpose                               |
| -------------- | -------------------------------- | ------------------------------------------ | ------------------------------------- |
| **ProChannel** | **PC76 Compressor** (1176-style) | Ratio 4:1, Attack Fast, Release Fast       | Aggressive bass control               |
| **ProChannel** | **ProChannel EQ**                | Low +2dB @ 80Hz, Mid -2dB @ 250Hz          | Basic tone shaping                    |
| **FX Bin**     | **TDR Kotelnikov**               | Ratio 3:1, Peak 15ms, RMS 150ms            | Transparent leveling without pumping  |
| **FX Bin**     | **TDR Nova**                     | HP @ 35Hz, Dynamic cut -4dB @ 200Hz        | Remove mud dynamically                |
| **FX Bin**     | **TDR SlickEQ**                  | American mode, Deep saturation @ low drive | Add harmonic grit for small speakers  |

:::tip[Cakewalk Tip:]
Insert **Softube Saturation Knob** in ProChannel after compression for easy one-knob tube warmth.
:::

## **3. GUITARS** 

:::note[Goal:]
Wide, atmospheric, shimmering indie tone
:::

| Stage          | Plugin                                 | Settings                                                           | Purpose                       |
| -------------- | -------------------------------------- | ------------------------------------------------------------------ | ----------------------------- |
| **ProChannel** | **Console Emulator** (Trident A-Range) | Subtle drive                                                       | Colorful British preamp vibe  |
| **ProChannel** | **ProChannel EQ**                      | High-pass @ 100Hz, High shelf +2dB @ 6kHz                          | Basic cleanup                 |
| **FX Bin**     | **TDR Nova**                           | Dynamic cut -3dB @ 3kHz (tames Suno harshness)                     | Harshness control             |
| **FX Bin**     | **TDR SlickEQ**                        | British mode, Low +2dB @ 120Hz, High +3dB @ 6kHz, Silky saturation | Indie rock shimmer            |
| **FX Bin**     | **Panagement 2**                       | Width 150-200%, Cave/Heaven reverb, 25% wet                        | Spatial width                 |
:::tip[Cakewalk Tip:]
Use **FX Chain** to create a macro: one knob controls both SlickEQ high shelf and Panagement width for automated "chorus expansion" [tapeop.com](https://tapeop.com/reviews/gear/92/sonar-x2-producer).
:::

## **4. SYNTH/KEYBOARD** 

:::note[Goal:]
Atmospheric pads and focused arpeggios
:::

| Stage          | Plugin              | Settings                                                         | Purpose                      |
| -------------- | ------------------- | ---------------------------------------------------------------- | ---------------------------- |
| **ProChannel** | **Tube Saturation** | Low drive                                                        | Warm up digital Suno synths  |
| **FX Bin**     | **TDR Nova**        | HP @ 120Hz, Dynamic cut -3dB @ 300Hz, Dynamic shelf +2dB @ 12kHz | Clean and airy               |
| **FX Bin**     | **TDR SlickEQ**     | German mode, High shelf +3dB @ 12kHz, Mellow saturation          | Expensive analog synth vibe  |
| **FX Bin**     | **Panagement 2**    | Back of field, Width 180%, Dark/Heaven reverb, 35% wet           | Floating pad texture         |
:::tip[Cakewalk Tip:]
For arpeggiators, use **Sonitus Gate** in the FX Bin before compression to tighten up the tail and create a "staccato" indie feel.
:::

## **5. VOCAL (Lead)** 

:::note[Goal:]
Intimate, upfront, every word clear
:::

| Stage          | Plugin                        | Settings                                                                                                    | Purpose                           |
| -------------- | ----------------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------- |
| **ProChannel** | **PC2A T-Type** (LA-2A-style) | Gain reduction 2-4 dB                                                                                       | Smooth, warm optical compression  |
| **ProChannel** | **Style Dial "Smoother"**     | 20-40%                                                                                                      | Quick de-essing                   |
| **FX Bin**     | **TDR Kotelnikov**            | Ratio 2:1, gentle leveling                                                                                  | Transparent control               |
| **FX Bin**     | **TDR Nova**                  | Dynamic cut -4dB @ 200Hz, Dynamic cut -2dB @ 800Hz, Dynamic boost +3dB @ 3.5kHz, Dynamic shelf +4dB @ 10kHz | Full vocal dynamic EQ             |
| **FX Bin**     | **TDR SlickEQ**               | American mode, Tilt slightly up                                                                             | Air and presence                  |
| **Send Bus**   | **BREVERB 2**                 | Small room or plate, 20% wet, pre-delay 25ms                                                                | Vocal space                       |

:::tip[Cakewalk Tip:]
Use **VocalSync** (if you have multiple vocal takes) to tighten backing vocals to the lead automatically [admiralbumblebee.com](https://www.admiralbumblebee.com/music/2018/12/22/Cakewalk-Part-1-Almost-Everything.html).
:::

## **6. BACKING VOCALS** 

| Stage          | Plugin           | Settings                           | Purpose                    |
| -------------- | ---------------- | ---------------------------------- | -------------------------- |
| **ProChannel** | **PC2A T-Type**  | Light compression                  | Blend under lead           |
| **FX Bin**     | **TDR Nova**     | Dynamic cut -2dB @ 2.5kHz          | Prevent masking lead vocal |
| **FX Bin**     | **TDR SlickEQ**  | High shelf +3dB @ 10kHz            | Air                        |
| **FX Bin**     | **Panagement 2** | Width 180%, back of field, 30% wet | Wide and behind lead       |

## **7. PERCUSSION/OTHERS** 

| Stage          | Plugin                             | Settings                                        | Purpose                |
| -------------- | ---------------------------------- | ----------------------------------------------- | ---------------------- |
| **ProChannel** | **ProChannel EQ**                  | High-pass @ 150Hz                               | Remove low-end clutter |
| **FX Bin**     | **TDR Nova**                       | Dynamic cut -3dB @ 5kHz (tame harsh percussion) | Tame Suno harshness    |
| **FX Bin**     | **TDR SlickEQ**                    | British mode, subtle high shelf                 | Sheen                  |
| **Send Bus**   | **REmatrix Solo** (Cakewalk stock) | Short room IR, 15% wet                          | Natural space          |

# **Bus Routing in Cakewalk**
Create **three aux buses** for a professional workflow:

## **Bus 1: Drum Bus**
- Route all drum/percussion tracks here
- Insert: **PC4K Compressor** (ProChannel) → **TDR Kotelnikov** (gentle 1.5:1 glue)
- Send to: Reverb Bus
    
## **Bus 2: Guitar/Synth Space**
- Route guitars and synths
- Insert: **TDR SlickEQ** (German mode, subtle) → **Panagement 2** (if not on individual tracks)
- Send to: Reverb Bus
    
## **Bus 3: Reverb Bus (100% Wet)**
- Insert: **BREVERB 2** (Hall or Plate, 100% wet)
- Return to: Master Bus 
- **Why**: Shared reverb creates a cohesive "room" for your band

| Order | Plugin                                     | Settings                                                                                    | Purpose                      |
| ----- | ------------------------------------------ | ------------------------------------------------------------------------------------------- | ---------------------------- |
| 1     | **ProChannel Console Emulator**            | SSL or Neve, subtle                                                                         | Analog mix bus glue          |
| 2     | **TDR Kotelnikov**                         | Ratio 1.5:1, Threshold -20dB, Peak 60ms, RMS 200ms, SC HP 80Hz                              | Transparent mix compression  |
| 3     | **TDR Nova**                               | Dynamic cut -1dB @ 400Hz (muddy build-up during chorus), Gentle shelf +1dB @ 12kHz          | Dynamic master EQ            |
| 4     | **TDR SlickEQ**                            | German mode, Low +0.5dB @ 60Hz, High shelf +1dB @ 12kHz, Mellow saturation @ very low drive | Mastering tone               |
| 5     | **Concrete Limiter** (Cakewalk ProChannel) | Threshold -1 dB, gentle                                                                     | Catch peaks                  |
| 6     | **Boost 11** (Cakewalk stock, optional)    | Threshold for -14 to -12 LUFS                                                               | Final loudness               |

:::tip[Cakewalk Tip:]
**Cakewalk Tip**: Enable **Plugin Oversampling** (2x or 4x) on your limiter to prevent inter-sample peaks.

```
Right-click the plugin → Oversampling → Enable for Render.
```

:::

# **Cakewalk-Specific Power Moves**

## **1. ProChannel Console Emulation on Every Track**
Add the **Console Emulator** as the first module in every ProChannel. Choose:
- **SSL**: Clean, punchy, great for drums/bass
- **Neve**: Warm, thick, great for vocals/guitars
- **Trident A-Range**: Colorful, aggressive, great for indie rock grit
    
This alone will make your Suno stems sound less "digital" and more like a real band recorded through a desk

## **2. Use "Mix Recall" for A/B Comparisons**
Before finalizing, save a **Mix Scene** (Mix Recall → Save Scene). Then create variations:
- Scene A: Your current mix
- Scene B: Bypass all TDR plugins (hear the raw Suno stems)
- Scene C: Bypass all ProChannel processing
Toggle between them to ensure you're actually improving things.

## **3. FX Chain for Quick Automation**
Create an **FX Chain** on your guitar bus with two mapped controls:

- **Knob 1**: SlickEQ High Shelf (chorus brightness)
- **Knob 2**: Panagement 2 Width (chorus expansion)

Automate this single knob to "explode" the chorus and "tighten" the verse

## **4. Sidechain Compression (Cakewalk Method)**

To make the bass duck when the kick hits:
1. On the **Bass track**, insert **PC4K** or **Sonitus Compressor**
2. Click the **Sidechain** button in the plugin toolbar
3. Select **Kick Drum** as the sidechain source
4. Set fast attack, medium release, ratio 4:1
    
This creates the "pumping" glue heard in professional alt-rock mixes

## **5. Tape Emulator on the Master**
Insert **Tape Emulator** (ProChannel, before the limiter) with:
- **Drive**: Low
- **Bias**: Normal
- **IPS**: 15 or 30
    
This adds subtle harmonic "glue" that makes the mix feel like a finished record [Cakewalk.com](https://legacy.cakewalk.com/Documentation?product=Cakewalk&language=3&help=ProChannel.01.html).

## **Quick Reference: TDR vs Cakewalk Stock — When to Use Which**

| Task                         | Best Tool                          | Why                                 |
| ---------------------------- | ---------------------------------- | ----------------------------------- |
| Transparent leveling         | **TDR Kotelnikov**                 | More precise than PC4K/PC76         |
| Analog character compression | **PC2A / PC76**                    | Modeled after classic hardware      |
| Taming harsh resonances      | **TDR Nova**                       | Dynamic EQ beats static every time  |
| Broad tone shaping           | **TDR SlickEQ**                    | Saturation + musical curves         |
| Quick de-essing              | **Style Dial "Smoother"**          | One-knob solution                   |
| Mix bus glue                 | **Console Emulator + Kotelnikov**  | Analog + digital precision          |
| Reverb                       | **BREVERB 2**                      | Professional algorithmic quality    |
| Saturation                   | **Tube Saturation / Softube Knob** | Easy ProChannel integration         |
| Limiting                     | **Concrete Limiter**               | Clean, built for Sonar              |

:::note[Final Export Settings]
# **Final Export Settings**

1. **File > Export > Audio**
2. Format: **WAV** (32-bit float) for archive, **MP3** (320 kbps) for sharing
3. Enable **"Enable for Render"** oversampling on all TDR plugins (2x or 4x)
4. Export through the master bus chain above
5. Target: **-14 LUFS integrated** (streaming standard), peak no higher than **-1 dB true peak**

:::
