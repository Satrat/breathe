# Breathe
Breathe is an algorithmic composition that captures the breathing of a musician as they improvise to manipulate the frequency spectrum of their instrument and control granular synthesis

## Dependencies
* [Max MSP](https://cycling74.com/)
* [High order Ambisonics library](https://cycling74.com/tools/hoalibrary-v2), can also be downloaded from the Max package manager
* Jean-Francois Charles' [Spectral Freeze](https://www.jeanfrancoischarles.com/2008/10/) example patch. (included in this repo as `solo-freeze.pfft`)
* Yafr2 reverb

## Repo Layout
### 03hGranularSynthesis.maxpat
Granular synthesizer, controls grain rate and duration based on amplitude of incoming audio signal. Controls rerecording of grain sorce through MIDI input
### ambi.maxpat
Uses Hoa library to spatialize sounds sources, gradually moves sources randomly throughout the sound field
### harm_reverb.maxpat
Subpatch that applies yafr2 reverb to a signal with an interface for setting reverb parameters
### single_harm~.maxpatch
Subpatch for ramping a signal from one max amplitude to another over an amount of time specified by an inlet
### solo-freeze.pfft
Subpatch that takes an fft snapshot of a signal and loops it to create a drone signal
### main.maxpat
Main patch of the piece. Routes incoming guitar, breath and MIDI foot pedal signals

## How to Use
This patch takes in three inputs: An audio signal from a guitar(or any instrument of your choosing), An audio signal of a microphone attached below the musicians nose to capture their breath, and a MIDI foot pedal. Set these inputs in `main.maxpat` then lock the patch to start.

The guitarist can use the foot pedal to trigger an FFT of their signal and start a drone(up to 6 drones can play at once). The foot pedal is also used by the guitarist to start and stop recordings of the grain source. Grain sources can be up to 10 seconds long
