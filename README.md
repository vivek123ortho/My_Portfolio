<div align="center">

# Vivek Pundkar — Portfolio

**Full-Stack Developer & Generative AI Engineer**

An interactive, door-based portfolio with a pull-cord theme switch, a live colour-reveal portrait, and three "rooms" that showcase my web, Generative AI and DSA work.

[Live site](#-live-demo) · [Quick start](#-quick-start) · [Deploy](#-deploy-in-5-minutes) · [Customise](#-customise-it)

</div>

---

## ✨ Highlights

| Feature | What it does |
|---|---|
| **Pull-cord theme** | Pull the rope in the header to flip between a warm ivory light mode and a neutral greyish-black dark mode. |
| **Three doors** | *Full-Stack Web*, *Generative AI* and *DSA & Core CS*. Each door swings open and reveals a full-screen room with its projects. |
| **Colour-reveal portrait** | A cut-out portrait with a grayscale base and a liquid colour reveal that follows the cursor. |
| **Role keycard** | The "I am a …" headline flips through roles like a desk calendar. |
| **Ability card** | A holographic, flippable card summarising my stack. |
| **Story timeline** | A scroll-driven timeline from the newest project back through hackathons and education. |
| **Live LeetCode stats** | The DSA room pulls my solved counts from my public LeetCode profile, with a graceful fallback. |
| **Smooth scrolling** | Inertial scrolling powered by [Lenis](https://github.com/darkroomengineering/lenis). |
| **Responsive** | Doors become a swipeable carousel on phones; layouts adapt from 360 px up to large desktops. |
| **Zero build step** | Plain HTML, CSS and JavaScript. No npm install, no bundler. |

## 🧰 Tech stack

| Layer | Choice |
|---|---|
| Markup & styles | HTML5, modern CSS (custom properties, `clip-path`, 3D transforms, `backdrop-filter`) |
| Logic | Vanilla JavaScript (ES modules) |
| Scrolling | Lenis 1.3 (bundled in `vendor/`) |
| Typeface | Onest (self-hosted WOFF2 in `fonts/`) |
| Images | WebP, background-removed portrait |
| Hosting | Any static host (Netlify, Vercel, GitHub Pages, Cloudflare Pages) |

## 📁 Project structure

```
.
├── index.html          # Markup, styles and page content
├── js/
│   └── app.js          # All behaviour + project data (DOORS_INFO) + LeetCode widget
├── assets/
│   ├── hero_color.webp # Portrait (colour, transparent background)
│   └── hero_gray.webp  # Portrait (grayscale base layer)
├── card/               # Layers for the holographic ability card
├── fonts/              # Onest (latin + latin-ext)
├── vendor/
│   └── lenis.min.mjs   # Smooth-scroll library
└── README.md
```

## 🚀 Quick start

Modules and fonts need a web server, so don't open `index.html` by double-clicking. Use any static server:

```bash
# Option 1: Node
npx serve .

# Option 2: Python
python3 -m http.server 8000
```

Then open the printed address (for example `http://localhost:3000`).
Using VS Code? The **Live Server** extension works too.

## 🌍 Deploy in 5 minutes

**Netlify (fastest)**
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop).
2. Drag this whole folder onto the page. Done, you get a live URL.

**Vercel**
1. Push this folder to a GitHub repository.
2. Import it at [vercel.com/new](https://vercel.com/new), set the framework preset to **Other**, and click **Deploy**.

**GitHub Pages**
1. Push to a repository, then open **Settings → Pages**.
2. Choose **Deploy from a branch**, select `main` and `/ (root)`, and save.

**Cloudflare Pages**
1. Create a project from your Git repository.
2. Leave the build command empty and set the output directory to `/`.

> After deploying, put your live URL in the [Live demo](#-live-demo) section below.

## 🛠 Customise it

Almost everything you will want to change lives in two places.

| I want to change… | Where |
|---|---|
| Projects inside the three doors | `DOORS_INFO` at the top of `js/app.js` |
| Door names, hover text and room glow colours | `DOORS_INFO` (`headline`, `subtitle`, `bullets`, `theme`) |
| LeetCode username | `LC_USER` in `js/app.js` |
| LeetCode numbers if the live service is down | `LC_FALLBACK` in `js/app.js`, for example `{ total: 120, easy: 60, medium: 50, hard: 10 }` |
| Rotating roles ("I am a …") | the `words` list in `js/app.js` |
| Story timeline entries | the `<li class="ch">` items in `index.html` |
| Contact links, email, phone | the footer (`.sf`) in `index.html` |
| Page title, description, social metadata | the `<head>` of `index.html` |
| Portrait | replace `assets/hero_color.webp` and `assets/hero_gray.webp` (same size, transparent background) |
| Light and dark colours | the `html[data-mode="dark"]` block and `:root` variables in `index.html` |
| Favicon | the `<link rel="icon">` tag in `index.html` |

### Adding a project to a door

Add an object to the `projects` array of a door in `DOORS_INFO`:

```js
{
  badge: 'Python · Oct 2026',
  title: 'My New Project',
  desc: 'One sentence about what it does.',
  bullets: ['What you built.', 'The result or impact.'],
  tags: ['Python', 'FastAPI'],
  link: 'https://github.com/your-username/your-repo',
  feat: true        // optional: makes the card full width
}
```

### LeetCode widget

The DSA room loads solved counts from public LeetCode stats services. These are free third-party services, so they can occasionally be down. If both fail, the card hides the numbers and shows a button to open the profile. Set `LC_FALLBACK` to show fixed numbers instead.

## 🧪 Troubleshooting

| Problem | Fix |
|---|---|
| Blank page or fonts missing | Serve the folder over HTTP (see Quick start) instead of opening the file directly. |
| Doors don't open | Hard-refresh (Ctrl/Cmd + Shift + R) so the latest `index.html` and `app.js` are loaded. |
| LeetCode card shows no numbers | The stats service may be down. Set `LC_FALLBACK`, or visit the profile link on the card. |
| Old version still showing after deploy | Clear the CDN or browser cache, or hard-refresh. |

## 🌐 Browser support

Latest versions of Chrome, Edge, Safari and Firefox. The page uses modern CSS (`clip-path`, `color-mix`, `backdrop-filter`), so very old browsers are not supported.

## 📬 Contact

- **Email:** vivekpundkar45@gmail.com
- **LinkedIn:** [vivek-pundkar-871896333](https://www.linkedin.com/in/vivek-pundkar-871896333)
- **GitHub:** [vivek123ortho](https://github.com/vivek123ortho)
- **LeetCode:** [vivek_pundkar](https://leetcode.com/u/vivek_pundkar)

## 🔗 Live demo

Add your deployed link here: `https://your-site.netlify.app`

## 📄 Credits & licences

- [Lenis](https://github.com/darkroomengineering/lenis): MIT licence
- [Onest](https://fonts.google.com/specimen/Onest): SIL Open Font Licence
- All project descriptions, text and the portrait © Vivek Pundkar. Please don't reuse them as your own.

---

<div align="center">Built with care, one detail at a time.</div>
