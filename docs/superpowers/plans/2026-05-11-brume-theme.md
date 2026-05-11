# Brume Theme Palette — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a publishable theme palette repo with 4 variants, a JSON source of truth, CSS port, and a showcase website deployed to GitHub Pages.

**Architecture:** Static monorepo — JSON palette definition as source of truth, CSS custom property exports, and a single-page website. No build tools required.

**Tech Stack:** HTML, CSS, JSON, GitHub Pages

---

## File Structure

```
brume/
├── palette/
│   └── colors.json
├── ports/
│   └── css/
│       ├── brume-fog.css
│       ├── brume-haze.css
│       ├── brume-mist.css
│       └── brume-void.css
├── website/
│   ├── index.html
│   └── style.css
├── LICENSE
└── README.md
```

---

### Task 1: Initialize Repo and Create Palette JSON

**Files:**
- Create: `palette/colors.json`

- [ ] **Step 1: Initialize git repo**

```bash
cd C:\Users\Admin\Downloads\new-theme
git init
```

- [ ] **Step 2: Create `palette/colors.json`**

```json
{
  "name": "Brume",
  "description": "A frost-tinted color palette — every color shifted through mist.",
  "variants": {
    "fog": {
      "name": "Fog",
      "description": "Morning fog, soft light",
      "colors": {
        "base": "#ebeef6",
        "surface": "#dfe2ed",
        "overlay": "#d0d4e3",
        "mantle": "#bcc2d6",
        "crust": "#a8afc6",
        "text": "#2c3050",
        "subtext1": "#434868",
        "subtext0": "#5c6180",
        "rose": "#c45878",
        "flamingo": "#c06870",
        "red": "#b84858",
        "maroon": "#a03848",
        "orange": "#c07838",
        "yellow": "#b8a040",
        "green": "#3c9868",
        "teal": "#288888",
        "sky": "#3888c0",
        "blue": "#4060c0",
        "violet": "#6858b0",
        "mauve": "#9860b8",
        "pink": "#b86898",
        "silver": "#6a7090"
      }
    },
    "haze": {
      "name": "Haze",
      "description": "Overcast sky, muted midtone",
      "colors": {
        "base": "#2a2d3e",
        "surface": "#343750",
        "overlay": "#3e4260",
        "mantle": "#4a4e6e",
        "crust": "#585c7e",
        "text": "#d0d6e4",
        "subtext1": "#a8b0c4",
        "subtext0": "#8088a4",
        "rose": "#d88898",
        "flamingo": "#d07888",
        "red": "#d06878",
        "maroon": "#b85068",
        "orange": "#d89860",
        "yellow": "#d0c070",
        "green": "#68c088",
        "teal": "##58b8b8",
        "sky": "#68b0d8",
        "blue": "#5878d0",
        "violet": "#9080d0",
        "mauve": "#b888d0",
        "pink": "#d098b8",
        "silver": "#a8b0c4"
      }
    },
    "mist": {
      "name": "Mist",
      "description": "Evening mist, vivid accents",
      "colors": {
        "base": "#12131f",
        "surface": "#1a1c2e",
        "overlay": "#22253a",
        "mantle": "#2c2f48",
        "crust": "#363a56",
        "text": "#d5dce8",
        "subtext1": "#b0b8cc",
        "subtext0": "#8a92ab",
        "rose": "#f0a0b4",
        "flamingo": "#e8909c",
        "red": "#e87d8a",
        "maroon": "#c86078",
        "orange": "#f0b080",
        "yellow": "#e8d590",
        "green": "#90d8b0",
        "teal": "#78d0d0",
        "sky": "#88c8f0",
        "blue": "#7090e8",
        "violet": "#a898e8",
        "mauve": "#d0a0e8",
        "pink": "#e8b8d0",
        "silver": "#c0c8e0"
      }
    },
    "void": {
      "name": "Void",
      "description": "Deep night, glowing accents",
      "colors": {
        "base": "#08090f",
        "surface": "#10111c",
        "overlay": "#181a28",
        "mantle": "#202338",
        "crust": "#2a2d44",
        "text": "#c8d0e0",
        "subtext1": "#a0a8c0",
        "subtext0": "#7880a0",
        "rose": "#f8a8bc",
        "flamingo": "#f098a8",
        "red": "#f08898",
        "maroon": "#d86880",
        "orange": "#f8b888",
        "yellow": "#f0d898",
        "green": "#98e0b8",
        "teal": "#80d8d8",
        "sky": "#90d0f8",
        "blue": "#7898f0",
        "violet": "#b0a0f0",
        "mauve": "#d8a8f0",
        "pink": "#f0c0d8",
        "silver": "#c8d0e4"
      }
    }
  }
}
```

