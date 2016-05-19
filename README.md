# 7MU009---Music-Computing
Repurposed broken lighting desk used to control a virtual step sequencer and synthesiser through the use of Arduinos. Built in Pure Data.

## Background
------
This project focuses on the participatory Do it Yourself (DiY) culture, which illustrates a certain ethos in its approach to technology and materials. Based less on commercially released technologies that are classified as finalised products and concentrated on raw materials of garbage and recycling, incomplete, broken or discarded technology. This type of practise places emphasis on building unique, custom-built technology from the components and materials, which have been re-functioned from their original objective to create new and often unexpected functions. According to Snake-Beings (2016) the ability to make something happen, is more expansive and incorporates the capacities of materials to become active participants in the production of cultural artifacts.

The re-functioning of materials and existing technology from its original purpose to a new context of usage creates what Spencer (2006) calls the Lo-Fi ethos of DiY culture.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Do-it-yourself approach…is all about…using whatever resources are available to your…[and] not trying to seek out &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;new technology. (Spencer, 2006, p.187)

Greg Locke, creator of The Trons, has a similar approach to the DiY approach. The Trons are a robot garage band made from recycled materials, including flimsy materials of Meccano and aluminium. Through re-purposing discarded technologies, DiY practitioners engage in “tinkering methodologies” (Hertz and Parikka, 2012) which, define the process as an experimental, exploration of engagement between humans redundant technologies.

This information is relevant and appropriate to the project as the physical controller, that communicates user input to the software counterpart, is built from a broken and discarded lighting console. The original circuitry for the console was in a state of disrepair, however, the potentiometers and metal frame were in good working order. The goal of the project was to create an analogue style step sequencer and synthesiser controlled by a physical, tactile surface while generating all the actual audio within a software counterpart.

## Why Use a Sequencer?
------
On a step sequencer, it is common to find one or more rows of potentiometers, usually with eight or sixteen potentiometers per row. On an analogue step sequencer, for each row, there’s a voltage output. The sequencer steps along the row or rows, one potentiometer at a time. At each step, the voltage level set by a corresponding potentiometer is sent to that row’s output. The output can be patched to the CV input of an oscillator. Each time the sequencer selects a new potentiometer; the frequency of the oscillator changes, producing a new musical pitch. When the sequencer reaches the last potentiometer in the row, it returns back to the start and, if left unaltered, the pattern of selected pitches repeats again. An incoming signal tells the sequencer when it is ready to move to the next potentiometer in the row, this is called the clock, trigger or gate. This signal is usually also used to gate multiple envelope generators.

A sequencer provides a note value, how long each note should be, how long the note is and how loud or soft to play it. It offers very precise control of these parameters. A step sequencer offers the ability to create tuneful or at least coherent music in a relatively short amount of time. Compare this with the MIDI keyboard, which takes a great deal more effort and practice to achieve a similar result. The sequencer does not require an extensive skillset to be able to quite start creating music, although, the longer spent practicing on it, the better skilled a person can become at doing more complex tasks. For example, at first, the player may only select a few notes and let them run continuously for a long period of time, whereas after a few sessions of practice they will be able to control a great deal more parameters simultaneously and begin to play it like an instrument.

The step sequencer allows for a higher level of control and precision simultaneously compared to the MIDI keyboard, as a controller, granting access to a different kind of musical experience and interaction. For this reason the step sequencer was chosen as the controller for this project.

