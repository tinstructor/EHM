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

## Using the Hardware

### Ordering PCB's

### Soldering

### Energy Harvester

### Current Sense Amplifiers

### Voltage Buffers

### Power Delivery

## License
Released under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)

![CC BY-SA 3.0](https://i.imgur.com/wnw2ful.png)
