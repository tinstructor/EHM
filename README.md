# EHM
An energy harvester with advanced monitoring capabilities.

## Table of Contents
<!-- TOC -->

  - [About The Project](#about-the-project)
  - [Getting Started](#getting-started)
    - [Cloning the EHM Repository](#cloning-the-ehm-repository)
    - [Installing Autodesk EAGLE](#installing-autodesk-eagle)
    - [Navigating the Project Files](#navigating-the-project-files)
    - [Generating Gerber Files](#generating-gerber-files)
  - [Hardware Configuration](#hardware-configuration)
    - [Ordering PCB's](#ordering-pcbs)
    - [Sourcing Components](#sourcing-components)
    - [Soldering](#soldering)
  - [Device Operation](#device-operation)
    - [Energy Harvester](#energy-harvester)
    - [Current Sense Amplifiers](#current-sense-amplifiers)
    - [Voltage Buffers](#voltage-buffers)
    - [Power Delivery](#power-delivery)
  - [License](#license)

<!-- /TOC -->

## About The Project

This project was created with [Autodesk EAGLE](http://eagle.autodesk.com/)

## Getting Started

### Cloning the EHM Repository

In order to download the source files in a zip archive, click [here](https://github.com/tinstructor/EHM/archive/master.zip). Alternatively you may also clone this repository using git bash terminal commands. Substitute "John Doe" by your own username and use your own email address.

```bash
$ git config --global user.name "John Doe"
$ gif config --global user.email "john.doe@example.com"
```

Next up, enter the following command to clone the repository into the folder in which you opened the git bash terminal. Choose your location conveniently, for example `C:\Users\<username>\Documents\eagle\repos` might be a good place.

```bash
$ git clone https://github.com/tinstructor/EHM.git
```

From here on I'll assume all directies to be relative to whatever directory you chose to clone the project in. Also, I'll be using Windows style backslash notations because I just happened to be writing this on a Windows machine. If that offends you, you should really grow up.

### Installing Autodesk EAGLE

Once you've cloned the repository and thereby obtained the necessary files, a free version of Autodesk EAGLE may be downloaded from [here](https://www.autodesk.com/products/eagle/free-download). This is not some trial version that prompts you to spend money you really don't have, instead it is a limited version of the software meant for hobbyists. For our intents and purposes the features offered by the hobbyist version are more than adequate.

>**Note:** if you're a student or an educator you may apply for an educational license [here](https://www.autodesk.com/education/free-software/eagle), which grants you access to the full version of the latest EAGLE release, albeit for non-profit use only.

### Navigating the Project Files

When opening EAGLE for the first time, navigate to the `Options > Directories` tab in the top-left corner. A pop-up window will appear. It is here that you must now add the location of the project files in order to open them in EAGLE. Go to the `Projects` field and add the absolute location of the `EHM\Project` folder, seperating it from the default project location with a semicolon `;`.

![directories](https://i.imgur.com/Cv7TZrJ.png)

The project files will now appear in the control panel view. Notice that there are 2 files present, i.e., a schematic and a board file. Double clicking either of these files will cause both of them to open simultaneously in a seperate window. It is imperative that you always have both file windows open at the same time when making changes of any type. Otherwise you may run into horrible inconsistency problems. No worries, if you where to accidently close one of these windows, EAGLE will prompt you with a bright yellow and black banner.

![project folder](https://i.imgur.com/ZMVJjka.png)

Learning to use EAGLE efficiently may seem difficult in the beginning but it's not actually that bad. In fact Autodesk has some nice [tutorials](https://www.autodesk.com/products/eagle/blog/?s=schematic+basics) that'll get you going in no time.

### Generating Gerber Files

In case you've made changes to the board layout, you'll need to generate new Gerber files. These files tell the machines of your PCB manufacturer of choice how to lay out all traces and other stuff exactly how you designed it. In order to do this, open the board layout window and navigate to the `File > CAM Processor` tab.

![cam processor](https://i.imgur.com/vqzKKHu.png)

A pop-up window now appears. The process of generating gerber files is clearly demonstrated in [this video](https://youtu.be/Jf2y1rTRHDg). However, I've spared you some extra steps and created a simple cam job file `gerb274x.cam` (located in `EHM\CAM`) for you to load as follows:

![cam job](https://i.imgur.com/k3a9aoq.png)

After browsing the file explorer and choosing the appropriate CAM file, all you need to do is press the `Process Job` button in the bottom-right corner of the CAM Processor pop-up window. This will generate a new zip archive called `Gerber.zip` in the `EHM\Project` folder. If you didn't make any changes, a handy `Gerber.zip` archive is already located in the repository folder itself (`EHM\Gerber.zip`).

## Hardware Configuration

### Ordering PCB's

Now, when it comes to ordering PCB's there are a stupid amount of manufacturers out there and they're all claiming some perceived advantage over their competitors. Let me tell you, for the most part it's all marketing b\*llsh\*t. Which manufacturer you choose typically depends on price, manufacturing capabilities and how fast they can deliver. For hobbyists like you and me, the latter is typically of less importance while we tend to focuss more on low pricing.

These days, when I order relatively small dual-layer PCB's for prototyping purposes I'll typically order from [JLCPCB](https://jlcpcb.com/). For the price their manufacturing capabilities and quality are outstanding. In fact, you'll have a hard time finding better prices regardless off  manufacturing capabilities. I mean, €7.05 (before shipping) for 10 PCB's and a stencil is somewhat unreal.

>**Note:** choosing a lead-free finish will add €5.27 to the total price. However, since most hobbyist solder with leaded solder anyway, you must ask yourself whether shelling out extra money for a small batch of prototypes is worth it.

![jlcpcb](https://i.imgur.com/n989hVG.png)

A great way to save some cost in the long run while making your job easier is to use a stencil printer like the [CYBRES SP2421](https://www.tindie.com/products/CYBRES/cybres-sp2421-stencil-printer/) or the [NeoDen PM3040](https://printtec.nl/contents/nl/d361.html). The purpose of a stencil printer will become clear in the section on [Soldering](#soldering). What you need to know at this stage is that there are two types of (manual) stencil printers: while the SP2421 requires no stencil frame (where the PM3040 does) it does require a set of precision cut holes in your stencil. If you've got the capabilities to cut these holes and do it precisely, it's a great way to save some money on both the printer itself as well as the additional shipping costs associated with framed stencils.

>**Note:** stencil jigs typically accept stencils with a maximum size. Make sure to set the size of the stencil accordingly when ordering! Setting a custom stencil size comes with no additional cost, at least on [JLCPCB](https://jlcpcb.com/) it doesn't.

![stencil size](https://i.imgur.com/vpXTCht.png)

### Sourcing Components

First of all, let me state that sourcing components for absolute bottom dollar (or euro in my case) may well be considered a black art. My advise would be to get what you can on [LCSC](https://lcsc.com/) and have them ship your order together with your PCB's from [JLCPCB](https://jlcpcb.com/). That way you can avoid additional shipping fees.

Since the component selection on LCSC is somewhat limited you could go to places like [Mouser](https://www.mouser.com/) for the miscellaneous stuff like the BQ25570RGRR energy harvesting IC and the MAX9934TAUA+ current sense amplifier.

Anyway, at the time of writing this, I wasn't sure yet as to which type of energy I'd be harvesting (solar, thermal, ...) so I couldn't really give you a Bill Of Materials (BOM). However, since most critical components are marked in the schematic with their full partname I'm sure you'll have no trouble obtaining the correct components if you really wanted to. My advice would be to always make sure you get the part with the correct footprint.

>**Note:** make sure to order y14870rxxx00b9r type current resistors with a CSM2512 footprint as illustrated in `EHM\Datasheets\y14870rxxx00b9r.pdf`.

Oh yeah and before I forget, sites like [Banggood](https://www.banggood.com/) are amazing for getting pre-assembled cables like [this](https://www.banggood.com/10Pcs-Mini-Micro-JST-2_0-PH-6Pin-Connector-Plug-With-30cm-Wires-Cables-p-1147297.html) one and [this](https://www.banggood.com/100Pcs-Mini-Micro-JST-2_0-PH-2Pin-Connector-Plug-With-120mm-Wires-Cables-p-1147298.html) one. What's more, Banggood typically charges completely nothing for shipping. The only downside is that stuff will take some weeks to arrive at your doorstep. That's what you get for being so cheap.

### Soldering

While we're on the subject of Banggood, they have a pretty awesome selection of soldering supplies. I myself am a big fan of offerings from [Mechanic](https://www.banggood.com/search/mechanic-solder.html) and of their [XG-Z40](https://www.banggood.com/XG-Z40-10cc-Syringe-Solder-Paste-Flux-Paste-Sn63Pb37-25-45um-p-973158.html) solder paste syringe in particular. If you have no morality issues with leaded solder and you want to spend less money and time on soldering, XG-Z40 is the way to go.

>**Note:** when buying solder paste in a syringe (like the XG-Z40) you'll also need some [blunt tip needles](https://www.banggood.com/search/blunt-tip-fill-needle.html). Make sure to choose tips with a sufficiently large diameter. Otherwise you'll have a hard time pushing out solder paste. My advice is to go with 0.9mm diameter (typically pink) ones. You'll also need to plan a trip to your local pharmacy to get some [10ml syringes](https://www.farmaline.be/apotheek/bestellen/wegwerpspuit-10-ml-terumo-zonder-naald-ss-10es/) because you'll need the rubber plunger thingy in order to push the solder out of the syringe.

![XG-Z40](https://i.imgur.com/Ypw5MJX.jpg)

While XG-Z40 is fine for small rework purposes (as shown in [this](https://youtu.be/4Z1B_DbW-C0) video), when using a stencil you'd really need some [solder paste](https://www.banggood.com/MECHANIC-Soldering-Solder-Welding-Paste-Flux-SMD-SMT-Sn63Pb37-Tool-Soldering-Iron-Flux-Repair-Tool-p-1328894.html) in a jar. Numerous tutorials are available on how to start using stencils for solder paste dispension. For example [this](https://www.youtube.com/watch?v=WDIqtGMROjM) video from Sparkfun is a great place to start when you don't have the funds for an expensive stencil printer. If you do however (have such funds), [this](https://youtu.be/ud8odsM8eA4) video shows how its done.

After putting solder paste on your board and carefully sticking the component to it, you have several different options for heating the solder paste so that it may eventually solidify. For example, you could hit it with a [hot air station](https://www.reichelt.com/be/en/digital-hot-air-smd-rework-station-320w-esd-station-zd-939l-p161632.html). Hot air stations are relatively cheap compared to other solutions and besides, they are an irreplaceable shop tool. Another cheap-ish option is a [hot plate](https://www.tindie.com/products/LafrasH/modern-electronics-reflowr-v2/). The problem with it is that it really only works well for one side of your PCB, which would require you to manually solder components to the pads on the opposite side of the PCB with a hot air gun and/or a conventional soldering iron (with some special tips). Nonetheless this may prove useful if you've placed the most difficult to solder components on the same side. A much more powerful and vastly more expensive solution is something like a
[vapour phase reflow oven](https://www.eleshop.nl/vapour-phase-soldeeroven-mini-condens-it.html).

>**Note:** some people even use conventional electrically heated skillets or toaster ovens. While these methods are inexpensive, they tend to heat your PCB unevenly, potentially causing spotburns and/or tombstoning. The same can be said about the IR reflow ovens of yesteryear.

![ZD-939L](https://i.imgur.com/vGHQUZS.png)

## Device Operation

### Energy Harvester

According to the design principles and other useful information laid out in `EHM\Datasheets\bq25570.pdf` and `EHM\Literature\sluuaa7a.pdf`, the BQ25570 IC allows for a number of configurations to be made pertaining to its operation. But before we can start you might be wondering, what exactly is the function of this chip? The following quote should start to make things somewhat clear:

> *The bq25570 device is a highly integrated energy harvesting Nano-Power management solution that ... is specifically designed to efficiently acquire and manage the microwatts (µW) to milliwatts (mW) of power generated from a variety of DC sources like photovoltaic (solar) or thermal electric generators. \[It is\] targeted toward products and systems, such as wireless sensor networks (WSN) which have stringent power and operational demands.*
>
> **Texas Instruments**

In order to do this, the capabilities of the BQ25570 are twofold. First of all, it contains a boost charger whose intended purpose is to boost the low voltage output of harvesters such as small solar cells or a Thermo-Electric Generator (TEG) to a constant voltage level that is sufficiently high to charge a storage element connected to the battery terminal J4. It does this as efficiently as possible by means of a mechanism called Maximum Powerpoint Tracking (MPPT). The purpose of MPPT is to match the input impedance of the boost charger to the output impedance of the energy harvester which in turn ensures a maximum transfer of power.

More specifically, in this case, the integrated MPPT block continuously measures a certain user configurable percentage (i.e., the MPPT percentage) of the energy harvester's open circuit voltage and uses this information to control the switching frequency of the boost converter to match its input impedance to be equal to the harvester's output impedance, thus assuring maximum power transfer. Choosing the MPPT percentage depends heavily on the type of energy harvesting device. If its output impedance is purely resistive, setting the MPPT percentage to 50% ensures maximum power transfer. However, the capacitive nature of a solar cell's output impedance requires an MPPT percentage closer to 80%. For your convenience I've added the possibility to

![mppt conf](https://i.imgur.com/VKKGwCk.png)

![vout conf](https://i.imgur.com/yBrZWuL.png)

`EHM\BQ25570_Design_Help_V1_3.xlsx`

![design help](https://i.imgur.com/TWJK8u1.png)

All resistors are E96 series 1% resistors with an 0603 footprint. The following table provides a summary of the proposed configuration and the passive components required:

![tables](https://i.imgur.com/t1auMWZ.png)

### Current Sense Amplifiers

### Voltage Buffers

### Power Delivery

## License
This project and all original material included with it are released under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)

![CC BY-SA 3.0](https://i.imgur.com/wnw2ful.png)
