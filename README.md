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
├── netlify.toml            ← Netlify settings (no build) + caching/security headers
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

## 4. Deploy free on Netlify (easiest)

**Option A: drag and drop (no account setup beyond sign-up)**
1. Go to https://app.netlify.com and sign up (free).
2. Open **Sites** and choose **Add new site → Deploy manually**.
3. Drag the whole `portfolio` folder onto the upload area.
4. Netlify gives you an address like `https://random-name-123.netlify.app`. In **Site configuration → Change site name** you can pick something like `jayanne-otadora`.
5. Do the **After your first deploy** steps below, then drag the folder in again to update the site.

**Option B: connected to GitHub (updates automatically on every change)**
1. Put the `portfolio` folder in a GitHub repository (see section 5, steps 1–3).
2. In Netlify choose **Add new site → Import an existing project → GitHub** and pick the repository.
3. Leave **Build command** empty. Set **Publish directory** to `.`, or to `portfolio` if the folder is inside a bigger repository. Click **Deploy**.

## 5. Deploy free on GitHub Pages

1. Sign in at https://github.com and click **New repository**. Name it, for example, `portfolio`, set it to **Public**, and click **Create repository**.
2. Open the upload page. Use whichever of these you see:
   * **Empty repository** (you see a "Quick setup" box): in the sentence "…or **uploading an existing file**", click the blue words *uploading an existing file*.
   * **Repository already has files** (for example, you ticked "Add a README"): click the **Add file** button above the file list, then **Upload files**.
   * **Can't find either**: type this address into your browser, using your own username: `https://github.com/YOUR-GITHUB-USERNAME/portfolio/upload/main`
3. You'll see a big box that says "Drag files here to add them to your repository".
   * In File Explorer, open the `portfolio` folder and press **Ctrl + A** to select everything inside it: the `assets`, `css` and `js` folders plus all the files. Don't select the `portfolio` folder itself.
   * Drag the selection into the box on GitHub and wait for every file to finish uploading. Use Chrome or Edge so that the folders upload too. The "choose your files" button can't upload folders.
   * Scroll down and click the green **Commit changes** button.
   * Check: the repository's main page should show `index.html` in the file list, next to the `assets`, `css` and `js` folders. If you see a single `portfolio` folder instead, the folder itself was uploaded and you'll need to start again with an empty repository.
4. Go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then click **Save**.
5. After 1–2 minutes your site is live at `https://YOUR-GITHUB-USERNAME.github.io/portfolio/`.

## 6. After your first deploy (important for SEO and link previews)

1. Copy your live address, e.g. `https://jayanne-otadora.netlify.app/`.
2. In `index.html`, replace every `https://YOUR-SITE-URL/` with that address (5 places in the `<head>`). Use your editor's Find & Replace.
3. Do the same in `sitemap.xml` and `robots.txt`. In `robots.txt`, also delete the `#` before `Sitemap:`.
4. Re-upload or commit the changed files.
5. Optional: test the link preview with LinkedIn's Post Inspector (https://www.linkedin.com/post-inspector/) and submit the sitemap in Google Search Console.
6. Optional: connect a custom domain (Netlify: **Domain management**; GitHub: **Settings → Pages → Custom domain**). Both include free HTTPS.

---

## 7. ⚠️ Please verify before publishing

I didn't invent any experience, numbers, testimonials, or contact details. These items came from the PDF and need your confirmation, or were deliberately changed:

| # | Item | What to check |
|---|------|---------------|
| 1 | **Third testimonial (Rosalee Maquinay)** | **Hidden.** It reads like feedback written *about a client* ("the client was responsive to any of my requests for clarification"), not about you. If it really is about your work, un-comment it in `index.html`; search for `HIDDEN — PLEASE VERIFY`. |
| 2 | Testimonials from **Luxe Lending Corp** and **Property Finance Corp** | Confirm the wording is exact, the company names are right, and you have permission to publish them. Consider adding the reviewer's name and role, which makes testimonials more credible. The 5-star ratings come from the PDF. |
| 3 | **Pricing** | The PDF has no rates, weekly hours, or time zone, so none are shown. A commented placeholder is in the Pricing section if you want to add them. |
| 4 | **Case studies** | The PDF lists outcomes without numbers, so none were added. "Nine custom Claude skills": confirm the count. If you have real metrics (hours saved, records managed), adding them will strengthen this section. |
| 5 | **Contact details** | Email `sweet_loving_ann@yahoo.com`, phone `+63 936 847 8110`, plus your LinkedIn and Upwork URLs. Open each link once after deploying. A phone number on a public site can attract spam calls, so you can delete that line if you prefer. Many freelancers use a name-based email (e.g. firstname.lastname@…) for a more professional first impression. |
| 6 | **"Artlist.ai"** | Written as plain **Artlist** on the site, because Artlist's official site is artlist.io. Change it back if you meant a different product. |
| 7 | **"How I Work", step 4** | The PDF said "Ongoing support and regular updates", which repeated step 3 ("Daily/Weekly Updates"). It now reads "Ongoing support". |
| 8 | **Stock photos** | The 4 "How I Work" images, the laptop graphic, and the brushstroke texture are Canva template or stock elements. Canva's licence generally covers use in your own designs. If you ever download them from Canva separately, check the licence. |

### Other corrections made to the PDF text
* "CRMsBuild dashboards and reports" (two items merged) was split into "Managing client databases and CRMs" and "Building dashboards and reports".
* "Improve client communication" appeared twice in Services. It is now listed once.
* "Google Apps Script automationse Solution" became "Google Apps Script automation solutions".
* The internal note "strongest accomplishments to mention" was replaced with "Selected accomplishments and the results they delivered."
* The About text was split into proper sentences, with consistent capitalisation in lists. "Initial consultation to understand your need" became "…your needs".

### Design notes
* **Fonts**: the PDF uses *LeJour Serif* (a paid Canva font) and *Poppins*. The site uses Poppins plus **Antic Didone**, a free Google Font with a similar tall, high-contrast look. If you own a web licence for LeJour Serif, add it with `@font-face` and put its name first in `--font-display`.
* **Accessibility**: the PDF's antique gold on blush pink has low contrast (about 1.4:1). It is kept **only for the large display headings**, to preserve the look. All body text, links, labels, and buttons use dark ink or burgundy, which meet WCAG AA contrast. For maximum accessibility, set `--gold` to a darker bronze such as `#6b4a0c`.
* Animations are limited to a colour change on button hover. Smooth scrolling turns off automatically for visitors who ask their device to reduce motion.