- [ ] **Step 3: Verify JSON is valid**

Run: `node -e "JSON.parse(require('fs').readFileSync('palette/colors.json','utf8')); console.log('Valid JSON')"` from `C:\Users\Admin\Downloads\new-theme`

---

### Task 2: Create CSS Port Files

**Files:**
- Create: `ports/css/brume-fog.css`
- Create: `ports/css/brume-haze.css`
- Create: `ports/css/brume-mist.css`
- Create: `ports/css/brume-void.css`

- [ ] **Step 1: Create `ports/css/brume-fog.css`**

```css
:root {
  --brume-base: #ebeef6;
  --brume-surface: #dfe2ed;
  --brume-overlay: #d0d4e3;
  --brume-mantle: #bcc2d6;
  --brume-crust: #a8afc6;
  --brume-text: #2c3050;
  --brume-subtext1: #434868;
  --brume-subtext0: #5c6180;
  --brume-rose: #c45878;
  --brume-flamingo: #c06870;
  --brume-red: #b84858;
  --brume-maroon: #a03848;
  --brume-orange: #c07838;
  --brume-yellow: #b8a040;
  --brume-green: #3c9868;
  --brume-teal: #288888;
  --brume-sky: #3888c0;
  --brume-blue: #4060c0;
  --brume-violet: #6858b0;
  --brume-mauve: #9860b8;
  --brume-pink: #b86898;
  --brume-silver: #6a7090;
}
```

- [ ] **Step 2: Create `ports/css/brume-haze.css`**

```css
:root {
  --brume-base: #2a2d3e;
  --brume-surface: #343750;
  --brume-overlay: #3e4260;
  --brume-mantle: #4a4e6e;
  --brume-crust: #585c7e;
  --brume-text: #d0d6e4;
  --brume-subtext1: #a8b0c4;
  --brume-subtext0: #8088a4;
  --brume-rose: #d88898;
  --brume-flamingo: #d07888;
  --brume-red: #d06878;
  --brume-maroon: #b85068;
  --brume-orange: #d89860;
  --brume-yellow: #d0c070;
  --brume-green: #68c088;
  --brume-teal: #58b8b8;
  --brume-sky: #68b0d8;
  --brume-blue: #5878d0;
  --brume-violet: #9080d0;
  --brume-mauve: #b888d0;
  --brume-pink: #d098b8;
  --brume-silver: #a8b0c4;
}
```

- [ ] **Step 3: Create `ports/css/brume-mist.css`**

```css
:root {
  --brume-base: #12131f;
  --brume-surface: #1a1c2e;
  --brume-overlay: #22253a;
  --brume-mantle: #2c2f48;
  --brume-crust: #363a56;
  --brume-text: #d5dce8;
  --brume-subtext1: #b0b8cc;
  --brume-subtext0: #8a92ab;
  --brume-rose: #f0a0b4;
  --brume-flamingo: #e8909c;
  --brume-red: #e87d8a;
  --brume-maroon: #c86078;
  --brume-orange: #f0b080;
  --brume-yellow: #e8d590;
  --brume-green: #90d8b0;
  --brume-teal: #78d0d0;
  --brume-sky: #88c8f0;
  --brume-blue: #7090e8;
  --brume-violet: #a898e8;
  --brume-mauve: #d0a0e8;
  --brume-pink: #e8b8d0;
  --brume-silver: #c0c8e0;
}
```

- [ ] **Step 4: Create `ports/css/brume-void.css`**

```css
:root {
  --brume-base: #08090f;
  --brume-surface: #10111c;
  --brume-overlay: #181a28;
  --brume-mantle: #202338;
  --brume-crust: #2a2d44;
  --brume-text: #c8d0e0;
  --brume-subtext1: #a0a8c0;
  --brume-subtext0: #7880a0;
  --brume-rose: #f8a8bc;
  --brume-flamingo: #f098a8;
  --brume-red: #f08898;
  --brume-maroon: #d86880;
  --brume-orange: #f8b888;
  --brume-yellow: #f0d898;
  --brume-green: #98e0b8;
  --brume-teal: #80d8d8;
  --brume-sky: #90d0f8;
  --brume-blue: #7898f0;
  --brume-violet: #b0a0f0;
  --brume-mauve: #d8a8f0;
  --brume-pink: #f0c0d8;
  --brume-silver: #c8d0e4;
}
```

