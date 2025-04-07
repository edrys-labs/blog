---
title: Deploying RemoteLabs in Seconds with Edrys-Lite
date: "2024-07-05"
draft: false
author: "André Dietrich"
cover: 'static/img/posts/deploying-remotelabs-in-seconds-with-edrys-lite/cover.jpg'
description: ""
featured: true
---

Edrys-Lite is a browser-based approach to remote labs that simplifies the process of creating and sharing educational lab environments. This innovative tool leverages two key technologies: WebRTC for direct peer-to-peer connections between browsers, and CRDT (Conflict-free Replicated Data Types) for real-time data synchronization. Additionally, Edrys-Lite replicates the modular approach and reusability of components from Edrys, its server-based predecessor, ensuring a seamless and efficient lab deployment experience.

{{< youtube 6ZjGHorc2ds >}}

## Key Features of Edrys-Lite

Project-site: https://edrys-labs.github.io

### WebRTC: Seamless Peer-to-Peer Connections

WebRTC (Web Real-Time Communication) enables direct communication between browsers without the need for a central server. This technology facilitates audio, video, and data sharing, making it ideal for real-time collaborative environments such as remote labs. By using WebRTC, Edrys-Lite ensures low-latency and high-quality connections, enhancing the user experience for both educators and students.

### CRDT: Efficient Real-Time Synchronization

CRDT (Conflict-free Replicated Data Types) is a powerful technology that allows multiple users to edit the same document simultaneously without conflicts. In Edrys-Lite, CRDT ensures that all participants see the same data in real-time, whether they are working on textual or graphical editors, camera streams, terminals, markdown content, whiteboards, or simulations. This real-time synchronization is crucial for collaborative learning environments, where multiple users need to interact with shared resources seamlessly.

### Modular and Reusable Components

A lab in Edrys-Lite is a collection of modules combined to solve specific tasks. Currently, the platform supports a variety of modules, including:

- Textual and graphical editors
- Camera streams
- Terminals
- Markdown (for embedding educational content and descriptions)
- Whiteboard drawing
- Simulations

A comprehensive list of usable modules can be found here. These module configurations can be stored in simple JSON or YAML files, which can be modified manually or hosted on GitHub for easy access and sharing.

### Simplified Deployment Process

Edrys-Lite has streamlined the deployment process to make it as simple as possible. To deploy a lab, you only need a link to the lab-configuration file. This link can be used with the following URL format:

```
https://edrys-labs.github.io/?/deploy/$URL_OF_YOUR_REMOTE_LAB
```

For example, combining the deploy URL with a lab-configuration URL looks like this:

https://edrys-labs.github.io/?/deploy/https://raw.githubusercontent.com/edrys-labs/lab-web-serial/main/laboratory/micropython.yaml

By clicking on this link, your browser will fetch the lab-configuration, generate a new lab URL, and open an Edrys-Lite classroom.

### One-Click Deployment Button

To further simplify the process, we have added a one-click deploy button in our GitHub labs. This button looks like this:

[<img src="https://img.shields.io/badge/%F0%9F%9A%80%20-%20Deploy%20Lab%20-%20light?style=plastic" height="25" />](https://edrys-labs.github.io/?/deploy/https://raw.githubusercontent.com/edrys-labs/lab-web-serial/main/laboratory/micropython.yaml)

The button is simply an image linked to the deploy URL, making it easy to deploy a lab with a single click. Here is the markdown code for adding the deploy button to your GitHub repository:

``` markdown
[<img src="https://img.shields.io/badge/%F0%9F%9A%80%20-%20Deploy%20Lab%20-%20light?style=plastic" height="25" />](https://edrys-labs.github.io/?/deploy/https://raw.githubusercontent.com/edrys-labs/lab-web-serial/main/laboratory/micropython.yaml)
```

By clicking on this button, users can instantly deploy and access the specified lab configuration.

### Conclusion

Edrys-Lite makes deploying remote labs quick and easy, leveraging advanced technologies like WebRTC and CRDT to provide a robust and collaborative learning environment. Whether you're an educator looking to share interactive lessons or a student eager to explore new topics, Edrys-Lite offers a seamless and efficient solution for remote education.

Happy lab sharing!