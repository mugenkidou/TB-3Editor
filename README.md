# Unofficial TB-3 MIDI Implementation v1.3

October 12th, 2018

------

This contents of this publication has no relations with Roland Corporation. Please do not send any inquiries to Roland Corp. Should you have any questions, please send them to myself, Mugenkidou([mugenkidou.wakakusa@gmail.com](mailto:mugenkidou.wakakusa@gmail.com))
When operating MIDI devices according to this publication's contents, please make sure to make any necessary  backups and proceed at your own risk. We will not take any responsibility for any data loss, hardware failure, or other damage.

------

You can set/get hidden parameters by DT1/RQ1 commands. See also [TB-3 MIDI Implementation](https://www.roland.com/us/products/tb-3/support/).



**Table of contents**

* [System Parameters](#System-Parameters)
    * [MIDI](#MIDI)
* [Synth Parameters](#Synth-Parameters)
    * [LFO](#LFO)
    * [CV Offset](#CV-Offset)
    * [Cross Modulation](#Cross-Modulation)
    * [Ring Modulation](#Ring-Modulation)
    * [VCO](#VCO)
    * [VCF](#VCF)
    * [VCA](#VCA)
* [Effects Parameters](#Effects-Parameters)
    * [Distortion](#Distortion)
    * [EFX1](#EFX1)
    * [EFX2](#EFX2)
* [Parameter Assign](#Parameter-Assign)
* [Pattern Parameters](#Pattern-Parameters)
    * [Pitch](#Pitch)
    * [Slide](#Slide)
    * [Gate](#Gate)
    * [Accent](#Accent)
* [(*1) Parameter IDs](#(*1)-Parameter-IDs)

------



# System Parameters

## MIDI

| Address     |           | Description      | Value           |
| :---------- | --------- | ---------------- | --------------- |
| 01 00 00 00 | 0000 aaaa | MIDI OUT CHANNEL | 0 - 15 (1 - 16) |
| 01 00 00 01 | 0000 aaaa | MIDI IN CHANNEL  | 0 - 15 (1 - 16) |
| 01 00 00 02 | 0000 000a | OMNI MODE        | 0 - 1 (OFF, ON) |



## UNIDENTIFIED

| Address     |           | Description  | Value |
| :---------- | --------- | ------------ | ----- |
| 02 00 00 00 | 0000 0000 | UNIDENTIFIED | 0 - 0 |



## UNIDENTIFIED

| Address     |           | Description  | Value |
| :---------- | --------- | ------------ | ----- |
| 02 00 02 00 | 0000 0000 | UNIDENTIFIED | 0 - 0 |



## UNIDENTIFIED

| Address     |           | Description  | Value |
| :---------- | --------- | ------------ | ----- |
| 02 00 40 00 | 0000 0000 | UNIDENTIFIED | 0 - 0 |



# Synth Parameters

## LFO

| Address     |           | Description     | Value              |
| :---------- | --------- | --------------- | ------------------ |
| 10 00 00 00 | 0aaa aaaa | LFO RATE        | 0 - 127            |
| 10 00 00 01 | 0aaa aaaa | LFO DELAY       | 0 - 127            |
| 10 00 00 02 | 0aaa aaaa | LFO WAVE (SAW)  | 0 - 127            |
| 10 00 00 03 | 0aaa aaaa | LFO WAVE (SQR)  | 0 - 127            |
| 10 00 00 04 | 0aaa aaaa | LFO WAVE (TRI)  | 0 - 127            |
| 10 00 00 05 | 0aaa aaaa | LFO WAVE (SIN)  | 0 - 127            |
| 10 00 00 06 | 0aaa aaaa | CV OFFSET (LFO) | 0 - 127            |
| 10 00 00 07 | 0aaa aaaa | LFO WAVE (S&H)  | 0 - 127            |
| 10 00 00 08 | 0aaa aaaa | LFO DEPTH (VCO) | 0 - 127 (-64 - 63) |
| 10 00 00 09 | 0aaa aaaa | LFO DEPTH (VCF) | 0 - 127 (-64 - 63) |
| 10 00 00 0A | 0aaa aaaa | LFO DEPTH (VCA) | 0 - 127 (-64 - 63) |
| 10 00 00 0B | 0000 000a | BPM SYNC        | 0 - 1 (OFF, ON)    |
| 10 00 00 0C | 0000 000a | LFO RETRIGGER   | 0 - 1              |



## CV Offset

| Address                      |                          | Description            | Value                |
| ---------------------------- | ------------------------ | ---------------------- | -------------------- |
| 10 00 02 00<br />10 00 02 01 | 0000 aaaa<br />0000 bbbb | CV OFFSET (SQR PITCH)  | 0 - 255 (-128 - 127) |
| 10 00 02 02<br />10 00 02 03 | 0000 aaaa<br />0000 bbbb | CV OFFSET (SAW PITCH)  | 0 - 255 (-128 - 127) |
| 10 00 02 04<br />10 00 02 05 | 0000 aaaa<br />0000 bbbb | CV OFFSET (RING PITCH) | 0 - 255 (-128 - 127) |



## Cross Modulation

| Address     |           | Description                              | Value              |
| ----------- | --------- | ---------------------------------------- | ------------------ |
| 10 00 04 00 | 0aaa aaaa | CROSS MODULATION DEPTH (SQR>SAW)         | 0 - 127 (-64 - 63) |
| 10 00 04 01 | 0aaa aaaa | UNIDENTIFIED                             | 0 - 127            |
| 10 00 04 02 | 0aaa aaaa | CROSS MODULATION DEPTH (SAW>SAW)         | 0 - 127 (-64 - 63) |
| 10 00 04 03 | 0aaa aaaa | CROSS MODULATION DEPTH (WHITE NOISE>SAW) | 0 - 127 (-64 - 63) |
| 10 00 04 04 | 0aaa aaaa | CROSS MODULATION DEPTH (PINK NOISE>SAW)  | 0 - 127 (-64 - 63) |
| 10 00 04 05 | 0aaa aaaa | CROSS MODULATION DEPTH (SQR>SQR)         | 0 - 127 (-64 - 63) |
| 10 00 04 06 | 0aaa aaaa | UNIDENTIFIED                             | 0 - 127            |
| 10 00 04 07 | 0aaa aaaa | CROSS MODULATION DEPTH (SAW>SQR)         | 0 - 127 (-64 - 63) |
| 10 00 04 08 | 0aaa aaaa | CROSS MODULATION DEPTH (WHITE NOISE>SQR) | 0 - 127 (-64 - 63) |
| 10 00 04 09 | 0aaa aaaa | CROSS MODULATION DEPTH (PINK NOISE>SQR)  | 0 - 127 (-64 - 63) |



## Ring Modulation

| Address     |           | Description                         | Value   |
| ----------- | --------- | ----------------------------------- | ------- |
| 10 00 06 00 | 0aaa aaaa | RING MODULATION DEPTH (SAW)         | 0 - 127 |
| 10 00 06 01 | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |
| 10 00 06 02 | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |
| 10 00 06 03 | 0aaa aaaa | RING MODULATION DEPTH (RING)        | 0 - 127 |
| 10 00 06 04 | 0aaa aaaa | RING MODULATION DEPTH (WHITE NOISE) | 0 - 127 |
| 10 00 06 05 | 0aaa aaaa | RING MODULATION DEPTH (PINK NOISE)  | 0 - 127 |
| 10 00 06 06 | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |
| 10 00 06 07 | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |
| 10 00 06 08 | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |
| 10 00 06 09 | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |
| 10 00 06 0A | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |
| 10 00 06 0B | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |
| 10 00 06 0C | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |
| 10 00 06 0D | 0aaa aaaa | UNIDENTIFIED                        | 0 - 127 |



## VCO

| Address     |           | Description           | Value           |
| ----------- | --------- | --------------------- | --------------- |
| 10 00 08 00 | 0aaa aaaa | VCO SAW LEVEL         | 0 - 127         |
| 10 00 08 01 | 0aaa aaaa | VCO SQR LEVEL         | 0 - 127         |
| 10 00 08 02 | 0aaa aaaa | UNIDENTIFIED          | 0 - 127         |
| 10 00 08 03 | 0aaa aaaa | UNIDENTIFIED          | 0 - 127         |
| 10 00 08 04 | 0aaa aaaa | VCO SIN LEVEL         | 0 - 127         |
| 10 00 08 05 | 0aaa aaaa | VCO WHITE NOISE LEVEL | 0 - 127         |
| 10 00 08 06 | 0aaa aaaa | VCO PINK NOISE LEVEL  | 0 - 127         |
| 10 00 08 07 | 0aaa aaaa | VCO RING LEVEL        | 0 - 127         |
| 10 00 08 08 | 0000 000a | VCO SAW SW            | 0 - 1 (OFF, ON) |
| 10 00 08 09 | 0000 000a | VCO SQR SW            | 0 - 1 (OFF, ON) |
| 10 00 08 0A | 0000 000a | VCO SIN SW            | 0 - 1 (OFF, ON) |
| 10 00 08 0B | 0000 000a | VCO WHITE NOISE LEVEL | 0 - 1 (OFF, ON) |
| 10 00 08 0C | 0000 000a | VCO PINK NOISE LEVEL  | 0 - 1 (OFF, ON) |
| 10 00 08 0D | 0000 000a | VCO RING NOISE LEVEL  | 0 - 1 (OFF, ON) |



## VCF

| Address                      |                          | Description                  | Value   |
| ---------------------------- | ------------------------ | ---------------------------- | ------- |
| 10 00 0A 00<br />10 00 0A 01 | 0000 aaaa<br />0000 bbbb | VCF CUTOFF                   | 0 - 255 |
| 10 00 0A 02<br />10 00 0A 03 | 0000 aaaa<br />0000 bbbb | VCF RESONANCE                | 0 - 255 |
| 10 00 0A 04<br />10 00 0A 05 | 0000 aaaa<br />0000 bbbb | VCF ENVELOPE DEPTH (ENV MOD) | 0 - 255 |
| 10 00 0A 06                  | 0aaa aaaa                | VCF ENVELOPE ATTACK          | 0 - 127 |
| 10 00 0A 07                  | 0aaa aaaa                | VCF ENVELOPE DECAY           | 0 - 127 |
| 10 00 0A 08                  | 0aaa aaaa                | VCF ENVELOPE SUSTAIN         | 0 - 127 |
| 10 00 0A 09                  | 0aaa aaaa                | VCF ENVELOPE RELEASE         | 0 - 127 |
| 10 00 0A 0A                  | 0aaa aaaa                | VCF KEY FOLLOW               | 0 - 127 |



## VCA


| Address     |           | Description          | Value   |
| ----------- | --------- | -------------------- | ------- |
| 10 00 0C 00 | 0aaa aaaa | VCA ENVELOPE ATTACK  | 0 - 127 |
| 10 00 0C 01 | 0aaa aaaa | VCA ENVELOPE DECAY   | 0 - 127 |
| 10 00 0C 02 | 0aaa aaaa | VCA ENVELOPE SUSTAIN | 0 - 127 |
| 10 00 0C 03 | 0aaa aaaa | VCA ENVELOPE RELEASE | 0 - 127 |
| 10 00 0C 04 | 0aaa aaaa | MASTER VOLUME        | 0 - 127 |



# Effects Parameters

## Distortion

| Address     |           | Description   | Value                                                        |
| ----------- | --------- | ------------- | ------------------------------------------------------------ |
| 10 00 0E 00 | 0000 000a | DISTORTION SW | 0 - 1 (OFF, ON)                                              |
| 10 00 0E 01 | 000a aaaa | TYPE          | 0: Mid Boost, 1: Clean Boost, 2: Treble Bst, <br />3: Blues OD, 4: Crunch, 5: Natural OD, <br />6: OD-1, 7: T-Scream, 8: Turbo OD, <br />9: Warm OD, 10: Distortion, 11: Mild DS, <br />12: Mid DS, 13: RAT, 14: GUV DS, <br />15: DST+, 16: Modern DS, 17: Solid DS, <br />18: Stack, 19: Loud, 20: Metal Zone, <br />21: Lead, 22: '60s FUZZ, 23: Oct FUZZ, <br />24: MUFF FUZZ |
| 10 00 0E 02 | 0aaa aaaa | DRIVE         | 0 - 120                                                      |
| 10 00 0E 03 | 0aaa aaaa | BOTTOM        | 0 - 100 (-50 - 50)                                           |
| 10 00 0E 04 | 0aaa aaaa | TONE          | 0 - 100 (-50 - 50)                                           |
| 10 00 0E 05 | 0aaa aaaa | EFFECT LEVEL  | 0 - 100                                                      |
| 10 00 0E 06 | 0aaa aaaa | DRY LEVEL     | 0 - 100                                                      |
| 10 00 0E 07 | 0000 000a | COLOR         | 0 - 1                                                        |
| 10 00 0E 08 | 0000 000a | UNIDENTIFIED  | 0 - 1                                                        |



## EFX1

| Address     |           | Description | Value                                                        |
| ----------- | --------- | ----------- | ------------------------------------------------------------ |
| 10 00 10 00 | 0000 aaaa | EFX1 TYPE   | 0 - 10<br />(BYPASS, CS, RM, BC, TR, CH, FL, PH, DD, PS, EQ) |



### EFX1 : Compressor

| Address     |           | Description  | Value                       |
| ----------- | --------- | ------------ | --------------------------- |
| 10 00 10 01 | 0000 000a | CS SW        | 0 - 1 (OFF, ON)             |
| 10 00 10 02 | 0aaa aaaa | CS ATTACK    | 0 - 124 (0 - 800 [ms])      |
| 10 00 10 03 | 00aa aaaa | CS RELEASE   | 0 - 124 (0 - 800 [ms])      |
| 10 00 10 04 | 0000 aaaa | CS THRESHOLD | 0 - 40 (-40 - 0 [dB])       |
| 10 00 10 05 | 0000 aaaa | CS RATIO     | 0 - 13 (1:1.0 - 1:INF)      |
| 10 00 10 06 | 0000 aaaa | CS KNEE      | 0 - 9 (Hard, Soft1 - Soft9) |
| 10 00 10 07 | 0aaa aaaa | CS GAIN      | 0 - 80 (-40 - 40 [dB])      |
| 10 00 10 08 | 0aaa aaaa | CS BALANCE   | 0 - 100 (-50 - 50)          |



### EFX1 : Ring Modulator

| Address     |           | Description  | Value                  |
| ----------- | --------- | ------------ | ---------------------- |
| 10 00 10 09 | 0000 000a | RM SW        | 0 - 1 (OFF, ON)        |
| 10 00 10 0A | 0aaa aaaa | RM FREQUENCY | 0 - 127                |
| 10 00 10 0B | 0aaa aaaa | RM SENS      | 0 - 127                |
| 10 00 10 0C | 0000 000a | RM POLARITY  | 0 - 1 (UP, DOWN)       |
| 10 00 10 0D | 000a aaaa | RM EQ LOW    | 0 - 30 (-15 - 15 [dB]) |
| 10 00 10 0E | 000a aaaa | RM EQ HIGH   | 0 - 30 (-15 - 15 [dB]) |
| 10 00 10 0F | 0aaa aaaa | RM BALANCE   | 0 - 100 (-50 - 50) )   |
| 10 00 10 10 | 0aaa aaaa | RM LEVEL     | 0 - 127                |





### EFX1 : Bit Crasher
| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 10 11 | 0000 000a | BC SW|0 - 1 (OFF, ON)|
| 10 00 10 12 | 0aaa aaaa | BC FILTER| 0 - 127|
| 10 00 10 13 | 0aaa aaaa | BC SAMPLE RATE|0 - 127|
| 10 00 10 14 | 0aaa aaaa | UNIDENTIFIED|0 - 20|
| 10 00 10 15 | 000a aaaa | BC EQ LOW|0 - 30 (-15 - 15 [dB])|
| 10 00 10 16 | 000a aaaa | BC EQ HIGH|0 - 30 (-15 - 15 [dB])|
| 10 00 10 17 | 0aaa aaaa | BC LEVEL|0 - 127|



### EFX1 : Tremolo

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 10 18 | 0000 000a | TR SW|0 - 1 (OFF, ON)|
| 10 00 10 19 | 0000 0aaa | TR TYPE|0 - 5 (TRI, SAW1, SAW2, SIN, SQUARE, RAND)|
| 10 00 10 1A | 0aaa aaaa | TR PHASE|0 - 100 ( 0 - 360°) |
| 10 00 10 1B | 0aaa aaaa | TR RATE|0 - 100 (8000 - 20 [ms])|
| 10 00 10 1C | 000a aaaa | TR BPM SYNC|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 10 1D | 0aaa aaaa | TR SHAPE|0 - 100|
| 10 00 10 1E | 0aaa aaaa | TR DEPTH|0 - 100|
| 10 00 10 1F | 0000 000a | TR PAN SELECT|0 - 1 (TRE, PAN)|
| 10 00 10 20 | 0aaa aaaa | TR LEVEL|0 - 100|



### EFX1 : Chorus

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 10 21 | 0000 000a | CH SW|0 - 1 (OFF, ON)|
| 10 00 10 22 | 0000 00aa | CH MODE |0 - 2 (MONO, STEREO1, STEREO2|
| 10 00 10 23 | 0aaa aaaa | CH RATE|0 - 100 (8000 - 20 [ms])|
| 10 00 10 24 | 000a aaaa | CH BPM SYNC|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 10 25 | 0aaa aaaa | CH DEPTH|0 - 100|
| 10 00 10 26 | 0aaa aaaa | CH PRE DELAY|0 - 80 (0 - 80 [ms]) |
| 10 00 10 27 | 000a aaaa | CH HPF|0 - 17 (Flat - 800 [Hz]) |
| 10 00 10 28 | 0000 aaaa | CH LPF|0 - 14 (630 [Hz] - Flat)|
| 10 00 10 29 | 0aaa aaaa | CH LEVEL|0 - 100|



### EFX1 : Flanger

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 10 2A | 0000 000a | FL SW|0 - 1 (OFF, ON)|
| 10 00 10 2B | 0aaa aaaa | FL RATE|0 - 100 (8000 - 20 [ms])|
| 10 00 10 2C | 000a aaaa | FL BPM SYNC|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 10 2D | 0aaa aaaa | FL DEPTH|0 - 100|
| 10 00 10 2E | 0aaa aaaa | FL MANUAL|0 - 100 (-50 - 50)|
| 10 00 10 2F | 0aaa aaaa | FL RESONANCE|0 - 100|
| 10 00 10 30 | 0aaa aaaa | FL SEPARATION|0 - 100|
| 10 00 10 31 | 0000 aaaa | FL HPF|0 - 10 (Flat - 800 [Hz])|
| 10 00 10 32 | 0aaa aaaa | FL EFFECT LEVEL|0 - 100|
| 10 00 10 33 | 0aaa aaaa | FL DIRECT LEVEL|0 - 100|



### EFX1 : Phaser

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 10 34 | 0000 000a | PH SW|0 - 1 (OFF, ON)|
| 10 00 10 35 | 0000 00aa | PH TYPE|0 - 3 (4Stage, 8Stage, 12Stage, Bi-Phase)|
| 10 00 10 36 | 0aaa aaaa | PH RATE|0 - 100 (8000 - 20 [ms])|
| 10 00 10 37 | 000a aaaa | PH BPM SYNC|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 10 38 | 0aaa aaaa | PH DEPTH|0 - 100|
| 10 00 10 39 | 0aaa aaaa | PH MANUAL|0 - 100 (-50 - 50)|
| 10 00 10 3A | 0aaa aaaa | PH RESONANCE|0 - 127|
| 10 00 10 3B | 000a aaaa | PH STEP RATE|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 10 3C | 0aaa aaaa | PH EFFECT LEVEL|0 - 100|
| 10 00 10 3D | 0aaa aaaa | PH DIRECT LEVEL|0 - 100|



### EFX1 : Delay

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 10 3E | 0000 000a | DD SW|0 - 1 (OFF, ON)|
| 10 00 10 3F | 0000 00aa | DD TYPE|0 - 2 (SINGLE, PAN, STEREO)|
| 10 00 10 40 | 0aaa aaaa | DD TIME|0 - 100 (0 - 100 [ms])|
| 10 00 10 41 | 0aaa aaaa | DD TAP TIME|0 - 100 (0 - 100 [ms])|
| 10 00 10 42 | 000a aaaa | DD BPM SYNC |0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 10 43 | 0aaa aaaa | DD FEEDBACK|0 - 100|
| 10 00 10 44 | 0000 aaaa | DD LPF|0 - 14 (630 [Hz] - Flat)|
| 10 00 10 45 | 0aaa aaaa | DD EFFECT LEVEL|0 - 100|
| 10 00 10 46 | 0aaa aaaa | DD DIRECT LEVEL|0 - 100|



### EFX1 : Pitch Shifter

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 10 47 | 0000 000a | PS SW|0 - 1 (OFF, ON)|
| 10 00 10 48 | 0000 00aa | PS VOICE|0 - 2 (1MONO, 2MONO, 2Stereo)|
| 10 00 10 49 | 00aa aaaa | PS 1 PITCH|0 - 48 (-2400 - 2400 [Cent] )|
| 10 00 10 4A | 0aaa aaaa | PS 1 PRE DELAY|0 - 100 (0 - 100 [ms])|
| 10 00 10 4B | 0aaa aaaa | PS FEEDBACK|0 - 100|
| 10 00 10 4C | 0aaa aaaa | PS 1 EFX LEVEL|0 - 100|
| 10 00 10 4D | 00aa aaaa | PS 2 PITCH|0 - 48 (-2400 - 2400 [Cent])|
| 10 00 10 4E | 0aaa aaaa | PS 2 PRE DELAY|0 - 100 (0 - 100 [ms])|
| 10 00 10 4F | 0000 0000 | UNIDENTIFIED|0 - 0|
| 10 00 10 50 | 0aaa aaaa | PS 2 EFX LEVEL|0 - 100|
| 10 00 10 51 | 0aaa aaaa | PS DIRECT LEVEL|0 - 100|
| 10 00 10 52 | 000a aaaa | UNIDENTIFIED|0 - 30|



### EFX1 : EQ

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 10 53 | 0000 000a | EQ SW|0 - 1 (OFF, ON)|
| 10 00 10 54 | 000a aaaa | EQ LOW CUT|0 - 17 (Flat - 800 [Hz] )|
| 10 00 10 55 | 00aa aaaa | EQ LOW GAIN|0 - 40 (-20 - 20 [dB])|
| 10 00 10 56 | 000a aaaa | EQ LOW MID FREQ|0 - 27 (20.0 - 10.0k [Hz] )|
| 10 00 10 57 | 0000 0aaa | EQ LOW MID Q|0 - 5 (0.5 - 16)|
| 10 00 10 58 | 00aa aaaa | EQ LOW MID GAIN|0 - 40 (-20 - 20 [dB])|
| 10 00 10 59 | 000a aaaa | EQ HIGH MID FREQ|0 - 27 (20.0 - 10.0k [Hz] )|
| 10 00 10 5A | 0000 0aaa | EQ HIGH MID Q|0 - 5 (0.5 - 16)|
| 10 00 10 5B | 00aa aaaa | EQ HIGH MID GAIN|0 - 40 (-20 - 20 [dB])|
| 10 00 10 5C | 0000 aaaa | EQ HIGH CUT|0 - 14 ( 630 [Hz] - Flat)|
| 10 00 10 5D | 00aa aaaa | EQ HIGH GAIN|0 - 40 (-20 - 20 [dB])|
| 10 00 10 5E | 00aa aaaa | EQ LEVEL|0 - 40 (-20 - 20 [dB])|



## EFX2

| Address     |           | Description | Value                                                        |
| ----------- | --------- | ----------- | ------------------------------------------------------------ |
| 10 00 12 00 | 0000 aaaa | EFX2 TYPE   | 0 - 10<br />(BYPASS, CS, RM, BC, TR, CH, FL, PH, DD, PS, EQ) |



### EFX2 : Compressor

| Address     |           | Description  | Value                       |
| ----------- | --------- | ------------ | --------------------------- |
| 10 00 12 01 | 0000 000a | CS SW        | 0 - 1 (OFF, ON)             |
| 10 00 12 02 | 0aaa aaaa | CS ATTACK    | 0 - 124 (0 - 800 [ms])      |
| 10 00 12 03 | 00aa aaaa | CS RELEASE   | 0 - 124 (0 - 800 [ms])      |
| 10 00 12 04 | 0000 aaaa | CS THRESHOLD | 0 - 40 (-40 - 0 [dB])       |
| 10 00 12 05 | 0000 aaaa | CS RATIO     | 0 - 13 (1:1.0 - 1:INF)      |
| 10 00 12 06 | 0000 aaaa | CS KNEE      | 0 - 9 (Hard, Soft1 - Soft9) |
| 10 00 12 07 | 0aaa aaaa | CS GAIN      | 0 - 80 (-40 - 40 [dB])      |
| 10 00 12 08 | 0aaa aaaa | CS BALANCE   | 0 - 100 (-50 - 50)          |



### EFX2 : Ring Modulator

| Address     |           | Description  | Value                  |
| ----------- | --------- | ------------ | ---------------------- |
| 10 00 12 09 | 0000 000a | RM SW        | 0 - 1 (OFF, ON)        |
| 10 00 12 0A | 0aaa aaaa | RM FREQUENCY | 0 - 127                |
| 10 00 12 0B | 0aaa aaaa | RM SENS      | 0 - 127                |
| 10 00 12 0C | 0000 000a | RM POLARITY  | 0 - 1 (UP, DOWN)       |
| 10 00 12 0D | 000a aaaa | RM EQ LOW    | 0 - 30 (-15 - 15 [dB]) |
| 10 00 12 0E | 000a aaaa | RM EQ HIGH   | 0 - 30 (-15 - 15 [dB]) |
| 10 00 12 0F | 0aaa aaaa | RM BALANCE   | 0 - 100 (-50 - 50) )   |
| 10 00 12 10 | 0aaa aaaa | RM LEVEL     | 0 - 127                |





### EFX2 : Bit Crasher
| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 12 11 | 0000 000a | BC SW|0 - 1 (OFF, ON)|
| 10 00 12 12 | 0aaa aaaa | BC FILTER| 0 - 127|
| 10 00 12 13 | 0aaa aaaa | BC SAMPLE RATE|0 - 127|
| 10 00 12 14 | 0aaa aaaa | UNIDENTIFIED|0 - 20|
| 10 00 12 15 | 000a aaaa | BC EQ LOW|0 - 30 (-15 - 15 [dB])|
| 10 00 12 16 | 000a aaaa | BC EQ HIGH|0 - 30 (-15 - 15 [dB])|
| 10 00 12 17 | 0aaa aaaa | BC LEVEL|0 - 127|



### EFX2 : Tremolo

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 12 18 | 0000 000a | TR SW|0 - 1 (OFF, ON)|
| 10 00 12 19 | 0000 0aaa | TR TYPE|0 - 5 (TRI, SAW1, SAW2, SIN, SQUARE, RAND)|
| 10 00 12 1A | 0aaa aaaa | TR PHASE|0 - 100 ( 0 - 360°) |
| 10 00 12 1B | 0aaa aaaa | TR RATE|0 - 100 (8000 - 20 [ms])|
| 10 00 12 1C | 000a aaaa | TR BPM SYNC|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 12 1D | 0aaa aaaa | TR SHAPE|0 - 100|
| 10 00 12 1E | 0aaa aaaa | TR DEPTH|0 - 100|
| 10 00 12 1F | 0000 000a | TR PAN SELECT|0 - 1 (TRE, PAN)|
| 10 00 12 20 | 0aaa aaaa | TR LEVEL|0 - 100|



### EFX2 : Chorus

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 12 21 | 0000 000a | CH SW|0 - 1 (OFF, ON)|
| 10 00 12 22 | 0000 00aa | CH MODE |0 - 2 (MONO, STEREO1, STEREO2|
| 10 00 12 23 | 0aaa aaaa | CH RATE|0 - 100 (8000 - 20 [ms])|
| 10 00 12 24 | 000a aaaa | CH BPM SYNC|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 12 25 | 0aaa aaaa | CH DEPTH|0 - 100|
| 10 00 12 26 | 0aaa aaaa | CH PRE DELAY|0 - 80 (0 - 80 [ms]) |
| 10 00 12 27 | 000a aaaa | CH HPF|0 - 17 (Flat - 800 [Hz]) |
| 10 00 12 28 | 0000 aaaa | CH LPF|0 - 14 (630 [Hz] - Flat)|
| 10 00 12 29 | 0aaa aaaa | CH LEVEL|0 - 100|



### EFX2 : Flanger

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 12 2A | 0000 000a | FL SW|0 - 1 (OFF, ON)|
| 10 00 12 2B | 0aaa aaaa | FL RATE|0 - 100 (8000 - 20 [ms])|
| 10 00 12 2C | 000a aaaa | FL BPM SYNC|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 12 2D | 0aaa aaaa | FL DEPTH|0 - 100|
| 10 00 12 2E | 0aaa aaaa | FL MANUAL|0 - 100 (-50 - 50)|
| 10 00 12 2F | 0aaa aaaa | FL RESONANCE|0 - 100|
| 10 00 12 30 | 0aaa aaaa | FL SEPARATION|0 - 100|
| 10 00 12 31 | 0000 aaaa | FL HPF|0 - 10 (Flat - 800 [Hz])|
| 10 00 12 32 | 0aaa aaaa | FL EFFECT LEVEL|0 - 100|
| 10 00 12 33 | 0aaa aaaa | FL DIRECT LEVEL|0 - 100|



### EFX2 : Phaser

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 12 34 | 0000 000a | PH SW|0 - 1 (OFF, ON)|
| 10 00 12 35 | 0000 00aa | PH TYPE|0 - 3 (4Stage, 8Stage, 12Stage, Bi-Phase)|
| 10 00 12 36 | 0aaa aaaa | PH RATE|0 - 100 (8000 - 20 [ms])|
| 10 00 12 37 | 000a aaaa | PH BPM SYNC|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 12 38 | 0aaa aaaa | PH DEPTH|0 - 100|
| 10 00 12 39 | 0aaa aaaa | PH MANUAL|0 - 100 (-50 - 50)|
| 10 00 12 3A | 0aaa aaaa | PH RESONANCE|0 - 127|
| 10 00 12 3B | 000a aaaa | PH STEP RATE|0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 12 3C | 0aaa aaaa | PH EFFECT LEVEL|0 - 100|
| 10 00 12 3D | 0aaa aaaa | PH DIRECT LEVEL|0 - 100|



### EFX2 : Delay

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 12 3E | 0000 000a | DD SW|0 - 1 (OFF, ON)|
| 10 00 12 3F | 0000 00aa | DD TYPE|0 - 2 (SINGLE, PAN, STEREO)|
| 10 00 12 40 | 0aaa aaaa | DD TIME|0 - 100 (0 - 100 [ms])|
| 10 00 12 41 | 0aaa aaaa | DD TAP TIME|0 - 100 (0 - 100 [ms])|
| 10 00 12 42 | 000a aaaa | DD BPM SYNC |0 - 20 (OFF, 2, 3/2, 4/3, 1, 3/4, 2/3, 1/2, 3/8, <br />1/3, 1/4, 3/16, 1/6, 1/8, 3/32, 1/12, 1/16, <br />3/64, 1/24, 1/32, 3/128)|
| 10 00 12 43 | 0aaa aaaa | DD FEEDBACK|0 - 100|
| 10 00 12 44 | 0000 aaaa | DD LPF|0 - 14 (630 [Hz] - Flat)|
| 10 00 12 45 | 0aaa aaaa | DD EFFECT LEVEL|0 - 100|
| 10 00 12 46 | 0aaa aaaa | DD DIRECT LEVEL|0 - 100|



### EFX2 : Pitch Shifter

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 12 47 | 0000 000a | RV SW|0 - 1 (OFF, ON)|
| 10 00 12 48 | 0000 0aaa | RV TYPE|0 - 6 (AMBIENT, ROOM, HALL1, HALL2, <br />PLATE, SPRING, MODULATION )|
| 10 00 12 49 | 0aaa aaaa | RV TIME|0 - 99|
| 10 00 12 4A | 0aaa aaaa | RV PRE DELAY|0 - 100 (0 - 100 [ms] )|
| 10 00 12 4B | 000a aaaa | RV HPF|0 - 17 (Flat - 800 [Hz])|
| 10 00 12 4C | 0000 aaaa | RV LPF|0 - 14 (630 [Hz] - Flat)|
| 10 00 12 4D | 0000 aaaa | RV DENSITY|0 - 10|
| 10 00 12 4E | 0aaa aaaa | RV EFFECT LEVEL|0 - 100|
| 10 00 12 4F | 0aaa aaaa | RV DIRECT LEVEL|0 - 100|
| 10 00 12 50 | 0aaa aaaa | RV SPRING SENS|0 - 100|
| 10 00 12 51<br />10 00 12 52 | 0000 aaaa<br />0000 bbbb | UNIDENTIFIED|0 - 255|
| 10 00 12 53 | 000a aaaa | UNIDENTIFIED|0 - 30|



# Parameter Assign

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 10 00 14 00 | 0000 000a | PORTAMENT SW|0 - 1 (OFF, ON)|
|          01 | 0aaa aaaa | PORTAMENT TIME|0 - 127|
|          02 | 0000 000a | PORTAMENT MODE|0 - 1 (LEGATO, ALWAYS)|
|          03 | 0000 aaaa | BENDER RANGE|0 - 17|
|04<br />05 | 0000 aaaa<br />0000 bbbb | PARAMETER ID (PAD MODULATION) (*1) |0 - 255|
|06<br />07 | 0000 aaaa<br />0000 bbbb | PARAMETER ID (EFFECT KNOB) (*1) |0 - 255|
|          08<br />09 | 0000 aaaa<br />0000 bbbb | PARAMETER ID (PAD X) (*1) |0 - 255|
|          0A<br />0B | 0000 aaaa<br />0000 bbbb | PARAMETER ID (PAD Y) (*1) |0 - 255|
|          0C | 0000 aaaa | UNIDENTIFIED|0 - 15|
|          0D | 0000 aaaa | UNIDENTIFIED|0 - 15|
|          0E<br />0F | 0000 aaaa<br />0000 bbbb | ACCENT|0 - 255|
|          10 | 0aaa aaaa | UNIDENTIFIED|0 - 100|
|          11 | 0aaa aaaa | UNIDENTIFIED|0 - 100|



# Pattern Parameters

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 30 00 00 00 | 0000 000a | TRIPLET|0 - 1 (OFF, ON)|
|          01 | 000a aaaa | PATTERN LENGTH|0 - 31|
|          02 | 0aaa aaaa | GATE TIME|0 - 127|



## Pitch

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 30 00 02 00 | 0aaa aaaa | STEP 1 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 01 | 0aaa aaaa | STEP 2 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 02 | 0aaa aaaa | STEP 3 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 03 | 0aaa aaaa | STEP 4 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 04 | 0aaa aaaa | STEP 5 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 05 | 0aaa aaaa | STEP 6 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 06 | 0aaa aaaa | STEP 7 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 07 | 0aaa aaaa | STEP 8 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 08 | 0aaa aaaa | STEP 9 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 09 | 0aaa aaaa | STEP 10 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 0A | 0aaa aaaa | STEP 11 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 0B | 0aaa aaaa | STEP 12 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 0C | 0aaa aaaa | STEP 13 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 0D | 0aaa aaaa | STEP 14 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 0E | 0aaa aaaa | STEP 15 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 0F | 0aaa aaaa | STEP 16 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 10 | 0aaa aaaa | STEP 17 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 11 | 0aaa aaaa | STEP 18 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 12 | 0aaa aaaa | STEP 19 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 13 | 0aaa aaaa | STEP 20 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 14 | 0aaa aaaa | STEP 21 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 15 | 0aaa aaaa | STEP 22 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 16 | 0aaa aaaa | STEP 23 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 17 | 0aaa aaaa | STEP 24 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 18 | 0aaa aaaa | STEP 25 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 19 | 0aaa aaaa | STEP 26 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 1A | 0aaa aaaa | STEP 27 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 1B | 0aaa aaaa | STEP 28 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 1C | 0aaa aaaa | STEP 29 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 1D | 0aaa aaaa | STEP 30 PITCH|12 - 108 (C-2 - C7)|
| 30 00 02 1E | 0aaa aaaa | STEP 31 PITCH|12 - 10 8(C-2 - C7)|
| 30 00 02 1F | 0aaa aaaa | STEP 32 PITCH|12 - 108 (C-2 - C7)|



## Slide

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 30 00 04 00 | 0000 000a | STEP 1 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 01 | 0000 000a | STEP 2 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 02 | 0000 000a | STEP 3 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 03 | 0000 000a | STEP 4 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 04 | 0000 000a | STEP 5 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 05 | 0000 000a | STEP 6 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 06 | 0000 000a | STEP 7 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 07 | 0000 000a | STEP 8 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 08 | 0000 000a | STEP 9 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 09 | 0000 000a | STEP 10 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 0A | 0000 000a | STEP 11 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 0B | 0000 000a | STEP 12 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 0C | 0000 000a | STEP 13 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 0D | 0000 000a | STEP 14 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 0E | 0000 000a | STEP 15 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 0F | 0000 000a | STEP 16 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 10 | 0000 000a | STEP 17 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 11 | 0000 000a | STEP 18 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 12 | 0000 000a | STEP 19 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 13 | 0000 000a | STEP 20 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 14 | 0000 000a | STEP 21 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 15 | 0000 000a | STEP 22 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 16 | 0000 000a | STEP 23 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 17 | 0000 000a | STEP 24 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 18 | 0000 000a | STEP 25 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 19 | 0000 000a | STEP 26 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 1A | 0000 000a | STEP 27 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 1B | 0000 000a | STEP 28 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 1C | 0000 000a | STEP 29 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 1D | 0000 000a | STEP 30 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 1E | 0000 000a | STEP 31 SLIDE|0 - 1 (OFF, ON)|
| 30 00 04 1F | 0000 000a | STEP 32 SLIDE|0 - 1 (OFF, ON)|



## Gate

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 30 00 06 00 | 0000 000a | STEP 1 GATE|0 - 1 (OFF, ON)|
| 30 00 06 01 | 0000 000a | STEP 2 GATE|0 - 1 (OFF, ON)|
| 30 00 06 02 | 0000 000a | STEP 3 GATE|0 - 1 (OFF, ON)|
| 30 00 06 03 | 0000 000a | STEP 4 GATE|0 - 1 (OFF, ON)|
| 30 00 06 04 | 0000 000a | STEP 5 GATE|0 - 1 (OFF, ON)|
| 30 00 06 05 | 0000 000a | STEP 6 GATE|0 - 1 (OFF, ON)|
| 30 00 06 06 | 0000 000a | STEP 7 GATE|0 - 1 (OFF, ON)|
| 30 00 06 07 | 0000 000a | STEP 8 GATE|0 - 1 (OFF, ON)|
| 30 00 06 08 | 0000 000a | STEP 9 GATE|0 - 1 (OFF, ON)|
| 30 00 06 09 | 0000 000a | STEP 10 GATE|0 - 1 (OFF, ON)|
| 30 00 06 0A | 0000 000a | STEP 11 GATE|0 - 1 (OFF, ON)|
| 30 00 06 0B | 0000 000a | STEP 12 GATE|0 - 1 (OFF, ON)|
| 30 00 06 0C | 0000 000a | STEP 13 GATE|0 - 1 (OFF, ON)|
| 30 00 06 0D | 0000 000a | STEP 14 GATE|0 - 1 (OFF, ON)|
| 30 00 06 0E | 0000 000a | STEP 15 GATE|0 - 1 (OFF, ON)|
| 30 00 06 0F | 0000 000a | STEP 16 GATE|0 - 1 (OFF, ON)|
| 30 00 06 10 | 0000 000a | STEP 17 GATE|0 - 1 (OFF, ON)|
| 30 00 06 11 | 0000 000a | STEP 18 GATE|0 - 1 (OFF, ON)|
| 30 00 06 12 | 0000 000a | STEP 19 GATE|0 - 1 (OFF, ON)|
| 30 00 06 13 | 0000 000a | STEP 20 GATE|0 - 1 (OFF, ON)|
| 30 00 06 14 | 0000 000a | STEP 21 GATE|0 - 1 (OFF, ON)|
| 30 00 06 15 | 0000 000a | STEP 22 GATE|0 - 1 (OFF, ON)|
| 30 00 06 16 | 0000 000a | STEP 23 GATE|0 - 1 (OFF, ON)|
| 30 00 06 17 | 0000 000a | STEP 24 GATE|0 - 1 (OFF, ON)|
| 30 00 06 18 | 0000 000a | STEP 25 GATE|0 - 1 (OFF, ON)|
| 30 00 06 19 | 0000 000a | STEP 26 GATE|0 - 1 (OFF, ON)|
| 30 00 06 1A | 0000 000a | STEP 27 GATE|0 - 1 (OFF, ON)|
| 30 00 06 1B | 0000 000a | STEP 28 GATE|0 - 1 (OFF, ON)|
| 30 00 06 1C | 0000 000a | STEP 29 GATE|0 - 1 (OFF, ON)|
| 30 00 06 1D | 0000 000a | STEP 30 GATE|0 - 1 (OFF, ON)|
| 30 00 06 1E | 0000 000a | STEP 31 GATE|0 - 1 (OFF, ON)|
| 30 00 06 1F | 0000 000a | STEP 32 GATE|0 - 1 (OFF, ON)|



## Accent

| Address |      | Description | Value |
| ------- | ---- | ----------- | ----- |
| 30 00 08 00 | 0000 000a | STEP 1 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 01 | 0000 000a | STEP 2 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 02 | 0000 000a | STEP 3 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 03 | 0000 000a | STEP 4 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 04 | 0000 000a | STEP 5 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 05 | 0000 000a | STEP 6 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 06 | 0000 000a | STEP 7 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 07 | 0000 000a | STEP 8 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 08 | 0000 000a | STEP 9 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 09 | 0000 000a | STEP 10 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 0A | 0000 000a | STEP 11 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 0B | 0000 000a | STEP 12 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 0C | 0000 000a | STEP 13 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 0D | 0000 000a | STEP 14 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 0E | 0000 000a | STEP 15 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 0F | 0000 000a | STEP 16 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 10 | 0000 000a | STEP 17 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 11 | 0000 000a | STEP 18 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 12 | 0000 000a | STEP 19 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 13 | 0000 000a | STEP 20 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 14 | 0000 000a | STEP 21 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 15 | 0000 000a | STEP 22 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 16 | 0000 000a | STEP 23 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 17 | 0000 000a | STEP 24 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 18 | 0000 000a | STEP 25 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 19 | 0000 000a | STEP 26 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 1A | 0000 000a | STEP 27 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 1B | 0000 000a | STEP 28 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 1C | 0000 000a | STEP 29 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 1D | 0000 000a | STEP 30 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 1E | 0000 000a | STEP 31 ACCENT|0 - 1 (OFF, ON)|
| 30 00 08 1F | 0000 000a | STEP 32 ACCENT|0 - 1 (OFF, ON)|



# (*1) Parameter IDs

| ID    | Parameter Name                           |
| ----- | ---------------------------------------- |
| 00 00 | LFO RATE                                 |
| 00 01 | LFO DELAY                                |
| 00 02 | LFO WAVE SAW                             |
| 00 03 | LFO WAVE SQR                             |
| 00 04 | LFO WAVE TRI                             |
| 00 05 | LFO WAVE SIN                             |
| 00 06 | CV OFFSET LFO                            |
| 00 07 | LFO WAVE S&H                             |
| 00 08 | VCO LFO DEPTH                            |
| 00 09 | VCF LFO DEPTH                            |
| 00 0A | VCA LFO DEPTH                            |
| 00 0B | BPM SYNC                                 |
| 00 0C | LFO RETRIGGER                            |
| 00 0D | CV OFFSET TO SQR PITCH                   |
| 00 0E | CV OFFSET TO SAW PITCH                   |
| 00 0F | CV OFFSET TO RING PITCH                  |
| 01 00 | CROSS MODULATION DEPTH (SQR>SAW)         |
| 01 01 | UNIDENTIFIED                             |
| 01 02 | CROSS MODULATION DEPTH (SAW>SAW)         |
| 01 03 | CROSS MODULATION DEPTH (WHITE NOISE>SAW) |
| 01 04 | CROSS MODULATION DEPTH (PINK NOISE>SAW)  |
| 01 05 | CROSS MODULATION DEPTH (SQR>SQR)         |
| 01 06 | UNIDENTIFIED                             |
| 01 07 | CROSS MODULATION DEPTH (SAW>SQR)         |
| 01 08 | CROSS MODULATION DEPTH (WHITE NOISE>SQR) |
| 01 09 | CROSS MODULATION DEPTH (PINK NOISE>SQR)  |
| 01 0A | RING MODULATION DEPTH (SAW)              |
| 01 0B | RING MODULATION DEPTH (SQR)              |
| 01 0C | UNIDENTIFIED                             |
| 01 0D | UNIDENTIFIED                             |
| 01 0E | RING MODULATION DEPTH (RING)             |
| 01 0F | RING MODULATION DEPTH (WHITE NOISE)      |
| 02 00 | RING MODULATION DEPTH (PINK NOISE)       |
| 02 01 | UNIDENTIFIED                             |
| 02 02 | UNIDENTIFIED                             |
| 02 03 | UNIDENTIFIED                             |
| 02 04 | UNIDENTIFIED                             |
| 02 05 | UNIDENTIFIED                             |
| 02 06 | UNIDENTIFIED                             |
| 02 07 | UNIDENTIFIED                             |
| 02 08 | VCO SAW LEVEL                            |
| 02 09 | VCO SQR LEVEL                            |
| 02 0A | UNIDENTIFIED                             |
| 02 0B | UNIDENTIFIED                             |
| 02 0C | VCO SIN LEVEL                            |
| 02 0D | VCO WHITE NOISE LEVEL                    |
| 02 0E | VCO PINK NOISE LEVEL                     |
| 02 0F | VCO RING LEVEL                           |
| 03 00 | VCO SAW SW                               |
| 03 01 | VCO SQR SW                               |
| 03 02 | VCO SIN SW                               |
| 03 03 | VCO WHITE NOISE SW                       |
| 03 04 | VCO PINK NOISE SW                        |
| 03 05 | VCO RING SW                              |
| 03 06 | VCF CUTOFF                               |
| 03 07 | VCF RESONANCE                            |
| 03 08 | VCF ENVELOPE DEPTH (ENV MOD)             |
| 03 09 | VCF ENVELOPE ATTACK                      |
| 03 0A | VCF ENVELOPE DECAY                       |
| 03 0B | VCF ENVELOPE SUSTAIN                     |
| 03 0C | VCF ENVELOPE RELEASE                     |
| 03 0D | VCF KEY FOLLOW                           |
| 03 0E | VCA ENVELOPE ATTACK                      |
| 03 0F | VCA ENVELOPE DECAY                       |
| 04 00 | VCA ENVELOPE SUSTAIN                     |
| 04 01 | VCA ENVELOPE RELEASE                     |
| 04 02 | MASTER VOLUME                            |
| 04 03 | DISTORTION SW                            |
| 04 04 | TYPE                                     |
| 04 05 | DRIVE                                    |
| 04 06 | BOTTOM                                   |
| 04 07 | TONE                                     |
| 04 08 | EFFECT LEVEL                             |
| 04 09 | DRY LEVEL                                |
| 04 0A | COLOR                                    |
| 04 0B | UNIDENTIFIED                             |
| 04 0C | EFX1 TYPE                                |
| 04 0D | EFX1 CS SW                               |
| 04 0E | EFX1 CS ATTACK                           |
| 04 0F | EFX1 CS RELEASE                          |
| 05 00 | EFX1 THRESHOLD                           |
| 05 01 | EFX1 CS RATIO                            |
| 05 02 | EFX1 CS KNEE                             |
| 05 03 | EFX1 CS GAIN                             |
| 05 04 | EFX1 CS BALANCE                          |
| 05 05 | EFX1 RM SW                               |
| 05 06 | EFX1 RM FREQUENCY                        |
| 05 07 | EFX1 RM SENS                             |
| 05 08 | EFX1 RM POLARITY                         |
| 05 09 | EFX1 RM EQ LOW                           |
| 05 0A | EFX1 RM EQ HIGH                          |
| 05 0B | EFX1 RM BALANCE                          |
| 05 0C | EFX1 RM LEVEL                            |
| 05 0D | EFX1 BC SW                               |
| 05 0E | EFX1 BC FILTER                           |
| 05 0F | EFX1 BC SAMPLE RATE                      |
| 06 00 | EFX1 UNIDENTIFIED                        |
| 06 01 | EFX1 BC EQ LOW                           |
| 06 02 | EFX1 BC EQ HIGH                          |
| 06 03 | EFX1 BC LEVEL                            |
| 06 04 | EFX1 TR SW                               |
| 06 05 | EFX1 TR TYPE                             |
| 06 06 | EFX1 TR PHASE                            |
| 06 07 | EFX1 TR RATE                             |
| 06 08 | EFX1 TR BPM SYNC                         |
| 06 09 | EFX1 TR SHAPE                            |
| 06 0A | EFX1 TR DEPTH                            |
| 06 0B | EFX1 TR PAN SELECT                       |
| 06 0C | EFX1 TR LEVEL                            |
| 06 0D | EFX1 CH SW                               |
| 06 0E | EFX1 CH MODE                             |
| 06 0F | EFX1 CH RATE                             |
| 07 00 | EFX1 CH BPM SYNC                         |
| 07 01 | EFX1 CH DEPTH                            |
| 07 02 | EFX1 CH PRE DELAY                        |
| 07 03 | EFX1 CH HPF                              |
| 07 04 | EFX1 CH LPF                              |
| 07 05 | EFX1 CH LEVEL                            |
| 07 06 | EFX1 FL SW                               |
| 07 07 | EFX1 FL RATE                             |
| 07 08 | EFX1 FL BPM SYNC                         |
| 07 09 | EFX1 FL DEPTH                            |
| 07 0A | EFX1 FL MANUAL                           |
| 07 0B | EFX1 FL RESONANCE                        |
| 07 0C | EFX1 FL SEPARATION                       |
| 07 0D | EFX1 FL HPF                              |
| 07 0E | EFX1 FL EFFECT LEVEL                     |
| 07 0F | EFX1 FL DIRECT LEVEL                     |
| 08 00 | EFX1 PH SW                               |
| 08 01 | EFX1 PH TYPE                             |
| 08 02 | EFX1 PH RATE                             |
| 08 03 | EFX1 PH BPM SYNC                         |
| 08 04 | EFX1 PH DEPTH                            |
| 08 05 | EFX1 PH MANUAL                           |
| 08 06 | EFX1 PH RESONANCE                        |
| 08 07 | EFX1 PH STEP RATE                        |
| 08 08 | EFX1 PH EFFECT LEVEL                     |
| 08 09 | EFX1 PH DIRECT LEVEL                     |
| 08 0A | EFX1 DD SW                               |
| 08 0B | EFX1 DD TYPE                             |
| 08 0C | EFX1 DD TIME                             |
| 08 0D | EFX1 DD TAP TIME                         |
| 08 0E | EFX1 DD BPM SYNC                         |
| 08 0F | EFX1 DD FEEDBACK                         |
| 09 00 | EFX1 DD LPF                              |
| 09 01 | EFX1 DD EFFECT LEVEL                     |
| 09 02 | EFX1 DD DIRECT LEVEL                     |
| 09 03 | EFX1 PS SW                               |
| 09 04 | EFX1 PS VOICE                            |
| 09 05 | EFX1 PS 1 PITCH                          |
| 09 06 | EFX1 PS 1 PRE DELAY                      |
| 09 07 | EFX1 PS FEEDBACK                         |
| 09 08 | EFX1 PS 1 EFX LEVEL                      |
| 09 09 | EFX1 PS 2 PITCH                          |
| 09 0A | EFX1 PS 2 PRE DELAY                      |
| 09 0B | EFX1 UNIDENTIFIED                        |
| 09 0C | EFX1 PS 2 EFX LEVEL                      |
| 09 0D | EFX1 PS DIRECT LEVEL                     |
| 09 0E | EFX1 UNIDENTIFIED                        |
| 09 0F | EFX1 EQ SW                               |
| 0A 00 | EFX1 EQ LOW CUT                          |
| 0A 01 | EFX1 EQ LOW GAIN                         |
| 0A 02 | EFX1 EQ LOW MID FREQ                     |
| 0A 03 | EFX1 EQ LOW MID Q                        |
| 0A 04 | EFX1 EQ LOW MID GAIN                     |
| 0A 05 | EFX1 EQ HIGH MID FREQ                    |
| 0A 06 | EFX1 EQ HIGH MID Q                       |
| 0A 07 | EFX1 EQ HIGH MID GAIN                    |
| 0A 08 | EFX1 EQ HIGH CUT                         |
| 0A 09 | EFX1 EQ HIGH GAIN                        |
| 0A 0A | EFX1 EQ LEVEL                            |
| 0A 0B | EFX2 TYPE                                |
| 0A 0C | EFX2 CS SW                               |
| 0A 0D | EFX2 CS ATTACK                           |
| 0A 0E | EFX2 CS RELEASE                          |
| 0A 0F | EFX2 CS THRESHOLD                        |
| 0B 00 | EFX2 CS RATIO                            |
| 0B 01 | EFX2 CS KNEE                             |
| 0B 02 | EFX2 CS GAIN                             |
| 0B 03 | EFX2 CS BALANCE                          |
| 0B 04 | EFX2 RM SW                               |
| 0B 05 | EFX2 RM FREQUENCY                        |
| 0B 06 | EFX2 RM SENS                             |
| 0B 07 | EFX2 RM POLARITY                         |
| 0B 08 | EFX2 RM EQ LOW                           |
| 0B 09 | EFX2 RM EQ HIGH                          |
| 0B 0A | EFX2 RM BALANCE                          |
| 0B 0B | EFX2 RM LEVEL                            |
| 0B 0C | EFX2 BC SW                               |
| 0B 0D | EFX2 BC FILTER                           |
| 0B 0E | EFX2 BC SAMPLE RATE                      |
| 0B 0F | EFX2 UNIDENTIFIED                        |
| 0C 00 | EFX2 BC EQ LOW                           |
| 0C 01 | EFX2 BC EQ HIGH                          |
| 0C 02 | EFX2 BC LEVEL                            |
| 0C 03 | EFX2 TR SW                               |
| 0C 04 | EFX2 TR TYPE                             |
| 0C 05 | EFX2 TR PHASE                            |
| 0C 06 | EFX2 TR RATE                             |
| 0C 07 | EFX2 TR BPM SYNC                         |
| 0C 08 | EFX2 TR SHAPE                            |
| 0C 09 | EFX2 TR DEPTH                            |
| 0C 0A | EFX2 TR PAN SELECT                       |
| 0C 0B | EFX2 TR LEVEL                            |
| 0C 0C | EFX2 CH SW                               |
| 0C 0D | EFX2 CH MODE                             |
| 0C 0E | EFX2 CH RATE                             |
| 0C 0F | EFX2 CH BPM SYNC                         |
| 0D 00 | EFX2 CH DEPTH                            |
| 0D 01 | EFX2 CH PRE DELAY                        |
| 0D 02 | EFX2 CH HPF                              |
| 0D 03 | EFX2 CH LPF                              |
| 0D 04 | EFX2 CH LEVEL                            |
| 0D 05 | EFX2 FL SW                               |
| 0D 06 | EFX2 FL RATE                             |
| 0D 07 | EFX2 FL BPM SYNC                         |
| 0D 08 | EFX2 FL DEPTH                            |
| 0D 09 | EFX2 FL MANUAL                           |
| 0D 0A | EFX2 FL RESONANCE                        |
| 0D 0B | EFX2 FL SEPARATION                       |
| 0D 0C | EFX2 FL HPF                              |
| 0D 0D | EFX2 FL EFFECT LEVEL                     |
| 0D 0E | EFX2 FL DIRECT LEVEL                     |
| 0D 0F | EFX2 PH SW                               |
| 0D 00 | EFX2 PH TYPE                             |
| 0D 01 | EFX2 PH RATE                             |
| 0D 02 | EFX2 PH BPM SYNC                         |
| 0D 03 | EFX2 PH DEPTH                            |
| 0E 04 | EFX2 PH MANUAL                           |
| 0E 05 | EFX2 PH RESONANCE                        |
| 0E 06 | EFX2 PH STEP RATE                        |
| 0E 07 | EFX2 PH EFFECT LEVEL                     |
| 0E 08 | EFX2 PH DIRECT LEVEL                     |
| 0E 09 | EFX2 DD SW                               |
| 0E 0A | EFX2 DD TYPE                             |
| 0E 0B | EFX2 DD TIME                             |
| 0E 0C | EFX2 DD TAP TIME                         |
| 0E 0D | EFX2 DD BPM SYNC                         |
| 0E 0E | EFX2 DD FEEDBACK                         |
| 0E 0F | EFX2 DD LPF                              |
| 0F 00 | EFX2 DD EFFECT LEVEL                     |
| 0F 01 | EFX2 DD DIRECT LEVEL                     |
| 0F 02 | EFX2 RV SW                               |
| 0F 03 | EFX2 RV TYPE                             |
| 0F 04 | EFX2 RV TIME                             |
| 0F 05 | EFX2 RV PRE DELAY                        |
| 0F 06 | EFX2 RV HPF                              |
| 0F 07 | EFX2 RV LPF                              |
| 0F 08 | EFX2 RV DENSITY                          |
| 0F 09 | EFX2 RV EFFECT LEVEL                     |
| 0F 0A | EFX2 RV DIRECT LEVEL                     |
| 0F 0B | EFX2 RV SPRING SENS                      |
| 0F 0C | EFX2 UNIDENTIFIED                        |
| 0F 0D | EFX2 UNIDENTIFIED                        |
