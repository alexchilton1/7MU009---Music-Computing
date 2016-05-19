# 7MU009---Music-Computing
Repurposed broken lighting desk used to control a virtual step sequencer and synthesiser through the use of Arduinos. Built in Pure Data.

## Background
------
This project focuses on the participatory Do it Yourself (DiY) culture, which illustrates a certain ethos in its approach to technology and materials. Based less on commercially released technologies that are classified as finalised products and concentrated on raw materials of garbage and recycling, incomplete, broken or discarded technology. This type of practise places emphasis on building unique, custom-built technology from the components and materials, which have been re-functioned from their original objective to create new and often unexpected functions. According to Snake-Beings (2016) the ability to make something happen, is more expansive and incorporates the capacities of materials to become active participants in the production of cultural artifacts.

The re-functioning of materials and existing technology from its original purpose to a new context of usage creates what Spencer (2006) calls the Lo-Fi ethos of DiY culture.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Do-it-yourself approach…is all about…using whatever resources are available to your…[and] not trying to seek out &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;new technology. (Spencer, 2006, p. 187)

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

Two huge advantages that this project has over these sequencers is; firstly, the total cost of the purchased parts comes to twenty pounds and secondly, if has a synthesiser built in to the software so there is no need for an additional piece of hardware. Obviously, being a hybrid, this project is reprogrammable at any time, whereas, the other sequencers will always remain what they are in their current form.

The first thing to note is, obviously, the fact that the hardware part is in fact nothing to do with producing music or audio in general for that matter. But it has been salvaged and repurposed to act as a step sequencer to controller a software synthesiser. This ties in a lot to what was mentioned at the beginning about The Trons. They are a group of robots created to make music from parts, which have nothing to do with music. However when put together they make music. According to Bryant,

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There is no such thing as a simple machine. Rather, every machine is simultaneously a unit or individual entity in its &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;own right and a complex assemblage of other machines. In short machines are composed of other machines. (Bryant, &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2014, p. 75)

If this is the case then machines can always be broken down into other machines. So the fact that the lighting console as a whole was broken is irrelevant, as inside it was full of smaller, working machines if applied in the correct way.

The board uses Arduino microcontrollers to convert and send messages from analogue potentiometers to the digital audio software Pure Data. These messages are then converted and read by the computer and this process is what creates the sound. All the potentiometers are wired and grounded correctly using the appropriate resistors to make sure that none of the Arduino’s get blown up. Insert figure 1.
After the potentiometer messages reach the computer they are read by Pure Data, the software patch behaves the same way analogue sequencers and synthesisers do, but without the need for voltage of course.

The fact that the board is a salvaged piece of repurposed equipment lends itself to the fact that some aspects of it could be drastically improved. For example, some of the potentiometers give false reading or are very jitter. This is possibly caused by their age, but more than likely it is down to the fact that have been used heavily and are worn out. Another thing that could do with changing is the amount of Arduino’s involved overall. Three were used in the end but this tends to make the project a little unstable so it would be wise to reduce the amount of them and instead apply a multiplexer chip to add extra changes. KEEP ALL ANALOGUE! Embed system? 