---

### Task 3: Build the Showcase Website

**Files:**
- Create: `website/index.html`
- Create: `website/style.css`

- [ ] **Step 1: Create `website/style.css`**

The stylesheet uses Brume Mist as the default theme for the website itself, with variant switching via data attributes.

```css
*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

:root {
  --brume-base: #12131f;
  --brume-surface: #1a1c2e;
  --brume-overlay: #22253a;
  --brume-mantle: #2c2f48;
  --brume-crust: #363a56;
  --brume-text: #d5dce8;
  --brume-subtext1: #b0b8cc;
  --brume-subtext0: #8a92ab;
  --brume-rose: #f0a0b4;
  --brume-flamingo: #e8909c;
  --brume-red: #e87d8a;
  --brume-maroon: #c86078;
  --brume-orange: #f0b080;
  --brume-yellow: #e8d590;
  --brume-green: #90d8b0;
  --brume-teal: #78d0d0;
  --brume-sky: #88c8f0;
  --brume-blue: #7090e8;
  --brume-violet: #a898e8;
  --brume-mauve: #d0a0e8;
  --brume-pink: #e8b8d0;
  --brume-silver: #c0c8e0;
}

[data-theme="fog"] {
  --brume-base: #ebeef6; --brume-surface: #dfe2ed; --brume-overlay: #d0d4e3;
  --brume-mantle: #bcc2d6; --brume-crust: #a8afc6; --brume-text: #2c3050;
  --brume-subtext1: #434868; --brume-subtext0: #5c6180; --brume-rose: #c45878;
  --brume-flamingo: #c06870; --brume-red: #b84858; --brume-maroon: #a03848;
  --brume-orange: #c07838; --brume-yellow: #b8a040; --brume-green: #3c9868;
  --brume-teal: #288888; --brume-sky: #3888c0; --brume-blue: #4060c0;
  --brume-violet: #6858b0; --brume-mauve: #9860b8; --brume-pink: #b86898;
  --brume-silver: #6a7090;
}

[data-theme="haze"] {
  --brume-base: #2a2d3e; --brume-surface: #343750; --brume-overlay: #3e4260;
  --brume-mantle: #4a4e6e; --brume-crust: #585c7e; --brume-text: #d0d6e4;
  --brume-subtext1: #a8b0c4; --brume-subtext0: #8088a4; --brume-rose: #d88898;
  --brume-flamingo: #d07888; --brume-red: #d06878; --brume-maroon: #b85068;
  --brume-orange: #d89860; --brume-yellow: #d0c070; --brume-green: #68c088;
  --brume-teal: #58b8b8; --brume-sky: #68b0d8; --brume-blue: #5878d0;
  --brume-violet: #9080d0; --brume-mauve: #b888d0; --brume-pink: #d098b8;
  --brume-silver: #a8b0c4;
}

[data-theme="void"] {
  --brume-base: #08090f; --brume-surface: #10111c; --brume-overlay: #181a28;
  --brume-mantle: #202338; --brume-crust: #2a2d44; --brume-text: #c8d0e0;
  --brume-subtext1: #a0a8c0; --brume-subtext0: #7880a0; --brume-rose: #f8a8bc;
  --brume-flamingo: #f098a8; --brume-red: #f08898; --brume-maroon: #d86880;
  --brume-orange: #f8b888; --brume-yellow: #f0d898; --brume-green: #98e0b8;
  --brume-teal: #80d8d8; --brume-sky: #90d0f8; --brume-blue: #7898f0;
  --brume-violet: #b0a0f0; --brume-mauve: #d8a8f0; --brume-pink: #f0c0d8;
  --brume-silver: #c8d0e4;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  background-color: var(--brume-base);
  color: var(--brume-text);
  line-height: 1.6;
  transition: background-color 0.3s, color 0.3s;
}

a { color: var(--brume-blue); text-decoration: none; }
a:hover { text-decoration: underline; }

.container { max-width: 1100px; margin: 0 auto; padding: 0 24px; }

header {
  padding: 48px 0 32px;
  text-align: center;
  border-bottom: 1px solid var(--brume-mantle);
}

header h1 {
  font-size: 3rem;
  font-weight: 800;
  letter-spacing: -1px;
  background: linear-gradient(135deg, var(--brume-sky), var(--brume-mauve));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

header p {
  color: var(--brume-subtext0);
  font-size: 1.15rem;
  margin-top: 8px;
}

.variant-switcher {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin: 32px 0;
}

.variant-btn {
  padding: 8px 24px;
  border-radius: 8px;
  border: 1px solid var(--brume-mantle);
  background: var(--brume-surface);
  color: var(--brume-text);
  cursor: pointer;
  font-size: 0.95rem;
  font-weight: 500;
  transition: all 0.2s;
}

.variant-btn:hover { border-color: var(--brume-blue); }
.variant-btn.active {
  background: var(--brume-blue);
  color: #fff;
  border-color: var(--brume-blue);
}

section { padding: 48px 0; }
section h2 {
  font-size: 1.5rem;
  margin-bottom: 24px;
  color: var(--brume-text);
}

.neutrals-grid, .accent-grid {
  display: grid;
  gap: 12px;
}

.neutrals-grid { grid-template-columns: repeat(5, 1fr); }
.accent-grid { grid-template-columns: repeat(auto-fill, minmax(120px, 1fr)); }

.color-swatch {
  border-radius: 12px;
  overflow: hidden;
  border: 1px solid var(--brume-mantle);
  cursor: pointer;
  transition: transform 0.15s, box-shadow 0.15s;
}

.color-swatch:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.3);
}

.swatch-preview { height: 72px; }
.swatch-info {
  padding: 10px 12px;
  background: var(--brume-surface);
}
.swatch-name {
  font-size: 0.8rem;
  font-weight: 600;
  text-transform: capitalize;
  color: var(--brume-text);
}
.swatch-hex {
  font-size: 0.75rem;
  font-family: 'JetBrains Mono', monospace;
  color: var(--brume-subtext0);
}

.usage-section { margin-top: 16px; }

.code-block {
  background: var(--brume-surface);
  border: 1px solid var(--brume-mantle);
  border-radius: 8px;
  padding: 16px 20px;
  overflow-x: auto;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.85rem;
  color: var(--brume-text);
  position: relative;
}

.copy-btn {
  position: absolute;
  top: 8px;
  right: 8px;
  padding: 4px 12px;
  border-radius: 6px;
  border: 1px solid var(--brume-mantle);
  background: var(--brume-overlay);
  color: var(--brume-subtext0);
  cursor: pointer;
  font-size: 0.75rem;
}

.copy-btn:hover { border-color: var(--brume-blue); color: var(--brume-text); }

footer {
  padding: 32px 0;
  text-align: center;
  border-top: 1px solid var(--brume-mantle);
  color: var(--brume-subtext0);
  font-size: 0.9rem;
}

.toast {
  position: fixed;
  bottom: 24px;
  left: 50%;
  transform: translateX(-50%) translateY(100px);
  background: var(--brume-blue);
  color: #fff;
  padding: 10px 24px;
  border-radius: 8px;
  font-size: 0.9rem;
  opacity: 0;
  transition: all 0.3s;
  pointer-events: none;
}

.toast.show {
  transform: translateX(-50%) translateY(0);
  opacity: 1;
}

@media (max-width: 768px) {
  header h1 { font-size: 2rem; }
  .neutrals-grid { grid-template-columns: repeat(3, 1fr); }
  .accent-grid { grid-template-columns: repeat(auto-fill, minmax(100px, 1fr)); }
}
```

