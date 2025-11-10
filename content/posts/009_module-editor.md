---
title: "The Editor Module: Your Gateway to Interactive Coding in Edrys-Lite"
date: 2025-11-10T13:38:26+01:00
description: "Discover how the Editor Module brings real-time collaborative coding to your remote labs."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/module-editor/cover.png'
---

Writing code together in real-time doesn't have to be complicated. The **Editor Module** for Edrys-Lite brings the power of collaborative coding directly to your browser, making it easy for students and educators to work on code simultaneously without any installation or setup hassles.

## What is the Editor Module?

The Editor Module is a flexible code editor that integrates seamlessly into your Edrys-Lite labs. Think of it as your classroom's shared coding workspace - multiple students can type, edit, and see each other's changes in real-time, just like working together on a shared document.

What makes it special? It's designed to work hand-in-hand with other Edrys modules. Write your code in the editor, and with a single click, send it to a terminal module for execution, a compiler for building, or any other module that can process your code.

## Getting Started

Adding the Editor Module to your lab is as simple as including this URL in your lab configuration:

```
https://edrys-labs.github.io/module-editor/index.html
```

That's it! No downloads, no complex setup - just add the link and start coding.

## Real-Time Collaboration

By default, the Editor Module synchronizes code across all participants in your lab. When one student makes a change, everyone sees it immediately. This feature is perfect for:

- **Live coding demonstrations** - Teachers can show code changes that students see instantly
- **Pair programming exercises** - Students can collaborate on the same codebase
- **Code reviews** - Discuss and improve code together in real-time

Need individual work? Simply disable synchronization in the configuration, and each student gets their own independent editor.

## Versatile and Adaptable

The Editor Module supports multiple programming languages and themes, adapting to your teaching needs. Whether you're teaching C++, Python, JavaScript, or any other language, the module provides appropriate syntax highlighting and editing features.

You can even work with multiple files at once - perfect for more complex programming projects where students need to manage header files, source files, and configuration files simultaneously.

## Part of a Bigger Picture

The Editor Module doesn't work in isolation. It's part of the modular ecosystem that makes Edrys-Lite so powerful. Combine it with terminal modules, simulation environments, or documentation modules to create complete, interactive learning experiences.

In an upcoming post, we'll explore how the Editor Module connects with terminal modules to create a full development environment right in your browser. Stay tuned!

## Try It Yourself

The Editor Module is open source and ready to use. Add it to your next Edrys-Lite lab and experience the simplicity of browser-based collaborative coding.

Check out the module on GitHub: [edrys-labs/module-editor](https://github.com/edrys-labs/module-editor)

Happy coding!