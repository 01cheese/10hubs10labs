---
title: Lightning Generator
published: 2025-06-07
updated: 2025-06-07
description: "Generate realistic animated lightning bolts using Canvas and JavaScript"
image: "./assets/img/lightning_generator.png"
tags: [JS, Canvas, Visual, Lightning, 300lines]
category: Projects
draft: false
lang: "en"
---

# ⚡ Lightning Generator

**Lightning Generator** is a minimalist visual project built with pure JavaScript. It generates realistic animated lightning bolts with branches and glow using HTML5 Canvas — in under 300 lines of code.

Perfect for:
- game intros or websites,
- visual effects,
- learning recursion and Canvas rendering.

---

## Features

- No libraries — just HTML, CSS, and JavaScript
- Generates main bolt and random branches
- Glow and blur effects using Canvas
- Fully responsive to any screen size
- Auto-redraw every 2 seconds

---

## Algorithm: Midpoint Displacement

The core algorithm is recursive midpoint displacement of a line segment.

At each iteration:
- the segment is split in two;
- the midpoint is randomly displaced;
- the process continues until the segment is short enough.

Example function:

```js
function midpointDisplacement(x1, y1, x2, y2, offset, detail = [], midpoints = []) {
  const k = 1 + Math.random() * 3;
  if (offset < 2) {
    detail.push([x1, y1, x2, y2]);
  } else {
    const midX = (x1 + x2) / 2 + (Math.random() - 0.5) * offset * k;
    const midY = (y1 + y2) / 2 + (Math.random() - 0.5) * offset * k;
    midpoints.push([midX, midY]);
    midpointDisplacement(x1, y1, midX, midY, offset / 1.7, detail, midpoints);
    midpointDisplacement(midX, midY, x2, y2, offset / 1.7, detail, midpoints);
  }
  return { segments: detail, midpoints };
}
```

---

## Rendering Structure

The project draws several visual layers using Canvas:

- Main lightning bolt
- Branches emerging from corners
- Thin sub-branches
- Screen flash (semi-transparent white overlay)

---

## How to Run Locally

```bash
git clone https://github.com/01cheese/Lightning-Algorithm
cd Lightning-Algorithm
start index.html
```

---

## 🔗 GitHub

[https://github.com/01cheese/Lightning-Algorithm](https://github.com/01cheese/Lightning-Algorithm)

---

## YouTube

<iframe width="100%" height="468" src="https://www.youtube.com/embed/KT4_vYQYe8Y?si=CuvciLxvi1lzXBHN" title="Lightning Generator" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
---

## References

- [Midpoint Displacement – CG Tutorial](https://lodev.org/cgtutor/randomnoise.html)
- [Canvas Lightning – Codepen](https://codepen.io/joeyhoer/full/poqzxGg)
- [Realistic Lightning – Medium](https://medium.com/@justinlloyd/realistic-lightning-in-html5-canvas-8430ecf5005d)

---

## Summary

Lightning Generator is:

- Simple in structure
- Visually impressive
- Great for learning and experimenting

Made by [01cheese](https://github.com/01cheese)