- [ ] **Step 2: Create `website/index.html`**

A single-page site with hero, variant switcher, color swatches, CSS usage example, and footer.

```html
<!DOCTYPE html>
<html lang="en" data-theme="mist">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Brume — Frost-tinted Color Palette</title>
  <link rel="stylesheet" href="style.css">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
</head>
<body>
  <div class="container">
    <header>
      <h1>Brume</h1>
      <p>A frost-tinted color palette — every color shifted through mist.</p>
    </header>

    <nav class="variant-switcher">
      <button class="variant-btn" data-variant="fog">Fog</button>
      <button class="variant-btn" data-variant="haze">Haze</button>
      <button class="variant-btn active" data-variant="mist">Mist</button>
      <button class="variant-btn" data-variant="void">Void</button>
    </nav>

    <section id="neutrals">
      <h2>Neutrals</h2>
      <div class="neutrals-grid" id="neutrals-grid"></div>
    </section>

    <section id="accents">
      <h2>Frost Spectrum</h2>
      <div class="accent-grid" id="accent-grid"></div>
    </section>

    <section id="usage" class="usage-section">
      <h2>Usage</h2>
      <p style="color:var(--brume-subtext0);margin-bottom:16px;">
        Use Brume in your project via CSS custom properties:
      </p>
      <div class="code-block">
        <button class="copy-btn" onclick="copyCode()">Copy</button>
<pre>&lt;link rel="stylesheet" href="https://unpkg.com/brume@latest/ports/css/brume-mist.css"&gt;

.my-element {
  background: var(--brume-surface);
  color: var(--brume-text);
  border: 1px solid var(--brume-mantle);
}</pre>
      </div>
    </section>

    <footer>
      <p>Brume by <a href="https://github.com/vkeerthivikram">vkeerthivikram</a> &middot; MIT License</p>
    </footer>
  </div>

  <div class="toast" id="toast">Copied!</div>

  <script>
    const PALETTE = {
      fog: {
        base: "#ebeef6", surface: "#dfe2ed", overlay: "#d0d4e3",
        mantle: "#bcc2d6", crust: "#a8afc6",
        text: "#2c3050", subtext1: "#434868", subtext0: "#5c6180",
        rose: "#c45878", flamingo: "#c06870", red: "#b84858",
        maroon: "#a03848", orange: "#c07838", yellow: "#b8a040",
        green: "#3c9868", teal: "#288888", sky: "#3888c0",
        blue: "#4060c0", violet: "#6858b0", mauve: "#9860b8",
        pink: "#b86898", silver: "#6a7090"
      },
      haze: {
        base: "#2a2d3e", surface: "#343750", overlay: "#3e4260",
        mantle: "#4a4e6e", crust: "#585c7e",
        text: "#d0d6e4", subtext1: "#a8b0c4", subtext0: "#8088a4",
        rose: "#d88898", flamingo: "#d07888", red: "#d06878",
        maroon: "#b85068", orange: "#d89860", yellow: "#d0c070",
        green: "#68c088", teal: "#58b8b8", sky: "#68b0d8",
        blue: "#5878d0", violet: "#9080d0", mauve: "#b888d0",
        pink: "#d098b8", silver: "#a8b0c4"
      },
      mist: {
        base: "#12131f", surface: "#1a1c2e", overlay: "#22253a",
        mantle: "#2c2f48", crust: "#363a56",
        text: "#d5dce8", subtext1: "#b0b8cc", subtext0: "#8a92ab",
        rose: "#f0a0b4", flamingo: "#e8909c", red: "#e87d8a",
        maroon: "#c86078", orange: "#f0b080", yellow: "#e8d590",
        green: "#90d8b0", teal: "#78d0d0", sky: "#88c8f0",
        blue: "#7090e8", violet: "#a898e8", mauve: "#d0a0e8",
        pink: "#e8b8d0", silver: "#c0c8e0"
      },
      void: {
        base: "#08090f", surface: "#10111c", overlay: "#181a28",
        mantle: "#202338", crust: "#2a2d44",
        text: "#c8d0e0", subtext1: "#a0a8c0", subtext0: "#7880a0",
        rose: "#f8a8bc", flamingo: "#f098a8", red: "#f08898",
        maroon: "#d86880", orange: "#f8b888", yellow: "#f0d898",
        green: "#98e0b8", teal: "#80d8d8", sky: "#90d0f8",
        blue: "#7898f0", violet: "#b0a0f0", mauve: "#d8a8f0",
        pink: "#f0c0d8", silver: "#c8d0e4"
      }
    };

    const NEUTRALS = ["base", "surface", "overlay", "mantle", "crust"];
    const ACCENTS = [
      "rose", "flamingo", "red", "maroon", "orange", "yellow",
      "green", "teal", "sky", "blue", "violet", "mauve", "pink", "silver"
    ];

    let currentVariant = "mist";

    function renderSwatches(variant) {
      const colors = PALETTE[variant];
      const neutralsGrid = document.getElementById("neutrals-grid");
      const accentGrid = document.getElementById("accent-grid");

      neutralsGrid.innerHTML = NEUTRALS.map(name =>
        `<div class="color-swatch" onclick="copyHex('${colors[name]}')">
          <div class="swatch-preview" style="background:${colors[name]}"></div>
          <div class="swatch-info">
            <div class="swatch-name">${name}</div>
            <div class="swatch-hex">${colors[name]}</div>
          </div>
        </div>`
      ).join("");

      accentGrid.innerHTML = ACCENTS.map(name =>
        `<div class="color-swatch" onclick="copyHex('${colors[name]}')">
          <div class="swatch-preview" style="background:${colors[name]}"></div>
          <div class="swatch-info">
            <div class="swatch-name">${name}</div>
            <div class="swatch-hex">${colors[name]}</div>
          </div>
        </div>`
      ).join("");
    }

    function copyHex(hex) {
      navigator.clipboard.writeText(hex);
      showToast(`Copied ${hex}`);
    }

    function copyCode() {
      const code = document.querySelector(".code-block pre").textContent;
      navigator.clipboard.writeText(code);
      showToast("Copied to clipboard");
    }

    function showToast(msg) {
      const toast = document.getElementById("toast");
      toast.textContent = msg;
      toast.classList.add("show");
      setTimeout(() => toast.classList.remove("show"), 2000);
    }

    document.querySelectorAll(".variant-btn").forEach(btn => {
      btn.addEventListener("click", () => {
        document.querySelectorAll(".variant-btn").forEach(b => b.classList.remove("active"));
        btn.classList.add("active");
        const variant = btn.dataset.variant;
        currentVariant = variant;
        document.documentElement.setAttribute("data-theme", variant);
        renderSwatches(variant);
      });
    });

    renderSwatches(currentVariant);
  </script>
</body>
</html>
```

