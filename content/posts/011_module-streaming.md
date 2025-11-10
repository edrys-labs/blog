---
title: "The Streaming Module: Delivering Live Video to Remote Labs"
date: 2025-11-10T14:05:12+01:00
description: "Share live video and audio from your lab station directly to all students - no complex streaming setup required."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/module-streaming/cover.png'
---

Remote labs need more than just code editors and terminals. Sometimes, students need to **see** what's happening - whether it's a hardware experiment, a physical demonstration, or lab equipment in action. That's where the **Streaming Module** comes in.

## What is the Streaming Module?

The Streaming Module transforms your webcam into a live broadcast channel for your Edrys-Lite lab. As an instructor or lab station, you can share real-time video and audio with all connected students, letting them observe experiments, demonstrations, and physical processes as they happen.

Think of it as bringing the lab bench directly to your students' screens, no matter where they are in the world.

## Why Live Streaming Matters in Education

Some concepts can't be fully conveyed through text or static images. Live video streaming enables:

- **Hardware demonstrations** - Show Arduino connections, circuit assembly, or robotic movements in real-time
- **Lab experiments** - Let students observe chemical reactions, physical phenomena, or mechanical processes
- **Equipment operation** - Demonstrate how to use specialized lab equipment or tools
- **Live troubleshooting** - Show students what's happening when their remote code controls physical devices
- **Collaborative observation** - Everyone sees the same thing simultaneously, perfect for group discussions

## Built for Remote Labs

Unlike traditional streaming platforms that require complex setups, accounts, or third-party services, the Streaming Module integrates seamlessly into Edrys-Lite. It leverages WebRTC for direct peer-to-peer connections, meaning:

- **Low latency** - Students see what's happening with minimal delay
- **No streaming service needed** - Everything works browser-to-browser
- **Privacy-focused** - Your stream stays within your classroom
- **Easy setup** - Just enable your webcam and start sharing

## Flexible Configuration

The module gives you control over what and how you share:

- **Video only, audio only, or both** - Share what makes sense for your lab
- **Mirror and rotate** - Adjust the video orientation to match your setup
- **Multiple streaming methods** - Choose WebRTC for best performance or WebSocket for specific scenarios

This flexibility means you can use the same module for different types of labs - from overhead camera views of physical experiments to side-by-side views of equipment operation.

## Perfect for Hybrid Learning

The Streaming Module shines in hybrid learning scenarios:

- **Remote students** join in-person labs by watching live streams
- **Documentation** becomes easier when everyone can see the same setup
- **Peer learning** improves as remote students observe what on-site students are doing
- **Safety** allows students to observe dangerous or sensitive experiments from a distance

## Getting Started

Adding video streaming to your Edrys-Lite lab is straightforward. Include this URL in your lab configuration:

```
https://edrys-labs.github.io/module-streaming/index.html
```

By default, the module will share both video and audio from your station's webcam. You can customize the behavior through simple configuration options, adjusting video orientation, enabling audio, or choosing your preferred streaming method.

## Real-World Applications

The Streaming Module is already being used for:

- **Robotics courses** - Students see their code control physical robots in real-time
- **Electronics labs** - Watch LED patterns, sensor readings, and circuit behavior
- **Chemistry demonstrations** - Observe reactions and experiments safely from anywhere
- **Maker spaces** - Share 3D printing, CNC machining, or fabrication processes
- **Physics experiments** - Witness mechanics, optics, or electromagnetic phenomena live

## Bringing Labs to Life

When combined with the [Editor Module](/blog/posts/009_module-editor/) and [Terminal Module](/blog/posts/010_module-pyxtermjs/), the Streaming Module completes the remote lab experience. Students write code, execute it, and immediately see the physical results on the live video stream.

The Streaming Module is open source and ready to transform your remote labs into immersive learning experiences.

Explore the module on GitHub: [edrys-labs/module-streaming](https://github.com/edrys-labs/module-streaming)

Ready to bring visual learning to your remote labs? Add the streaming module and let your students see science in action! 