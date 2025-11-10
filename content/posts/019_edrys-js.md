---
title: "Edrys.js: The Engine Behind the Edrys Modules"
date: 2025-11-10T14:45:00+01:00
description: "Discover the JavaScript library that powers all Edrys-Lite modules, making real-time collaboration and state management effortless."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/edrys-js/cover.png'
---

Behind every Edrys-Lite module we've explored - from the [Editor](/blog/posts/009_module-editor/) to the [Survey Module](/blog/posts/017_module-survey/) - lies a powerful JavaScript library that makes it all work seamlessly: **Edrys.js**. This library handles the complex parts of real-time collaboration so module developers can focus on creating great learning experiences.

## What is Edrys.js?

Edrys.js is the client library that connects modules to the Edrys-Lite classroom environment. It provides a simple API for:

- **Real-time messaging** - Send and receive data between users instantly
- **State synchronization** - Share reactive data that updates across all clients
- **Media streaming** - Broadcast video and audio to the classroom
- **Local storage** - Persist data across sessions
- **Role awareness** - Adapt module behavior based on user roles (teacher, student, station)

Think of it as the foundation that transforms independent web components into collaborative classroom tools.

## Why Edrys.js Matters

Building real-time collaborative applications from scratch is complex. You need to handle WebSocket connections, state synchronization, conflict resolution, and more. Edrys.js abstracts all this complexity:

```javascript
// Instead of managing WebSocket connections manually...
// Just send a message
Edrys.sendMessage("execute", codeContent);

// Instead of implementing state synchronization...
// Just use reactive state
const state = Edrys.getState("data", "Map");
state.set("key", "value");
```

Module developers get collaboration features for free, letting them focus on pedagogy rather than plumbing.

## Real-Time Messaging Made Simple

Edrys.js makes module-to-module communication trivial. The [Editor Module](/blog/posts/009_module-editor/) sends code to the [Terminal Module](/blog/posts/010_module-pyxtermjs/) with a single function call:

```javascript
// Send code to any listening module
Edrys.sendMessage("execute", userCode);

// Receive messages from other modules
Edrys.onMessage(({ from, subject, body }) => {
  if (subject === "execute") {
    runCode(body);
  }
});
```

This pub-sub pattern lets modules work together without knowing about each other's internals - loose coupling at its finest.

## Reactive State for Collaboration

The library uses [Yjs](https://docs.yjs.dev/) for conflict-free state synchronization. Changes made by one user automatically propagate to everyone:

```javascript
// Get a shared map that syncs across all users
const sharedData = Edrys.getState("canvas", "Map");

// Changes update for everyone in real-time
sharedData.set("drawing", canvasData);

// React to changes from other users
Edrys.onUpdate(() => {
  renderCanvas(sharedData.get("drawing"));
});
```

This powers collaborative features like synchronized editor content and shared whiteboards.

## Role-Based Behavior

Modules adapt to different user roles automatically:

```javascript
// Access role-specific configuration
if (Edrys.role === "teacher") {
  showAdminControls();
  loadTeacherConfig(Edrys.module.teacherConfig);
} else if (Edrys.role === "student") {
  loadStudentConfig(Edrys.module.studentConfig);
}
```

This single library supports different experiences for teachers, students, and stations without duplicating code.

## Media Streaming Support

Edrys.js handles the complexity of WebRTC and WebSocket streaming:

```javascript
// Share a video stream with everyone
const stream = await navigator.mediaDevices.getUserMedia({
  video: true,
  audio: true
});

Edrys.sendStream(stream, {
  method: "webrtc" // or "websocket"
});

// Receive streams from others
Edrys.onStream((stream, settings) => {
  videoElement.srcObject = stream;
});
```

The [Streaming Module](/blog/posts/011_module-streaming/) uses this to share live video effortlessly.

## Creating Your Own Modules

With Edrys.js, building custom modules is straightforward:

1. **Create an HTML file** with your module interface
2. **Add metadata** to describe your module
3. **Use Edrys.js API** for collaboration features
4. **Host it anywhere** - GitHub Pages, your server, wherever

The library handles all the classroom integration automatically. Module developers just need to know a bit of JavaScript and HTML.

## Extensible and Open

Edrys.js is open source, meaning:

- **Inspect the code** - Understand how it works
- **Contribute improvements** - Help make it better
- **Build confidently** - No vendor lock-in or hidden behavior
- **Learn from examples** - All existing modules use this same library

Every module we've discussed in this blog series is built with Edrys.js, demonstrating its versatility and power.

## The Foundation of Innovation

Edrys.js doesn't just power existing modules - it enables future innovation. Educators and developers can create:

- Custom assessment tools
- Specialized simulators
- Novel collaboration features
- Domain-specific learning environments

The library provides the foundation; imagination provides the direction.

## Getting Started with Module Development

Want to create your own Edrys-Lite module? The Edrys.js library makes it accessible. Start with a simple HTML file, include the library, and begin building. The [full API documentation](https://liascript.github.io/course/?https://raw.githubusercontent.com/edrys-labs/documentation/refs/heads/main/README.md#19) guides you through everything from basic messaging to advanced state management.

Edrys.js proves that powerful collaboration tools don't require complex frameworks or extensive infrastructure. Sometimes, the right abstraction is all you need to transform complexity into simplicity.

Explore module examples: [edrys-labs on GitHub](https://github.com/edrys-labs)

Ready to build your own collaborative learning tools? Edrys.js provides the foundation - you bring the creativity!