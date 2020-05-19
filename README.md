# FM_synthesizer_using_NIMyRio

I have created an NI MyRio FM synthesizer using Labview. I haven’t used any other external library/MIDI instrument.  Instead, I’m just sticking to this formula: y(t) = a(t) sin(2pi*fc*t + i(t)*sin(2pi*fm*t)) from Dr J Chowning’s research.  The instrument options are: bell, drum, clarinet, basson and brass. You can switch to different instruments from the case structure.

## Overall structure
The MyRio and the key dial communicates with the host computer via shared variable. Here variable to be shared is the frequency to be played. 

## How to get started
It would be hard to download the repository and run it on your PC directly due to the nature of Labview. But you could take all the VI files as the reference to build your synthesizer. <br />

host_wifi.vi : to detect which key is pressed on the key dial. Transform it to frequency value and share it to the host PC. <br />

server.vi : to play back sound according to instrument option, volume, and frequency received.<br />

synthesizer/synth_subvi_rt.vi : to build sound samples from various instruments based on this formula: y(t) = a(t) sin(2pi*fc*t + i(t)*sin(2pi*fm*t)) <br />