## What It Does Compared With Other Sequencers
------
The layout of the step sequencer in this project is based loosely around the Intellijel Metropolis Eurorack Sequencer (https://www.youtube.com/watch?v=uV9-XA5MPwY). It features eight sliding potentiometers for pitch selection, a potentiometer for changing tempo, a key a scale offset and a global clock with the ability to ratchet. Ratcheting, in this scenario, means playing the same note for the number of beats equal to the pulse count for that particular note. For example if there are two pulses set for each of the eight steps, it would play double the amount of notes within the same time constraint. It would play what appeared to be sixteen steps in the time it would take to play eight.

Similar step sequencers currently on the market that influenced this project are the: 
+ [Intellijel Metropolis Eurorack Sequencer](https://intellijel.com/eurorack-modules/metropolis/)
+ [Megacity Tear Drop Step Sequencer](http://analoguesolutions.com/megacity/)
+ [Koma Komplex Sequencer](http://koma-elektronik.com/?product=komplex-sequencer)
+ [Sputnik 5-Step Voltage Source](http://sputnik-modular.com/5-step-voltage-source/)
+ [Doepfer A155](http://www.doepfer.de/a155.htm)

The Metropolis has the ability to step Forward, Backward, Ping-Pong, Random and Brownian. It features the TB-303 style slide (portamento), ratchet and internally scale notes quantising in any key. This project features the same attributes, minus the Random and Brownian step ability.

The Tear Drop allows an incredible 64 steps in the sequence, due to the hardware and building process, this project is limited to eight steps. The Koma Komplex also features division (ratcheting) as well as the ability to control 64 steps in the sequence.

Two huge advantages that this project has over these sequencers is; firstly, the total cost of the purchased parts comes to twenty pounds and secondly, it has a synthesiser built in to the software so there is no need for an additional piece of hardware to recreate this. Obviously, being a hybrid of both physical and virtual components, this project is reprogrammable at any time, whereas, the other sequencers will always react the same in their current form. This project contains a step sequencer, synthesiser and effects unit all in one place. None of the others previously mentioned have this.

## How It Was Built
------
The first thing to note is, obviously, the fact that the hardware part is in fact nothing to do with producing music or audio in general for that matter. But it has been salvaged and repurposed to act as a step sequencer to controller a software synthesiser. This ties in a lot to what was mentioned at the beginning about The Trons. They are a group of robots created to make music from parts, which have nothing to do with music. However when put together they make music. According to Bryant:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There is no such thing as a simple machine. Rather, every machine is simultaneously a unit or individual entity in its &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;own right and a complex assemblage of other machines. In short machines are composed of other machines. (Bryant, &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2014, p.75)

If this is the case then machines can always be broken down into other machines. So the fact that the lighting console as a whole was broken is irrelevant, as inside it was full of smaller, working machines if applied in the correct way.

The board uses Arduino microcontrollers to convert and send messages from analogue potentiometers to the digital audio software Pure Data. Insert figure 1. 

These messages are then converted and read by the computer and this process is what creates the sound. All the potentiometers are wired and grounded correctly using the appropriate resistors to make sure that none of the Arduino’s get blown up. Insert figure 2.

After the potentiometer messages reach the computer they are read by Pure Data, the software patch behaves the same way analogue sequencers and synthesisers do, but without the need for voltage of course. 

Even though this software synthesiser does not use voltage like the classic analogue synthesisers, it still follows a similar workflow in the way it is constructed. It uses a little bit of additive synthesis.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Additive synthesis is a class of sound synthesis techniques based on the summation of elementary waveforms to create &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a more complex waveform. Additive synthesis is one of the oldest and most heavily researched synthesis techniques. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(Roads, 1996, p.134)

It also uses subtractive synthesis to filter out certain frequencies to create different timbres.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Subtractive synthesis implies the use of filters to shape the spectrum of a source sound. As the source passes through a &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;filter, the filter boosts or attenuates selected regions of the frequency spectrum. (Roads, 1996, p.184-5)

The layout of the synthesiser runs similarly to its analogue ancestors, using an oscillator to begin the process, followed by a filter section and finally an amplitude envelope. In the analogue domain, these sections require voltage and are known as voltage controlled oscillator and so on.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;On most synthesiser designs the VCO would more correctly be described as a voltage-controlled audio oscillator, &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;because it is designed to create electrical signals, and so eventually sounds, more or less within the range of human &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;hearing. (Jenkins, 207, p.49)


Through researching Schroeder’s work around all-pass filters combined with Schroeder-Moorer’s design of lowpass-feedback-comb-filters, it became clear there are two main ways of creating digital reverb in this manner. Artificial reverberation attempts to recreate the echoes in natural reverb using different techniques involving varying computational requirements, in this case a perceptual approach.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Reverberation is a natural acoustical effect. When a sound is emitted in a reverberant room, it is reinforced by a large &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;number of closely spaced echoes. These echoes occur because the emitted sound bounces off the reflecting surfaces &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;of the room. (Frenette, 2000, p.2)

The perceptual approach tries to generate artificial reverb that is perceptively indistinguishable from its natural counterpart by reproducing only the most predominant parts.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Long reverberation times are achieved by circulating the sound by means of delay in feedback loops. (Schroeder and &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Logan, 1961, p.211)

In 1961 Schroeder first attempted to make digital reverberation while at Bell Laboratories. The reverb in this project is based on the updated Schroeder reverberator known as Freeverb, which is a public domain C++ programme. It uses the same default signal-processing settings for the left stereo channel. Processing for the right channel is obtained by adding an integer of 23 to each of the delay-line lengths.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It uses four Schroeder allpasses in series and eight parallel Schroeder-Moorer filtered-feedback comb-filters for each &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;audio channel, and is said to be especially well tuned. (Smith III, 2014, p.110).


## Flow Diagram
------
![Lighting Board Sequencer Flow Diagram](https://github.com/alexchilton1/7MU009---Music-Computing/blob/master/Lighting%20Desk%20Sequencer%20Flow%20Diagram.png)

## Functionality and Overall Performance
------

## What Could Be Improved
------
The fact that the board is a salvaged piece of repurposed equipment lends itself to the fact that some aspects of it could be drastically improved. For example, some of the potentiometers give false reading or are very jitter. This is possibly caused by their age, but more than likely it is down to the fact that have been used heavily and are worn out. Another thing that could do with changing is the amount of Arduino’s involved overall. Three were used in the end but this makes the project a little unstable so it would be wise to reduce the amount of them and instead apply a multiplexer chip to be able to add extra potentiometers to a single Arduino board. Because of this lack of input, the controls for the ratchet and delay have to use Open Sound Control via an external device. It would be more aesthetically appealing to keep all the control inside the lighting console controller. Finally, taking all of this into account another addition could be the use of a Raspberry Pi or BeagleBone to embed the software part of the sequencer, allowing for the audio generation section be mounted inside of the controller itself. This would keep everything in one place and make the project even more appealing.

## Bibliography
------
Bryant, L, R. (2014) *Onto-Cartography: An Ontology of Machines and Media*. 1st ed. Edinburgh: Edinburgh University Press Ltd.

Farnell, A. (2010) *Designing Sound*. 1st ed. Massachusetts: The MIT Press.

Frenette, J. (2000) *Reducing Artificial Reverberation Algorithm Requirements Using Time-Variant Feedback Delay Networks*. Masters Research Project, University of Miami.

Hertz, G and Parikka, J. (2015) Zombie Media: Circuit Bending Media Archaeology into an Art Method. *Leonardo* [online]. 45(5), pp.424-430. [Accessed 14 May 2016]. Available at: <http://mediaarchaeologylab.com/wp-content/uploads/2013/06/Zombie-media.pdf>.

Jenkins, M. (2007) *Analog Synthesizers*. 1st ed. Oxford: Focal Press.

Kuniavsky, M. (2010) *Smart Things*. 1st ed. Massachusetts: Morgan Kaufmann

Miranda, E. (2001) *Composing Music with Computers*. 1st ed. Oxford: Focal Press.

Roads, C. (1996) *The Computer Music Tutorial*. 1st ed. Massachusetts: The MIT Press.

Schroeder, M. and Logan, B. (1961) ‘Colorless’ Artificial Reverberation. *Journal of the Audio Engineering Society*, 9(3), pp.209-214.

Smith III, J. (2015) *Freeverb* [online]. [Accessed 26 May 2015]. Available at: <https://ccrma.stanford.edu/~jos/pasp/Freeverb.html>.

Snake-Beings, E. (2016) *The DiY [’Do-it-Yourself’] Ethos: A participatory culture of material engagement* [online]. Ph.D. Thesis, University of Waikato. [Accessed 14 May 2016]. Available at: <http://researchcommons.waikato.ac.nz/bitstream/handle/10289/9973/thesis.pdf?sequence=3>.

Spencer, A. (2006) *The crafter culture handbook: Making it yourself*. 1st ed. London: Marion Boyars

