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
  - [Using the Hardware](#using-the-hardware)
    - [Ordering PCB's](#ordering-pcbs)
    - [Soldering](#soldering)
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

## Using the Hardware

### Ordering PCB's

Now, when it comes to ordering PCB's there are a stupid amount of manufacturers out there and they're all claiming some perceived advantage over their competitors. Let me tell you, for the most part it's all marketing b\*llsh\*t. Which manufacturer you choose typically depends on price, manufacturing capabilities and how fast they can deliver. For hobbyists like you and me, the latter is typically of less importance while we tend to focuss more on low pricing.

These days, when I order relatively small dual-layer PCB's for prototyping purposes I'll typically order from [JLCPCB](https://jlcpcb.com/). For the price their manufacturing capabilities and quality are outstanding. In fact, you'll have a hard time finding better prices regardless off  manufacturing capabilities. I mean, €7.05 for 10 PCB's and a stencil is somwhat unreal.

>**Note:** choosing a lead-free finish will add €5.27 to the total price. However, since most hobbyist solder with leaded solder anyway you must ask yourself whether shelling out extra money for a small batch of prototypes is worth it.

![jlcpcb](https://i.imgur.com/n989hVG.png)

### Soldering

### Energy Harvester

### Current Sense Amplifiers

### Voltage Buffers

### Power Delivery

## License
This project and all original material included with it are released under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)

![CC BY-SA 3.0](https://i.imgur.com/wnw2ful.png)
