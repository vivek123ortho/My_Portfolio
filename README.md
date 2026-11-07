<div align="center">

# Vivek Pundkar — Interactive Portfolio

**Full-Stack Developer · Generative AI Engineer · CS Undergraduate, SGGS Nanded**

A hand-built, framework-free portfolio with a pull-cord theme switch, three explorable project doors, a live colour-reveal portrait and a scroll-driven story timeline.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES%20Modules-F7DF1E?logo=javascript&logoColor=black)
![No build step](https://img.shields.io/badge/build-none-2ea44f)
![Hosting](https://img.shields.io/badge/hosting-GitHub%20Pages-181717?logo=github)

[Live site](#-live-site) · [Features](#-features) · [Run locally](#-run-locally) · [Deploy](#-deploy-with-github-pages) · [Customize](#-customize) · [Contact](#-contact)

</div>

---

## 🌐 Live site

Once GitHub Pages is enabled (see [Deploy](#-deploy-with-github-pages)), the site is published at:

`https://vivek123ortho.github.io/My_Portfolio/`

## ✨ Features

| Feature | Details |
|---|---|
| **Pull-cord theme switch** | A canvas rope with spring and Verlet-style physics. Pull it down to toggle between a warm ivory light theme and a neutral greyish-black dark theme. Your choice is remembered between visits. |
| **Smooth theme transition** | Uses the View Transitions API where the browser supports it, with an instant fallback elsewhere and for visitors who prefer reduced motion. |
| **Three project doors** | *Full-Stack Web*, *Generative AI* and *DSA & Core CS*. Each door swings open and reveals a full-screen room with its projects. The doors form a scroll-pinned carousel on phones. |
| **Live LeetCode stats** | The DSA room loads solved counts from public LeetCode stats services and falls back gracefully if they are unavailable. |
| **Colour-reveal portrait** | A background-free cut-out portrait with a grayscale base and a colour reveal that follows the cursor. |
| **Role keycard** | The "I am a …" headline flips through roles like a desk calendar. |
| **3D profile card** | A layered card with tilt, shine and a flip interaction. |
| **Technical skills section** | Six categories (Languages, Web, Databases, Generative AI, Tools, Fundamentals) in a responsive card grid. |
| **Story timeline** | A scroll-driven timeline from the newest project (Clarify SQL) back through GramPulse, AgroGreenBits, RentSafe AI, B.Tech and school. |
| **Live clock** | Indian Standard Time clock in the header. |
| **Smooth scrolling** | Inertial scrolling powered by [Lenis](https://github.com/darkroomengineering/lenis). |
| **Responsive and accessible touches** | Layouts adapt from phones to large desktops, `prefers-reduced-motion` is respected, and fonts are self-hosted. |

## 🗂 Page sections

1. **Hero** (`#home`): introduction, rotating roles, portrait and profile card
2. **Doors** (`#works`): Full-Stack Web, Generative AI, DSA & Core CS rooms
3. **Skills** (`#skills`): technical skills grid
4. **Story** (`#about`): experience and education timeline
5. **Footer** (`#contact-footer`): call to action, navigation and profile links

## 🧰 Tech stack

| Area | Choice |
|---|---|
| Markup and styling | HTML5 and modern CSS (custom properties, `color-mix`, `clip-path`, 3D transforms, `backdrop-filter`) |
| Behaviour | Vanilla JavaScript loaded as an ES module |
| Smooth scroll | Lenis 1.3 (bundled in `vendor/`) |
| Typeface | Onest, self-hosted WOFF2 |
| Images | WebP |
| Build tooling | None. There is no bundler, package manager or framework. |

## 📁 Project structure

```text
.
├── index.html              # Page markup, styles and content
├── js/
│   └── app.js              # Interactions, theme logic, project data, LeetCode widget
├── assets/                 # Portrait images (colour and grayscale layers)
├── card/                   # Layers for the 3D profile card
├── fonts/                  # Self-hosted Onest fonts
├── vendor/
│   └── lenis.min.mjs       # Lenis smooth-scroll library
└── README.md
```

## 🚀 Run locally

**Requirements:** a modern browser with JavaScript enabled and a local web server (Python 3 is enough). Nothing else needs to be installed.

1. Clone the repository and move into it:

   ```bash
   git clone https://github.com/vivek123ortho/My_Portfolio.git
   cd My_Portfolio
   ```

2. Start a local server in the folder that contains `index.html`:

   ```bash
   python -m http.server 3000
   ```

   On Windows, if `python` is not recognised, use `py -m http.server 3000`.
   You can also use `npx serve .`, or the **Live Server** extension in VS Code (right-click `index.html` → **Open with Live Server**).

3. Open <http://localhost:3000>. Stop the server with `Ctrl+C`.

> Open the site through a server, not by double-clicking `index.html`. The page loads JavaScript as an ES module, which browsers block on `file://` pages.

## 🌍 Deploy with GitHub Pages

The repository is a static site, so GitHub Pages can host it directly:

1. Push the project to the `main` branch of your repository.
2. Open the repository on GitHub and go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the `main` branch and the `/ (root)` folder, then save.
5. Wait for the deployment to finish. GitHub shows the published URL on the same page.

Every later push to `main` redeploys the site automatically.

**Other hosts:** the folder also works as-is on Netlify (drag it onto <https://app.netlify.com/drop>), Vercel (framework preset *Other*) and Cloudflare Pages (no build command, output directory `/`).

### Publishing your latest changes

```bash
git add .
git commit -m "Update portfolio"
git push origin main
```

## 🛠 Customize

| I want to change… | Where |
|---|---|
| Projects inside the three doors, door names and hover text | `DOORS_INFO` in `js/app.js` |
| Rotating roles ("I am a …") | the `words` list in `js/app.js` |
| LeetCode username | `LC_USER` in `js/app.js` |
| LeetCode numbers when the public services are down | `LC_FALLBACK` in `js/app.js`, for example `{ total: 120, easy: 60, medium: 50, hard: 10 }`. Leave it as `null` to use live stats only. |
| Skills | the `techskills` section (`#skills`) in `index.html` |
| Story timeline entries | the `ch` items inside the `story` section (`#about`) in `index.html` |
| Contact details and footer links | the footer (`#contact-footer`) in `index.html` |
| Page title and description | the `<head>` of `index.html` |
| Portrait | `assets/hero_color.webp` and `assets/hero_gray.webp` (keep the same size and a transparent background) |
| Light and dark colours | the `:root` and `html[data-mode="dark"]` variables in `index.html` |

### Adding a project to a door

Add an object to a door's `projects` array in `DOORS_INFO`:

```js
{
  badge: 'Python · Oct 2026',
  title: 'My New Project',
  desc: 'One sentence about what it does.',
  bullets: ['What you built.', 'The result or impact.'],
  tags: ['Python', 'FastAPI'],
  link: 'https://github.com/your-username/your-repo',
  feat: true            // optional: makes the card full width
}
```

### About the LeetCode widget

The counts come from free, public third-party services, so they can be delayed or unavailable. No API key is needed. If every service fails and `LC_FALLBACK` is `null`, the card hides the numbers and points visitors to the profile instead.

## 🧪 Troubleshooting

| Problem | Fix |
|---|---|
| Blank page, missing fonts or console module errors | Serve the folder over HTTP (see [Run locally](#-run-locally)). |
| Changes don't show after deploying | Hard refresh (`Ctrl/Cmd + Shift + R`) and wait a minute for GitHub Pages to finish. |
| LeetCode card has no numbers | The public service may be down. Set `LC_FALLBACK`, or use the profile button on the card. |
| Theme resets on every visit | The browser is blocking local storage (for example in private mode). The theme still works for the current visit. |

## 🌐 Browser support

Current versions of Chrome, Edge, Safari and Firefox. The site relies on modern CSS (`color-mix`, `clip-path`, `backdrop-filter`) and ES modules, so very old browsers are not supported. The View Transitions API is used only where available.

## 👤 Contact

**Vivek Pundkar**

- Email: [vivekpundkar45@gmail.com](mailto:vivekpundkar45@gmail.com)
- GitHub: [@vivek123ortho](https://github.com/vivek123ortho)
- LinkedIn: [Vivek Pundkar](https://www.linkedin.com/in/vivek-pundkar-871896333)
- LeetCode: [vivek_pundkar](https://leetcode.com/u/vivek_pundkar)

## 📄 Credits and licence

- [Lenis](https://github.com/darkroomengineering/lenis) is used under the MIT licence.
- [Onest](https://fonts.google.com/specimen/Onest) is used under the SIL Open Font Licence.
- The text, project descriptions and portrait are © Vivek Pundkar. Please don't reuse them as your own.
