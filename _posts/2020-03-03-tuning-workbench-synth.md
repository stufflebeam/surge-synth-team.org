---
layout: post
order: 5
title: "Tuning Workbench Synth"
summary: Tuning Workbench Synth is a synthesizer for learning and experimenting with microtonal scales.
featured-img: tuning-workbench-synth 
categories: [Synth, Microtuning]
---

Tuning Workbench Synth is a synthesizer which lets you experiment with virtual tunings in realtime, allowing you to edit 
mappings and tunings and hear a synthesizer change as you adjust individual notes. It also serves as an example of using
our [tuning library](/tuning-library) to add tuning to a virtual instruments.

The synth is entirely free and open source software, released under the GPL3. You can find the entire set of source
[at our github](https://github.com/surge-synthesizer/tuning-workbench-synth).

# Get TWS

The Tuning Workbench Synth is currently in a late alpha / early beta release. We release each commit to our repo
as a nightly.

You can download the [current nightly from our github](https://github.com/surge-synthesizer/tuning-workbench-synth/releases/tag/Nightly).

We distribute a standalone for Linux, a VST3 and Standalone for Windows, and a VST3, AU and Standalone for macOS. 
If you are a VST2 licensee and would like to build a VST2, you may do so using the instructions on our github.

# Using TWS

When you launch the tuning workbench synth, you will see the UI below. The main UI is divided into two sections,
the generator section (at the top) and tuning section (at the bottom).

![The TWS Main Screen](/assets/img/tws-manual/TWS-MainUI.png)

## The Generator Section

The generator section controls the sound source. Reading from left to right, it contains the following

- Oscillators
   - The VCO provides a set of analog-style oscillators in sine, square, saw, and triangle waves
     with a level for each of the waveforms and up to 10 unison voices with a spread. The spread
     is expressed in percentages of a single note, and is tuning aware.
   - The Sub-oscillator adds a square wave dropped 1-3 octaves (frequency halvings)
   - The Pluck oscillator provides a simple karplus-strong style attack generator
   - Each can be turned on or off using the power button in the upper right corner of the group boundary
- Modulators
  - The filter envelope is an ADSR envelope which modulates the filter cutoff frequency to depth mod
  - The amplitude envelope is an ADSR envelope applied to the VCO and Sub oscillators but not the Pluck oscillator 
  - The LFO is a per-voice low frequency oscillator with a rate, delay before onset, and attack ramp up time.
      - The vertical sliders assign the LFO modulation to the pitch of the playing note, the level of each oscillator,
        and the cutoff of the filter, respectively
      - The 'wheel' power button determines whether to use the MIDI mod wheel as an amplitude modulator for the
        LFO. If it is on, the LFO is scaled by the mod wheel; if it is off the LFO is unscaled, equivalent to the
        mod wheel being permanently opeion
  - The pitch bend control determines how many notes up and down the pitch bend moves. The pitch bend is expressed
    in notes and is tuning aware.
- The output section
  - The filter is a filter-per-voice which can be a simple low-pass, high-pass or band-pass filter
  - The delay is a global effect with standard delay controls
  - The master stage sets a global output level and a saturation level. We send the entire synth through
    a soft clipper at the output stage, so saturation drives us into the soft clip for a warming effect
    at lower levels and a distortion effect at higher levels.
- The top buttons
  - Presets opens a menu which lets you choose a few factory presets we put together, and save your presets as a separate file if you wish
  - Help opens this page
  - About gives you a screen with version numbers and links to source and so on.

## The tuning section 

The tuning section shows the current result of the scale and keyboard mapping, and allows you to edit those mappings.

The table shows the standard midi keyboard with frequencies and log frequencies. The SCL and KBM files allow you to see
and edit an SCL or KBM file. When you edit a file, the apply button will become active; press it to apply the tuning change.

You can import an SCL or KBM file by dragging and dropping a file onto any part of the UI or by using the "Load" button in the tabs.

## The Advanced Editor

Documentation forthcoming. But you can drag the knobs and graph to retune. Try it!

# Add a feature, Report a Bug

The tuning workbench synth is GPL3 open source software. We welcome contributors who want to build it, expand it, modify it,
and otherwise help us make it cool. Probably the best thing if you want to do this is join our slack or drop an issue on our github.

And if you find a bug, please do let us know!

