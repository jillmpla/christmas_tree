# 🎄 Animated SVG Christmas Tree

Spreading Christmas cheer all throughout the year!  
A lightweight, **pure HTML + CSS** project that draws a Christmas tree in **SVG** and animates the lights with **CSS keyframes**—no JavaScript required.

---

## About
Prototype showcasing an **animated SVG** Christmas tree with **CSS keyframe** twinkle lights and a **responsive** layout. Built to demonstrate clean SVG structure, accessible markup, and performant, dependency-free animation.

> _Tags:_ **SVG, CSS, Animation, Responsive**

---

## Table of Contents
- [About](#about)
- [What This Is](#what-this-is)
- [What I Built / Highlights](#what-i-built--highlights)
- [Files](#files)
- [How It Works](#how-it-works)
- [Customize](#customize)
- [Accessibility](#accessibility)
- [Run Locally](#run-locally)
- [Preview](#preview)
- [Links](#links)
- [License](#license)

---

## ✨ What This Is
- **SVG Graphics:** A vector-drawn evergreen (trunk, branches, star) plus grouped ornaments.
- **CSS Animations:** Blinking lights using `@keyframes` with staggered delays for a festive twinkle.
- **Responsive Layout:** The SVG scales cleanly on mobile and desktop (`max-width` on `#tree`).
- **No Dependencies:** Just open the HTML file and enjoy.

---

## 🛠 What I Built / Highlights
- Designed a **custom SVG tree** with groups for trunk, layered boughs, and ornaments.
- Added **animated ornaments** (red, blue light, blue dark, gold light, gold dark) using classes:
  - `.red`, `.blue-lt`, `.blue-dk`, `.gold-lt`, `.gold-dk` control color + animation.
  - `.g1`, `.g2`, `.g3` stagger animation with delays for a natural twinkle.
- Ensured **responsiveness** with a simple, centered layout:
  ```css
  #tree {
    max-width: 300px;
    display: block;
    margin: 0 auto;
  }
  ```
- Kept things **semantic & simple**: a single HTML file (`index.html`) with a separate stylesheet (`style.css`).

---

## 📂 Files
```
.
├─ index.html      # SVG markup and structure
├─ style.css       # Colors, keyframes, animation timing, responsiveness
└─ (optional) /assets/preview.png
```

---

## 🔎 How It Works
**Structure:** Ornaments are `<circle>` elements inside `<g id="lights">` with color and timing classes.
```html
<svg id="tree" xmlns="http://www.w3.org/2000/svg" viewBox="-1694.2 483.2 199.3 285.2" role="img">
  <g id="tree"> ... </g>
  <g id="lights">
    <circle class="red g1" cx="-1635.6" cy="681.7" r="9" />
    <circle class="blue-lt g2" cx="-1621.3" cy="641" r="7" />
    <circle class="gold-dk g3" cx="-1561.3" cy="681.7" r="7" />
  </g>
</svg>
```

**Animation:** Each color class toggles between two fills via `@keyframes`. Timing groups (`g1/g2/g3`) add delays.
```css
.red { fill: #aa1231; animation: 0.6s red-flash ease-in-out infinite; }
@keyframes red-flash {
  40% { fill: #ea385c; }
  80% { fill: #aa1231; }
}

.g1 { animation-delay: 0s; }
.g2 { animation-delay: 0.4s; }
.g3 { animation-delay: 0.8s; }
```

---

## 🎨 Customize
- **Colors:** Edit fills inside `.red`, `.blue-lt`, `.blue-dk`, `.gold-lt`, `.gold-dk` and their keyframes.
- **Speed:** Change `animation: 0.6s ...` to `1s` (slower) or `0.4s` (faster).
- **Size:** Adjust `#tree { max-width: ... }` to fit your layout.
- **Add Lights:** Duplicate a `<circle>` and assign a color + timing class, e.g. `class="gold-lt g2"`.

---

## ♿ Accessibility
Add a title/description and expose as an image role:
```html
<svg id="tree" role="img" aria-labelledby="treeTitle treeDesc" ...>
  <title id="treeTitle">Animated Christmas tree</title>
  <desc id="treeDesc">A stylized evergreen with twinkling red, blue, and gold lights.</desc>
  ...
</svg>
```
Respect reduced motion preferences:
```css
@media (prefers-reduced-motion: reduce) {
  .red, .blue-lt, .blue-dk, .gold-lt, .gold-dk { animation: none; }
}
```

---

## ▶️ Run Locally
1. Clone or download this repository.
2. Open `index.html` in your browser.
3. (Optional) Serve with GitHub Pages to publish a **Live Demo**.

---

## 📸 Preview
Add a screenshot for the README:
```markdown
![Animated SVG Christmas Tree](assets/preview.png)
```

---

## 🔗 Links
- **Repository:** _add your GitHub URL here_
- **Live Demo:** _add your GitHub Pages (or other) URL here_

---

## 🧾 License
MIT — see `LICENSE` for details.
