---
title: "The Terminal Module: Bringing Command-Line Power to Your Browser"
date: 2025-11-10T14:01:42+01:00
description: "Execute code, run commands, and interact with a full terminal environment - all from your browser with the PyxTerm.js Module."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/module-pyxtermjs/cover.png'
---

Remember when we talked about the [Editor Module](/blog/posts/009_module-editor/)? Now it's time to meet its perfect companion: the **PyxTerm.js Terminal Module**. Together, they create a complete development environment right in your browser, no installation needed.

## What is the PyxTerm.js Module?

The PyxTerm.js Module brings a fully functional terminal to your Edrys-Lite labs. Students can execute code, run commands, compile programs, and see real-time output - all within their browser. It's like having a command-line interface accessible to everyone in your class, regardless of their operating system or local setup.

Built on the powerful [pyxterm.js](https://github.com/cs01/pyxtermjs) project, this module transforms remote learning by eliminating the "it works on my machine" problem that plagues programming education.

## Why Terminal Access Matters

Teaching programming often means teaching students to use the command line. But getting everyone's local environment configured correctly can eat up valuable class time. With the PyxTerm.js Module, you provide:

- **Uniform environments** - Everyone works in the same setup
- **Instant access** - No installation or configuration required
- **Safe experimentation** - Students can try commands without affecting their own systems
- **Cross-platform compatibility** - Works the same on Windows, Mac, and Linux

## Security Built In

Educational environments need to balance accessibility with security. The PyxTerm.js Module offers multiple security layers:

- **Docker containers** - Isolate terminal sessions in secure environments
- **Firejail sandboxing** - Restrict what commands can access
- **Permission controls** - Teachers decide who can type in the terminal versus just viewing output

By default, students see terminal output but can't directly type commands. As an instructor, you can grant access when appropriate, making it perfect for demonstrations, guided exercises, or supervised coding sessions.

## Perfect Pairing with the Editor Module

Here's where it gets exciting: combine the Editor Module with the PyxTerm.js Module, and you have a complete IDE in the browser. Students write code in the editor, click execute, and immediately see results in the terminal. No switching between applications, no file transfers, no friction.

This seamless integration makes it ideal for:

- **Programming courses** - From Python basics to advanced C++ development
- **Hardware labs** - Connect to Arduino and other devices
- **System administration training** - Practice Linux commands safely
- **Algorithm visualization** - See code execution in real-time

## Getting Started

Adding the Terminal Module to your Edrys-Lite lab is straightforward. Simply include this URL in your lab configuration:

```
https://edrys-labs.github.io/module-pyxtermjs/index.html
```

You'll also need to run the terminal server. The simplest approach uses Docker:

```bash
docker run -it -p 5000:5000 edryslabs/module-pyxtermjs:latest
```

That's it! The terminal server handles all the heavy lifting, while your students just open their browsers and start coding.

## Flexible Deployment Options

The module supports various deployment scenarios:

- **Basic terminal access** - For simple command-line exercises
- **Development environments** - Pre-configured with compilers, interpreters, and tools
- **Hardware integration** - Connect to Arduino and other physical devices
- **Custom configurations** - Tailor the environment to your specific course needs

Pre-built Docker images are available for common scenarios, from basic terminal access to full development environments with GCC, Java, Python, Node.js, and more.

## Try It in Your Classroom

Want to see it in action? Check out the example lab configuration that demonstrates the PyxTerm.js Module working with other Edrys modules:

[Example Lab Configuration](https://raw.githubusercontent.com/edrys-labs/module-pyxtermjs/master/laboratory.yaml)

The PyxTerm.js Module is open source and ready to transform your remote programming labs.

Explore the module on GitHub: [edrys-labs/module-pyxtermjs](https://github.com/edrys-labs/module-pyxtermjs)

Ready to give your students command-line superpowers? Add the terminal module to your next lab and watch them code without boundaries!