# bangbang, 1996.

For piano and computer-controlled synthesizer.

When two streams of chords come crashing together and collide, all that energy packed into a small space needs to go somewhere. It spins out, leading to new configurations and densities. The Synthesizer part (which only plays 'piano' sounds) utilizes a program written in MAX. It complements and extends the piano part; the two taken together form a sort of Hyper-piano.

bangbang was composed for pianist Stephen Clarke, who performed the premiere in June 1995 at Toronto's Music Gallery. That performance was later broadcast on CBC Stereo's _Two New Hours_.

Duration = 14 minutes

## Technical Overview

The synthesizer is connected to a Macintosh computer running bangbang software, which consists of a series of MAX patches and a main interface patch. The Macintosh routes the MAX generated MIDI data back to the synthesizer for playback. The synth's left pedal is used to choose the individual patches, which are indicated in the score drawn in ovals. The synth's right pedal is used for control within two of the patches. The patches are:

PBENDER: applies a pitch-bend with random speed.  
REPEATER: repeats chords between 3 and 21 times, according to a stochastic weighting scheme. This is follwed by a single chord consisting of a one-step random walk for each voice.  
CHORDER: adds three notes to a single line, creating four-note chords. After the right pedal is pressed, the chords are arpeggiated.  
FUGA: creates 4 delayed, transposed notes for every note played in (1 for each speaker).  
CONVERGENCE: creates two streams of constantly cycling, converging lines. A certain percentage of the notes are deflected to the rear speakers and repeated. This percentage starts at 5% and ends at 55%.

### Requirements:

Acoustic piano  
76-note (or larger) keyboard controller  
Multitimbral synth with acoustic piano emulation, at least 2 separate stereo outs  
4 channels of amplification (stereo front, stereo rear)  
Appropriate signal processing (i.e., reverb)

### Channel Map:

1 front left/right (repeater)  
2 front left/right (chorder)  
3 front left/right (fuga: leader)  
4 front left (fuga: follower 4)  
5 front right (fuga: follower 3)  
6 rear left (fuga: follower 1)  
7 rear right (fuga: follower 2)  
8 front left/right (convergence: cascade)  
9 rear left/right (convergence: accents)  
10 not used  
11 not used  
12 not used  
13 not used  
14 not used  
15 rear left pitchbend set to +- 3 semitones (pbender)  
16 rear right pitchbend set to +- 6 semitones (pbender)

Controller Information:

transmit channel: 2  
local control: off  
Left Pedal: controller 2  
Right Pedal: controller 4