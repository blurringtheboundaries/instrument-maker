# About Instrument Maker

This is an open source framework for digital instrument building with sensors, with improving access in mind. For [Bela](http://bela.io) / Raspberry Pi.  Code currently developed by [Charles Matthews](http://ardisson.net/) through a series of collaborations (details soon, for now this page is written from a personal perspective) - get in touch if you would like to contribute!

Distributed under the terms of the GNU Public license version 3 (for now  / not sure how appropriate / need to read up on this).

This is one of my first public repos and will definitely be messy for a little while.  The current version is not ready for public consumption (see the technical notes below); please feel free to explore the code, and download and try out the abstractions if you are familiar with Pure Data..but I recommend waiting a little while until everything's more coherent.



## How does it work?

Within Pure Data, create objects with the im. prefix to access building blocks: inputs, outputs, tuning systems. Upload to Bela, or Raspberry Pi with an Arduino-type device connected.  With Bela, choosing a setup should be a case of dragging and dropping into a browser; files can exist as "presets", no need to edit or look at the code unless desired.

Video demo (code): https://youtu.be/8AJMJq2P8Ko

Video demo (mobile): https://www.youtube.com/watch?v=jl020N0MZxk

Video demo (play): https://www.youtube.com/watch?v=ywEX0N6TpEA

An accompanying hardware component is in development, which adds crocodile clip access to the Bela platform.

![](documentation/im-chords.png)

## Background

My intention is to help find a different entry point to instrument creation using sensors.  Access to this is not currently good enough.  Not just in a Disability context, but that's where the focus sits with this project. 

I'm reluctant to use the term "accessible music technology" to describe this; while I respect others that do, I don't currently think it's all that helpful a term in abstract (I hope this will form a move toward Disabled artist-led music technology: essentially the same idea, but implies a different power relationship).  But that's certainly a context in which some of this project's output will fit. Access or accessibility tend to rely upon openness, and benefit from opportunities for input at every stage of the design process.

So, ideally, this should provide an opportunity/context for someone to approach the problem of creating an instrument, rather than (necessarily) learning a programming language. Conversely, it shouldn't remove access to the underlying code..whether that's through a nicely packaged GUI, or a closed source back end. That's not necessarily the easiest problem to solve!  We're starting to see a bit more of this approach appearing in commercial software; [Max for Live](https://www.ableton.com/en/live/max-for-live/) is a good example.

A few considerations:

- remove obligation to code, but with opportunities to learn and dismantle 
- offer ways to create objects that feel like instruments, rather than controllers: devices that have a direct, local connection between physical input and output, without mediation from a keyboard and mouse (and added costs on that front)
- retain ability to make complex, difficult-to-master instruments
- options for expression beyond pitch, duration, and loudness by default; music is about more than playing notes and chords (obvious maybe, but AMT doesn't always look beyond this)
- integrate a variety of tuning systems
- expand access through ability to modify and create derivatives.

About me: I don't identify as a coder, much in the same way that I sometimes don't feel entitled to identify as a musician (I don't know wtf it is I do tbh), but I care enough about this kind of stuff to want to make it. Plus I have [pretty intense ADHD](http://ardisson.net/a/?p=363) and find it difficult to let things go.  I know that most of what I make could be used by other people, but it's been lacking some sort of unifying practice and documentation. I'm tired of saying "it'll be open source down the line". I have engaged in [openwashing](http://openwashing.org/) in the past, and almost certainly still do without realising it. 

Instrument Maker pulls together material from around fifteen years of lectures, collaborative projects, and artistic output ([Light Recorders](http://ardisson.net/a/?page_id=440) and [Augmented Gamelan](http://augmentedgamelan.com)).  I'm excited to think that this might form the basis for some much wider collaboration.  Portions of this work were developed with the support of [Drake Music](https://www.drakemusic.org/): e.g. [the Kellycaster](https://rockinpaddy.wordpress.com/) with John Kelly, Gawain Hewitt and others, [DMLab innovation challenges](http://music.britishcouncil.org/news-and-features/2016-10-20/embracing-music-technology-the-dm-lab-challenge), and the [Planted Symphony installation](http://www.drakemusic.org/our-work/artistic-development/projects-commissions/planted-symphony/). 

Some of this code was originally developed for Max/MSP, and can possibly be made available on request; it's a bit much to develop on the two platforms in parallel right now.  This sits alongside a couple of other projects that live in other repositories: the [Light Recorder Deck](https://github.com/matthewscharles/Light-Recorder-Deck) (for DMX light control), and Accessible Music Technology Framework (an Arduino library with similar aims, currently on hold).  

### What's Pure Data, why use it this way?

Pure Data is a free, open source, visually oriented programming language. Otherwise known as dataflow ("the flowchart is the program").  Boxes that serve particular functions are joined together, sending messages back and forth, some of which can be sound that eventually gets sent out to speakers.  For musicians, this can fit neatly with familiar notions of arranging mixers and effects pedals, or throwing objects at a drummer to negotiate tempo.

It's not a million miles away from the ["blocks"](https://en.wikipedia.org/wiki/Block_(programming))-type programming currently popular in education, either. I'm interested in how Pure Data can be used in a similar way, but without the complexity of trying to make everything from scratch: getting caught up in "spiders' webs" or a blank screen on day one, or feeling turned away by assumed knowledge of maths etc. — which are the experiences I often observe when teaching this, and reflect my own first steps. 

The idea that we need to identify as technically-minded to access these resources can tacitly reinforce power structures, including but not limited to those formed around gender, impairment, and Disability. Not to suggest that everyone wants to access creation on this level either..but why mention this here? Well, among the many options for creating bespoke software, even compared to some text-based languages, Pure Data certainly falls in the more "technical" camp.  With less emphasis on graphics than something like Max, it's a bit more like moving code around than guitar pedals.  There are less ready-made options to use as a starting point..but once we can find or create the right ones, the experience, the underlying principles, the learning curves, are mostly the same.  Much like learning a musical instrument.

Pure Data has an active online community with [forums](https://forum.pdpatchrepo.info/) and a [Facebook group](https://www.facebook.com/groups/4729684494/), where it's possible to discuss problems and ideas.

### Where are the problems with this approach?

My own experience of working with similar frameworks (such as the excellent BEAP and Vizzie collections for Max) has been mixed. They tend to be a little idiosyncratic and difficult to mix with more generic approaches in teaching environments, due to a need for standardised ins/outs and ranges..I can certainly see this as a problem here.

One of the advantages of working with Pure Data, or similar languages, is that the graphical interface can automatically be part of the code. Many of the interfaces we are used to now are more abstract versions of this; see, for example, the drag-and-drop plugin chaining and non-timeline-based interactions that were popularised through Ableton Live, which was ~~[originally prototyped in](http://www.roberthenke.com/technology/ableton_live.html)~~ partly inspired by Max.

In this proposed framework, in a way, we leave that idea behind; we might test the ideas on screen, with a mouse or keyboard, but that affords certain sorts of interactions..and the act of trying to create a useable interface in itself often leads us back into those spiders' webs..screen time…in a way, at this point at least I guess this is less about the playful exploration through code that we might associate with this kind of dataflow/visually oriented setup - but I believe it can lead to more play at the instrument end.  Having said that, you may notice some similarities between these objects and the kind of abstractions found in live coding environments like Tidal Cycles..there could be an interesting live-patching spinoff to explore.

### How will people get to access this?

It's taking time to package this up in a way that is immediately accessible. I am working with a few collaborators on example projects, and posting video updates when I can.  

This has been tested in some shape or form through workshops and lectures for the last five years, and this is the most obvious way to try ideas and get direct feedback. 

Once the framework is stable, I will start releasing some packaged examples, video tutorials and "worksheets". At this point it may be possible to make a more open call for collaboration.

I also have plans to release paid some paid apps to support development of the project, which will not require access to the code, but should be recreatable with the resources I put online.

### Are there other projects like this?

Yes! Not all dedicated to creating standalone instruments in this way, but you might like to check out some of these different angles on similar issues:

- http://automatonism.com/
- https://tidalcycles.org/
- https://www.ableton.com/en/blog/beap-powerful-modules-max-live/
- https://github.com/dktr0/estuary
- https://www.drakemusic.org/blog/becky-morris-knight/making-instruments-in-the-classroom/
- https://www.chrisballprojects.co.uk/sensilo-2/
- https://sonic-pi.net/
- http://instrumentslab.org/research/accessible-instruments.html
- https://www.bareconductive.com/shop/touch-board/
- and of course http://blog.bela.io/

(By no means intended to be exchaustive).

# Technical notes

At present, I anticipate that in order to use this framework effectively, you'll need to download an SD card image for a Bela or Raspberry Pi (available soon). This is in part due to reliance on external libraries, which would need better documentation to install from scratch. Furthermore, on the Raspberry Pi, we need instructions to boot directly to the software.

For the time being, the "source code" is available here.  If you want a disk image to test, just let me know.  Version tracking is kind of limited due to the nature of Pd files, but I'm trying to break it down enough that we can observe changes in units/abstractions.

## Interaction with sensors

Pure Data running on Bela is a thing of beauty: sensor inputs are treated as audio information.  Analog inputs are accessed through the `[im.input]` abstraction (with an argument matching the analog input), and connected directly to a virtual instrument.

At present, the most flexible way to recreate this experience with a Raspberry Pi (also a thing of beauty, in its own way, and a bit cheaper) appears to be through an affordable Arduino board running [Firmata](https://www.arduino.cc/en/reference/firmata). In practical terms, this requires dropping in an `[im.firmata]` object, which tells the `[im.input]`objects to look at Arduino inputs rather than the Bela's audio ADC.

### Interaction with actuators?

No reason not to, and my initial attempts included a lot of this! But focussing on audio output keeps it simple, sort of, for now.  

### MIDI output/what if I just want to make a controller?

As above..but there are lots of great things that do this already, and this was the focus of the accompanying AMT Arduino library.

### What about output to my modular or similar CV/gate synth?

[Ok, I'll make an exception](https://twitter.com/matthewscharles/status/1096605603579990016) ;) since this is all running at audio rate, this can integrate quite nicely. People do this with Pure Data (and Bela) already.

## Objects/abstractions in current demo

| Name                         | Vanilla? | Needs (easy fixes in italics)                                |
| ---------------------------- | -------- | ------------------------------------------------------------ |
| im.generatescale             | y        |                                                              |
| im.input                     | y        |                                                              |
| im.key                       | y        |                                                              |
| im.midiin                    | y        |                                                              |
| im.output                    | y        |                                                              |
| im.reverb                    | n        | freeverb~ (yeah, I cheated for now)                          |
| im.sample                    | y        | -                                                            |
| im.scala & scala2 (internal) | n        | *counter*, *gate*, *tosymbol*, *fromsymbol*, zl: *iter*, *group*, *len*, *join*, sect, *reg*, *rev* |
| im.scale                     | n        | zl: *reg*, *len*, *lookup*                                   |
| im.sensor                    | y        |                                                              |
| im.tunedperc                 | n        |                                                              |
| im.tuning                    | n        |                                                              |

## Tuning/Scala

The framework uses the [Scala](http://www.huygens-fokker.org/scala/) format to retrieve tuning systems, which may be useful for storing scales as well.  This could fit into (or replace) JSON as described below.

Please note: if you got as far as reading this section, there's a possibility that I don't care about microtuning as intensely as you do.  I can dig that. Think I'm mishandling this stuff? Let me know :)

Tuning is transferred to a table accessible at audio rate with interpolation if needed (I think this has potential for some subtley freaky modulation sources).

## Reliance on Cyclone library/ current todo list

I would like to make this available to work on [Pd Vanilla](https://stackoverflow.com/questions/14793956/is-there-any-reason-to-use-vanilla-pure-data-instead-of-pd-extended), to simplify the installation procedure and ensure compatibility with [libpd](https://github.com/libpd)-based contexts, e.g. [MobMuPlat](http://danieliglesia.com/mobmuplat/). At present, I use the [Cyclone](https://github.com/porres/pd-cyclone/) library as this makes Pd a lot more accessible to me coming from a Max background.  

I'm looking for ways to recreate the following objects using Vanilla.  Since the addition of new list functionality, some of this is more about breaking out of old habits, so I'll include this as something of a todo list for now.  *Can probably move a couple of the remaining tasks into issues.* I guess it could form part of a useful resource for Max heads in the future. 

- **zl**: I'm pretty sure that all of the below can be handled with the generic list object, but some of these operations desperately need encapsulating
  - I've created a `[for]` object (with argument ++ or --), which takes in a list or integer to create a for loop based on the input/length..this makes patching a bit nicer and a bit more like text-oriented code
  - **zl reg**: more specifically, I use this to retrieve a symbol-based argument within an abstraction. Works fine with `[list store]`
  - **zl group**: (a bit more than) just `[append]` and bang
    - fixed by creating `[list.group]`
  - **zl join**: `[list append]` or `[list prepend]`
  - **zl lookup**: like `[list store]`, with a `get $ 1` message
  - **zl len**: `[list length]`
  - **zl sect**: `[list split]`? — not quite, need to compare..this is the sort of thing that usually gets quite complicated/frustrating in Pd.
  - **zl iter**: recursive `[list split]` with `[until]`? — see serialization example (3) in the help file
    - solved by creating `[list.iter]` - takes argument ++ or -- to iterate up or down through the list (only one entry at a time at present)
  - **zl rev**: probably a combination of `[list split]` and `[list prepend]` as above with iter
    - solved by creating `[list.rev]`
  - **zl rot**: as above
    - solved by creating `[list.rot]`
- **gate** and **switch**: with arguments for multiple inlets/outlets..and that'll mean a bit of scripting. should be ok (I did this loads in Max some time ago, how hard can it be?) but might need to establish a reasonable maximum number.
- **tosymbol**: is it really just a case of `[list prepend symbol] -> [list trim]`? Or is this stuff actually useful after all? Switching between types in Pd has been a thorn in my side..
- **fromsymbol**: this one is potentially tougher..maybe I don't yet understand how symbols and lists are processed differently in Pd yet.
- **counter**: should be easy enough, certainly the way I use it here..in fact I'm starting to prefer the old-skool float and plus. Pd 101 with added arguments. Also created `[for]` which takes care of a fair bit of the non-realtime counting I need.
- **rampsmooth~**: ugh..this one will be tough to live without, I use this for everything. Maybe look at [source code](https://github.com/porres/pd-cyclone/blob/master/cyclone_objects/binaries/audio/rampsmooth.c) and use something like `[fexpr~]`? I've got as far as some if statements with `$x1[-1`], love it so far.
- **svf~**: unfortunately this is an easy way to make filters with audio modulation that will be similarly difficult to let go.
- **scale**: I think this should be `[expr ($f1 * (($f5 - $f4) / ($f3 - $f2))) + $f4]` but it doesn't handle negative numbers. There was an abstraction included within pd-extended that I'd like to check out.
  - created `[im.map]` using the above.

Interested in using some Max-style attributes…some potentially useful info [here](https://forum.pdpatchrepo.info/topic/10892/collect-all-arguments-as-a-list/7).

## JSON file format

I'm keen for this to use the JSON format to promote compatibility with other platforms. I use the PuRestJson external available for Pd, which works OK. Considering writing a parser with Vanilla objects, but really, is that going to end well?  

Update: yes, turns out that the `[text]` object is great for this!! Nested structures now working in read mode (still a bit hacky), haven't attempted to format and write a JSON file yet.  The search function looks like it could be quite powerful.

## Accessibility/misc documentation

-Some instructions involving the help browser could be useful, as could Henri Bisognini's autocomplete plugin

-How do we make this screen reader compatible?

-How could we make a symbol-based version?
