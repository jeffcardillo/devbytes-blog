---
title: "Hopeworks Code Day (Talk/Lab) - Arduino Circuit and Code Talk"
date: 2018-10-20T00:44:58-05:00
tags: ["Arduino", "ParticleIO", "Proton", "Circuit", "C"]
draft: false
---

This project reads the light level using a photoresistor and will turn on an LED if the light level drops below a certain threshold. This project was created for a presentation to be given at [Hopeworks Code Day](https://hopeworks.org/2018/09/17/hopeworks-2018-camden-code-day-is-coming/).

![Circuit board](https://raw.githubusercontent.com/jeffcardillo/HopeworksCodeDay/master/schematics/schematic_renders/photoresistor_photon_breadboard.png)

### Presentation Slides

The presentation slides can be viewed and downloaded [here](https://github.com/jeffcardillo/HopeworksCodeDay/blob/master/hopeworks_code_day_presentation.pdf).

### Code

The code for this project can be found under the [code](https://github.com/jeffcardillo/HopeworksCodeDay/tree/master/code) folder. This code can be copied and pasted in to the [Build Editor](https://build.particle.io/) in your console on [Particle IO](https://console.particle.io/)'s website. There are two version of the source code. One file has a bit more debug code included and will push sensor values and light status to the cloud for debugging purposes. The other file does not include the debugging code.

### Circuit Diagrams and Schematics

A full Fritzing project file can be found under the [schematics](https://github.com/jeffcardillo/HopeworksCodeDay/tree/master/schematics) directory. There are also renders of the [breadboard](https://github.com/jeffcardillo/HopeworksCodeDay/blob/master/schematics/schematic_renders/photoresistor_photon_breadboard.png), [schematic](https://github.com/jeffcardillo/HopeworksCodeDay/blob/master/schematics/schematic_renders/photoresistor_photon_schematic.png), and [pcb](https://github.com/jeffcardillo/HopeworksCodeDay/blob/master/schematics/schematic_renders/photoresistor_photon_pcb.png) under the /schematics/schematic_renders/ folder.

