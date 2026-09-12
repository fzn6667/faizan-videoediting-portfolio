# Faizan Haider — Video Editor Portfolio

Plain HTML/CSS/JS portfolio site. No build tools, no frameworks, no backend.

## Files

```
index.html   → all page content and structure
style.css    → all styling (dark cinematic theme, timecode motif)
script.js    → mobile menu, portfolio filtering, form validation, smooth scroll
assets/
  images/        → your profile photo goes here (already added: faizan-profile.webp)
  thumbnails/    → video thumbnail images go here
```

## 1. Replace your photo

Your uploaded photo is already placed at `assets/images/faizan-profile.webp` and
linked in the hero section. To swap it for a different photo, replace that file
(keep the same name) or update the `src` on this line in `index.html`:

```html
<img src="assets/images/faizan-profile.webp" alt="Portrait of Faizan Haider" class="portrait-img">
```

## 2. Add real video thumbnails

Drop your thumbnail images into `assets/thumbnails/` and update the `src` on each
`<img>` inside `.project-thumb` in the **Portfolio / Selected Work** section of
`index.html`. Filenames currently expected (all placeholders — none exist yet,
so each card shows a "PLACEHOLDER THUMBNAIL" label until you add real files):

- `placeholder-documentary-1.jpg`
- `placeholder-reel-1.jpg`
- `placeholder-youtube-1.jpg`
- `placeholder-promo-1.jpg`
- `placeholder-documentary-2.jpg`
- `placeholder-reel-2.jpg`

## 3. Add your real project links

Each project card has a play button:

```html
<a href="#" class="project-play" aria-label="Watch: ... — replace this link">▶</a>
```

Replace `href="#"` with the real YouTube/Vimeo/Fiverr link for that project.
Update the `<h3>` title and `<p>` description at the same time so they describe
the real project (the current text is clearly marked as placeholder copy).

To add a new project card, copy one whole `<article class="project-card" ...>`
block and give it a `data-category` of `documentary`, `reels`, `youtube`, or
`promotional` so the filter buttons pick it up.

## 4. Add your Fiverr link

In the **Contact** section of `index.html`, find:

```html
<a class="contact-link" href="#" data-placeholder="fiverr">
```

Replace `href="#"` with your real Fiverr profile URL, and remove the
`data-placeholder="fiverr"` attribute (it currently makes the link pop up a
reminder instead of navigating, via `script.js`).

Your email, WhatsApp, LinkedIn, X, and Instagram links are already filled in
with the real details you provided.

## 5. Connect the contact form to something real

Right now, submitting the form only validates the fields in the browser and
shows a local confirmation message — **no email is actually sent.** To make it
functional, pick one:

- **Form backend service** (easiest): sign up for something like Formspree,
  Getform, or Web3Forms, point the `<form>`'s `action` at the endpoint they
  give you, and let it POST normally.
- **Your own backend**: replace the placeholder logic at the bottom of
  `script.js` (inside the `form.addEventListener('submit', ...)` block) with a
  `fetch()` call to your API, which then sends the email server-side.

## Run it locally

No build step needed. Either:

- Open `index.html` directly in a browser, or
- Serve it locally (recommended, avoids some browser file:// restrictions):

  ```bash
  cd portfolio
  python3 -m http.server 8000
  ```

  Then visit `http://localhost:8000`.

## Deploy on GitHub Pages

1. Create a new GitHub repository and push this folder's contents to it:

   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```

2. On GitHub: go to the repo → **Settings** → **Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`,
   branch `main`, folder `/ (root)`. Save.
4. GitHub will publish the site at
   `https://<your-username>.github.io/<repo-name>/` within a minute or two.
