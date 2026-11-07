# Vivek Pundkar — Personal Portfolio

> A modern, interactive, and high-performance developer portfolio built with fluid responsive typography, Verlet physics, 3D holographic card effects, and interactive project showcases.



## ✨ Signature Features

- **Braided Pull Cord (Verlet Physics)**: Interactive canvas-based hanging cord with turned walnut knob and brass crimp ferrule. Drag, swing with realistic inertia, or pull to toggle between **Warm Ivory Light Mode** and **Charcoal Dark Mode**.
- **3D Desk Flip Calendar**: Animated continuous desk calendar with punch holes and spiral binder rings cycling through skills and disciplines.
- **Interactive Liquid Reveal Portrait**: Grayscale portrait base with liquid color reveal trail tracking the cursor.
- **3D Holographic Ability Card**: Tilt in 3D perspective with realistic gold foil sheen, specular glare, dual-layer parallax portrait window, and flip to reveal technical stats, badges, and profiles.
- **"My work, one door per skill"**: 5 realistic 3D textured doors that swing open into comprehensive project showcase rooms featuring real projects (RentSafe AI, GramPulse, AgroGreenBits).
- **"Let's go back in time" Story Timeline**: 3D perspective clock tunnel canvas that turns and recycles dials with scroll depth, accompanied by rolling odometer digits, ambient light morphing, and traveling rail dot.
- **Live IST Clock & Fluid Typography**: Real-time Indian Standard Time clock (`Nanded / Akola, IN`) and dynamically resizing edge-to-edge name watermark.

## 🛠️ Tech Stack

- **Front-end**: HTML5, Modern CSS3 (Custom Properties, Fluid Rem-Grid, View Transitions), Vanilla JavaScript (ES Modules)
- **Physics & Math**: Verlet numerical integration, spring dynamics, Canvas 2D rendering, 3D CSS transforms
- **Smooth Scrolling**: Lenis momentum scroll
- **Typography**: Onest (Latin & Latin-ext)

## 🚀 Running Locally

Clone the repository and run any local HTTP server:

```bash
# Clone the repository
git clone https://github.com/vivek123ortho/My_Portfolio.git
cd My_Portfolio

# Using Python
python -m http.server 3000

# Or using Node.js / npx
npx serve .
```

Open **`http://localhost:3000`** in your browser.

## 👤 Author

**Vivek Pundkar**
- Email: [vivekpundkar45@gmail.com](mailto:vivekpundkar45@gmail.com)
- GitHub: [@vivek123ortho](https://github.com/vivek123ortho)
- LinkedIn: [Vivek Pundkar](https://linkedin.com/in/vivek-pundkar-871896333)
- LeetCode: [vivek_pundkar](https://leetcode.com/u/vivek_pundkar)


## What was changed in this version
- **Portrait:** background removed (AI cutout); the hero, liquid-colour reveal and ability card all use the clean cutout.
- **Pull cord:** now switches between warm ivory (light) and a neutral greyish-black (dark).
- **Doors:** Full-Stack Web, Generative AI and DSA & Core CS rooms rewritten from the resume (edit `DOORS_INFO` in `js/app.js`).
- **LeetCode room:** shows live stats from a free public stats API. If it is unreachable, set real numbers in `LC_FALLBACK` (`js/app.js`), e.g. `{total:120, easy:60, medium:50, hard:10}`.

## Latest fixes
- Doors now open: a leftover loader layer was blocking every click. The door swings open, then the room is revealed from the doorway.
- Rebuilt the "Work" dropdown, the footer layout and the hover info card, which had missing styles.
- Timeline entry 01 is now the Clarify SQL project; it is also the featured card in the Generative AI door. Check the GitHub link `github.com/vivek123ortho/clarify-sql` is your real repo name.
- "IoT Systems Builder" removed from the hero role flip. Favicon is now a neutral "VP" mark (no photo).
