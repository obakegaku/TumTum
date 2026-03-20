# TumTum - work in progress
Code generated with Claude.ai, testing, debugging and documentation is carried out be me.

TumTum is a four track drum machine/ Sequncer that tries to approximate my favourite aspects of drum programming while maintaining a simple but playful UI. 
It uses concepts learned from my own drum programming to break, where required, the monotony of the standard 16 step sequencer.
Sub-step programming, variable step length, step probabilty, volume automisation as well as full or partial sequence and track randomisation is avaible for experimenting with. Simply open the TumTum.html file in your browser to start playing.

__The Tracks__
There are four instrument tracks on TumTum, each one has four voice profiles. 
Each instrument track has one specific effect as well as adjustable decay.

Track 3 is a minimal synthesizer voice. 
For each step enabled, it will generate a random note within a scale defined in the quantizer section. 
Notes are capped within a two octave range, but can be transposed up or down with dedicated transpose buttons. There is also a low probabilty that a quarter tone offset is applied to the current step for a microtonal, yet musical amount of detune. This can sound particularly nice with long decays and reverb in the second voice profile.

__The Sequencer__

Pressing the Play button will begin the sequencer. Steps progress at the rate determined by tripple Cross Glyph slider, from 60 - 220bpm.
Each track allows for independent step counts from 1 - 16 steps.
Steps are toggled by clicking; Shift + Click enables multiplicated substeps:
Tuplets, triplets and quadruplets.
 
 __Signal Flow__ (for the time being) 
 
Tracks have the follwoing signal path:
Track > volume automisation > track level slider > downsampler > 3-band EQ > Compressor > Master out
Track 3's reverb section is applied post downsampler, pre 3-band EQ.

__Per track Controls:__ 

- Track Mute 
- Step Length (Talon Glyph Slider)
- Step Probabilty (Exclamation Glyph Slider)
- Step Swing amount (Swing Glyph Slider)
- Track Volume (Track Glyph slider)
- Volume Automisation (Lightning Glyph Switch)
- Groove Lock (Padlock Glyph Switch)
- Voice Profile (Triangle, Square, Pentagon, Octagon Glyph Switches)
- Track Specific FX amount
- Track Specific Decay amount
- MIDI channel output dropdown

__Global FX Controls__

TumTum has global controls for: 
- A downsampler with sample rate, Depth and bit parameters (Anvil Glyph slider)
- 3-band EQ (Filter shelf Glyphs sliders, Q slider) 
- Compressor with Threshhold, Ratio, Attack and Decay (Levels Glyph slider)
- Master Output (Volume Glyph Slider)
- MIDI Output Device dropdown

__Randomisation, Auto-randomisation and Randomisation Locking__

There is a dedicated Randomise Button (Circular Arrow Glph) when a completely new pattern needs to be generated.
By Default, hitting the randomise Button will change the following:
- Enabled steps (Including sub-steps on T1,T2 & T4)
- Track Length
- Track Probability
- Track Voice profile
- Track Specific FX amount
- Track Specific Decay amount.

Tracks and the above parameters can also be "Locked" so they they are omitted from any Randomisation taking place. 
Per track, the left-most Lock Button ommits pattern, probability and Voice profile data from being randomised.
Per Track, the right-most Lock Button ommits Track FX and decay amount from being randomised.

For generative aplications there is also a Auto-Randomise button (Clock Glyph) and bar length slider. When enabled, Randomisation will occur ever x amount of bars (1-6) determined by the length of the slider. 1 Bar = 16 steps. Experimenting with the Pattern and FX Locks in combination with Auto-Randomisation can lead to some inspiring grooves.

__MIDI__

In addition to the Web Audio track voices, TumTum can also send it's MIDI output via WEB MIDI.
Typically this would involve using something like Tobias Erichsen's LoopMIDI on Windows, or enabling the built in IAC Driver on MAC to create a "virtual" MIDI device to be picked in other programmes. For example routing TumTum's MIDI to VCV Rack, Ableton Live, Bitwig etc.
The MIDI Output dropdown should reflect the method of routing your MIDI.
- Track 1 sends note on messages per step on C2, to it's specified MIDI channel
- Track 2 sends note on messages per step on C#2, to it's specified MIDI channel
- Track 3 sends note on messages per step on D2, to it's specified MIDI channel
- Track 4 sends note on messages per step on D#2, to it's specified MIDI channel




 
