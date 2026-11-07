# Vivek Pundkar — Personal Portfolio

A responsive, interactive personal portfolio built with HTML, CSS, and vanilla JavaScript. It features animated project showcases, a canvas-based pull cord, a 3D profile card, a scrolling timeline, and light and dark themes.

## Features

- Interactive pull cord with spring and Verlet-style motion; pull it to switch themes.
- Animated desk calendar and scrolling timeline.
- Portrait with a cursor-following color reveal.
- 3D profile card with tilt, shine, and flip interactions.
- Interactive project doors and detail panels.
- Live Indian Standard Time clock.
- LeetCode statistics loaded from public third-party APIs, with optional fallback values.
- Responsive layout and locally hosted Onest fonts.

## Requirements

- A modern browser with JavaScript enabled.
- A local HTTP server for development. Python 3 is one option.

There is no build step, package installation, or framework setup required.

## Run locally

1. Clone the repository and move into the project directory:

   ```bash
   git clone https://github.com/vivek123ortho/My_Portfolio.git
   cd My_Portfolio
   ```

2. Start a local web server from the directory containing `index.html`:

   ```bash
   python -m http.server 3000
   ```

   If `python` is not recognized on Windows, try:

   ```powershell
   py -m http.server 3000
   ```

   Alternatively, use the **Live Server** extension in Visual Studio Code and choose **Open with Live Server** on `index.html`.

3. Open [http://localhost:3000](http://localhost:3000) in your browser. Stop the Python server with `Ctrl+C`.

> Open the site through a local server rather than directly as a `file://` page. The portfolio loads JavaScript as an ES module, which browsers restrict when opened directly from disk.

## Deploy with GitHub Pages

The repository is a static site and can be hosted directly with GitHub Pages:

1. Open the repository on GitHub and go to **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and the `/(root)` folder, then save.
4. Wait for the deployment to finish. GitHub will show the published site URL in the Pages settings.

After pushing changes to `main`, GitHub Pages will publish the updated site automatically.

## Project structure

```text
.
├── index.html              # Page markup and styles
├── js/
│   └── app.js              # Interactions and portfolio behavior
├── assets/                 # Portrait images
├── card/                   # Profile card artwork
├── fonts/                  # Locally hosted Onest fonts
└── vendor/
    └── lenis.min.mjs       # Lenis smooth-scroll library
```

## Customize

- Update the portfolio content, contact information, and links in `index.html`.
- Update project door content in the `DOORS_INFO` data in `js/app.js`.
- The LeetCode username is configured as `LC_USER` in `js/app.js`. If the public stats services are unavailable, set `LC_FALLBACK` there to an object with `total`, `easy`, `medium`, and `hard` counts. Leave it as `null` to use live stats when available.

The LeetCode counts depend on public third-party services and may be unavailable or delayed. No API key is needed.

## Author

**Vivek Pundkar**

- Email: [vivekpundkar45@gmail.com](mailto:vivekpundkar45@gmail.com)
- GitHub: [@vivek123ortho](https://github.com/vivek123ortho)
- LinkedIn: [Vivek Pundkar](https://linkedin.com/in/vivek-pundkar-871896333)
- LeetCode: [vivek_pundkar](https://leetcode.com/u/vivek_pundkar)
