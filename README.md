# Jay Anne Otadora — Portfolio Website

A static one-page portfolio built from the 10-page "Virtual Assistant Presentation" PDF.
It uses plain HTML, CSS, and a little JavaScript. There is no build step and nothing to install, so it deploys for free on Netlify or GitHub Pages.

---

## 1. Project structure

```
portfolio/                  ← deploy THIS folder
├── index.html              ← all content, one clearly labelled block per section
├── 404.html                ← "page not found" page
├── css/styles.css          ← all styling; colours and fonts live in :root at the top
├── js/main.js              ← mobile menu, active nav link, footer year
├── assets/images/
│   ├── portrait-*.jpg      ← your 6 portraits, extracted from the PDF byte-for-byte (not re-compressed or edited)
│   ├── work-*.jpg          ← the 4 "How I Work" photos from the PDF (resized only)
│   ├── tools-laptop.png    ← laptop graphic from the PDF (resized only)
│   ├── check.png           ← red checkmark from the PDF
│   ├── thank-you-texture.jpg ← brushstroke background from the "Thank You" slide
│   ├── og-image.jpg        ← 1200×630 social-sharing preview
│   └── favicon.svg
├── .nojekyll               ← tells GitHub Pages to serve files as-is
├── robots.txt
└── sitemap.xml
```

The sections in `index.html`, in order:
1 Hero · 2 About · 3 Services · 4 Tools & Software · 5 How I Work · 6 Pricing & Availability · 7 Case Studies · 8 Testimonials · 9 Contact · 10 Thank You / Footer

## 2. Editing content

* **Text**: open `index.html` and search for the section comment, e.g. `<!-- ================= 3. SERVICES`. Edit the text between the tags.
* **Add a service or tool**: copy one `<li>…</li>` line and change the text.
* **Colours / fonts**: change the variables at the top of `css/styles.css` (`--blush`, `--burgundy`, `--gold`, `--font-display`, …). The whole site updates.
* **Swap a photo**: replace the file in `assets/images/` and keep the same file name. If the new photo has a different size, update the `width`/`height` attributes on its `<img>` tag.
* **Résumé download (optional)**: create `assets/resume/`, add your PDF as `Jay-Anne-Otadora-Resume.pdf`, then in `index.html` find `OPTIONAL RESUME BUTTON` and delete the `<!--` and `-->` around the button.

## 3. Preview on your computer

Double-clicking `index.html` works for a quick look. For an exact preview, run any local web server from inside the `portfolio` folder. For example, with Python installed:

```bash
python -m http.server 8080
```

Then open http://localhost:8080.