---

### Task 4: Create README and LICENSE

**Files:**
- Create: `README.md`
- Create: `LICENSE`

- [ ] **Step 1: Create `README.md`**

```markdown
# Brume

A frost-tinted color palette — every color shifted through mist.

Brume (French: mist) is a color palette where the entire spectrum has been shifted toward blue-grey, as if viewed through frosted glass. Reds become rose-blush. Greens become glacial sage. Yellows become cold wheat.

## Variants

| Variant | Description |
|---------|-------------|
| **Fog** | Morning fog, soft light (light) |
| **Haze** | Overcast sky, muted midtone (medium) |
| **Mist** | Evening mist, vivid accents (dark) |
| **Void** | Deep night, glowing accents (deep dark) |

## Colors

Each variant includes 22 colors:

**Neutrals:** Base, Surface, Overlay, Mantle, Crust

**Text:** Text, Subtext1, Subtext0

**Frost Spectrum:** Rose, Flamingo, Red, Maroon, Orange, Yellow, Green, Teal, Sky, Blue, Violet, Mauve, Pink, Silver

## Usage

### CSS

```html
<link rel="stylesheet" href="https://unpkg.com/brume@latest/ports/css/brume-mist.css">
```

```css
.my-element {
  background: var(--brume-surface);
  color: var(--brume-text);
  border: 1px solid var(--brume-mantle);
}
```

### JSON

The source of truth is [`palette/colors.json`](palette/colors.json). Use it to port Brume to any platform.

## Ports

Want to port Brume to your favorite editor/terminal/app? Fork and PR!

- [CSS](ports/css/) — CSS custom properties

## License

MIT
```

- [ ] **Step 2: Create `LICENSE` (MIT)**

```
MIT License

Copyright (c) 2026 vkeerthivikram

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

### Task 5: Final Verification

- [ ] **Step 1: Verify all files exist**

Run: `ls -R` from `C:\Users\Admin\Downloads\new-theme`

Expected: All files listed in file structure above.

- [ ] **Step 2: Open website locally and verify**

Run: `start website/index.html` (Windows) or `open website/index.html` (macOS)

Verify:
- All 4 variant buttons switch colors
- All swatches render correctly
- Click swatch copies hex to clipboard
- Responsive layout works

- [ ] **Step 3: Validate JSON**

Run: `node -e "JSON.parse(require('fs').readFileSync('palette/colors.json','utf8')); console.log('OK')"`

Expected: `OK`

- [ ] **Step 4: Validate CSS files**

Check each CSS file has exactly 22 `--brume-` variable declarations.
