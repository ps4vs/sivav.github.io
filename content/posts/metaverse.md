---
title: "glTF and VRM"
date: 2023-08-21
# weight: 1
# aliases: ["/first"]
tags: ["metaverse", "VRM", "glTF"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "An Intro to glTF and VRMs"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

# glTF2.0
### Introduction
**glTF** stands for `Graphics Language Transmission Format`, which is a file format for 3D scenes and models. It is often refered to as "JEPG of 3D" due to its goal of providing an efficient, interoperable format for the transmission and loading of 3D content.

### Overview
* **Open Standard**: glTF is an open standard developed by Khronos Group, the same organization behind other open standards like Vulkan, and OpenGL.
* **Compact and Streamable**: One of the main goals of glTF is to provide a format that's both compact in size and easily streamable, which is essential for web-based applications and real-time rendering.
* **Physically-Based Rendering**: glTF 2.0 introduced support for PBR materials allowing for more realistic shading and rendering of objets. PBR materials enable 3D objects look consistent under different lighting conditions.
* **JSON Structure**: The main structure of a glTF file is in JSON format, making it both human-readable and easy to parse. This structure described the 3D scene, including nodes, meshes, cameras, animations, and more.
* **Animations**: glTF supports skeletal animations, morph targets, and other animation types, allowing for dynamic and animated 3D content.
* **Extensions**: glTF has a robust extension system, allowing for additional features and capabilities to be integrated without altering the core specifications. For example, there are extensions for mesh compression, physics and more.
* **Wide Adoptation**: Many 3D software tools, game engines, and platforms like Meta, Microsoft support the format.

### Summary
glTF 2.0 is modern 3D file format designed for efficient transmission, loading and rendering of 3D concept, especially in web, real-time environment.

#### Physically-Based Rendering
It is a technique that makes digital objects look realistic by mimicking how real-world materials reflect light. It's like teaching computer to paint with materials that behave like they do in real life.

# Virtual Reality Model

### Introduction
It is a file format for 3D humanoid avatars which are widely used in metaverse. The VRM file format is based on glTF 2.0 format, which is popular open standard for 3D assets on web.

### Features and Characteristics
* **Humanoid Avatars**: VRM is specifically designed for humanoid avatars, making it suitable for virtual reality, augmented reality, and other applications where human-like avatars are used.
* **Blend Shapes**: VRM supports blend shapes (or morph targets), which allow for facial expressions and emotions to be potrayed on avatar.
* **Bone Structure**: VRM has a predefined bone structure, making it easier to create animations and control avatar movements.
* **Materials and Shaders**: VRM files include information on materials and shaders to render the avatar with appropriate texture and lighting.
* **Metadata**: VRM files can contain metadata like author information, version, and other avatar-related details.
* **Compatibility**: Due to its basis on glTF 2.0 format, VRM files can be used across various platforms and applications with ease.
* **Open Standard** VRM is an open standard, and there's a growing community supporting and developing tools and applications around it.

