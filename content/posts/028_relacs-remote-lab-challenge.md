---
title: "ReLaCS: Our Students Take On the Remote Lab Challenge"
date: 2026-09-07T10:00:00+01:00
description: "Students from our Software Development for Embedded Systems course built prototype experiments for TH Köln's ReLaCS Remote Lab Challenge, from a CAN-bus car model to a camera-tracked tilting maze."
draft: false
author: "Jihad Hyadi"
cover: 'static/img/posts/relacs-remote-lab-challenge/cover.jpg'
---

Students from our **Software Development for Embedded Systems** course recently took part in the [ReLaCS Remote Lab Challenge](https://www.th-koeln.de/anlagen-energie-und-maschinensysteme/relacs_138409.php), a call for participation from TH Köln's Faculty for Systems, Energy and Mechanical Engineering. The challenge invites students to design and build their own remote lab experiments—combining challenge-based learning with hands-on hardware design.

## What Is ReLaCS?

ReLaCS ("Remote Lab Challenge") is a project led at TH Köln, in partnership with the School of Engineering at the University of Edinburgh, and funded by the Stiftung für Innovation in der Hochschullehre. Running from April 2026 to March 2028, the project asks interdisciplinary student teams to design laboratory experiments for remote lab infrastructure while thinking through accessibility, sustainability, and pedagogy from the start. The best prototypes are refined and made available for future teaching, feeding into a shared knowledge hub for remote lab best practices.

For our students, it was a natural extension of what they already do in the embedded systems course: build small hardware experiments, then make them accessible over the web using [Edrys-Lite](https://edrys-labs.github.io/).

<div style="text-align: center; max-width: 70%; margin: 2em auto;">
  <img src="https://raw.githubusercontent.com/edrys-labs/blog/refs/heads/main/content/static/img/posts/relacs-remote-lab-challenge/lab-rack.jpg" alt="Rack of student remote lab prototypes" style="max-height: 500px; max-width: 100%; border: 1px solid #ddd; border-radius: 4px;" />
  <p style="font-style: italic; color: #666; margin-top: 0.5em;">Student prototypes mounted on our mobile lab rack</p>
</div>

## The Prototypes

True to the course's hands-on spirit, students didn't just simulate their ideas—they built physical setups, wired them up, and mounted cameras so the experiments could be observed and controlled remotely.

### A CAN-Bus Controlled Car

One team built a small car model—3D-printed and hand-painted—driven by an **STM32 Nucleo** board communicating over **CAN bus** with a second STM32 microcontroller. The setup demonstrates a genuine automotive-style architecture in miniature: one board issues commands, the other executes them, and a breadboard of supporting circuitry handles the interfacing in between.

<div style="text-align: center; max-width: 70%; margin: 2em auto;">
  <img src="https://raw.githubusercontent.com/edrys-labs/blog/refs/heads/main/content/static/img/posts/relacs-remote-lab-challenge/stm32-can-lab.jpg" alt="STM32 boards connected via CAN bus controlling a model car" style="max-height: 500px; max-width: 100%; border: 1px solid #ddd; border-radius: 4px;" />
  <p style="font-style: italic; color: #666; margin-top: 0.5em;">Two STM32 Nucleo boards linked over CAN bus, driving a 3D-printed model car</p>
</div>

### A Camera-Tracked Tilting Maze

Another team built a labyrinth-style balancing game: a ball rests on a tilting platform, and an Arduino-driven servo tilts the surface to guide it toward a target. A webcam mounted overhead lets a remote student watch the ball's position live—closing the feedback loop entirely through the browser, just like they would sitting in front of the physical device.

<div style="text-align: center; max-width: 70%; margin: 2em auto;">
  <img src="https://raw.githubusercontent.com/edrys-labs/blog/refs/heads/main/content/static/img/posts/relacs-remote-lab-challenge/tilt-ball-lab.jpg" alt="Camera-tracked tilting platform with a ball balancing game" style="max-height: 500px; max-width: 100%; border: 1px solid #ddd; border-radius: 4px;" />
  <p style="font-style: italic; color: #666; margin-top: 0.5em;">A servo-actuated tilting platform, observed by an overhead camera for remote play</p>
</div>

### More Experiments on the Rack

Alongside these two, further student experiments were mounted on the same [mobile lab station](/blog/posts/025_mobile-lab-station) we use for our other remote labs, each with its own camera for observation.

## Why It Matters

The challenge pushed students to think beyond "does it work on my desk?" and toward "can someone else operate this from anywhere?" That shift—designing for a remote user rather than a local one—is exactly the kind of thinking ReLaCS is trying to cultivate, and it mirrors the philosophy behind our own remote lab modules for [hardware control](/blog/posts/027_module-hardware-control), [streaming](/blog/posts/011_module-streaming), and [interactive coding](/blog/posts/009_module-editor).

We're proud of our students for jumping into this challenge, and we're looking forward to seeing which of these prototypes get refined into full teaching labs as ReLaCS continues.

Learn more about the challenge: [ReLaCS at TH Köln](https://www.th-koeln.de/anlagen-energie-und-maschinensysteme/relacs_138409.php)

Learn more about Edrys-Lite: [edrys-labs.github.io](https://edrys-labs.github.io)
