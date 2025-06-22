---
title: Fireworks Generator  
published: 2025-06-22  
updated: 2025-06-22  
description: "Stunning canvas-based fireworks with gravity, colors and explosion types — built in pure JavaScript"  
image: "./assets/img/fireworks_generator.png"  
tags: [JS, Canvas, Visual, Fireworks, 300lines]  
category: Projects  
draft: false  
lang: "en"  
---

# 🎆 Fireworks Generator

**Fireworks Generator** is a beautiful, dynamic visual effect built with **pure JavaScript** and the **HTML5 Canvas API**. It simulates realistic fireworks explosions, with gravity, trails, colors, and different explosion types — all in under 300 lines of code.

Perfect for:
- Holiday projects and celebrations
- Interactive websites and intros
- Learning canvas animations and physics basics

---

## Features

- No libraries — just HTML, CSS, and JavaScript
- Realistic gravity and friction-based physics
- Multiple explosion types: Ring, Sphere, Star, Fountain
- Bright color palettes: Warm, Cool, Pastel, Mono, Rainbow
- Adjustable particle count, auto-launch, and refresh rate
- Fully responsive to any screen size
- Control panel to tweak everything in real time

---

## How It Works

The animation is built from two classes:

- **Firework** — moves from bottom to target position, then explodes
- **Particle** — small fragments with velocity, color, fading and physics

When the firework reaches the target:
1. It generates multiple `Particle` objects based on the selected explosion type.
2. Each particle has its own velocity, friction, gravity, light, and lifetime.
3. A trail is rendered to simulate movement glow.

---

## Code Snapshot

Example of `Particle` physics logic:

```js
this.speed *= this.friction;
this.x += Math.cos(this.angle) * this.speed;
this.y += Math.sin(this.angle) * this.speed + this.gravity;
this.alpha -= this.decay;
```

The project uses `requestAnimationFrame()` for smooth animation and frame-by-frame FPS calculation.

---

## Live Controls

You can interactively control:

- Auto-launch toggle
- Launch rate (ms)
- Particle count
- Explosion shape
- Color palette

A slick UI panel appears in the top right corner. You can collapse it to keep the screen clean.

---

## How to Run Locally

```bash
git clone https://github.com/01cheese/Fireworks-Canvas
cd Fireworks-Canvas
start index.html
```

Or just open `index.html` in your browser.

---

## GitHub

[→ View on GitHub](https://github.com/01cheese/Fireworks-Generator)

---

## YouTube

<iframe width="100%" height="468" src="https://www.youtube.com/embed/YOUR_VIDEO_ID" title="Fireworks Generator" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

## Summary

Fireworks Generator is:
- Visually stunning
- Intuitive and responsive
- A fun way to explore canvas physics and animation

Created with care by [01cheese](https://github.com/01cheese)

