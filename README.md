# ohler.coach

Simon Ohler's coaching site. Static HTML/CSS, hosted on GitHub Pages.

Ported off MailerLite Pages, Aug 2026.

## Files

- `index.html` — the homepage
- `impressum/index.html` — Impressum, served at `/impressum/`
- `styles.css` — all styling, shared by every page
- `assets/` — images

## Adding a subpage

One folder per page, each containing an `index.html`. The folder name is the URL.

```
newpage/index.html   ->   ohler.coach/newpage/
```

Copy `impressum/index.html` as the starting point — it already has the header, footer
and the right paths. From inside a subfolder, everything at the top level is reached
with `../`:

```html
<link rel="stylesheet" href="../styles.css">
<img src="../assets/logo.png">
<a href="../">back to the homepage</a>
```

Then add a link to the new page in the footer of every page.

## Editing

Open `index.html` in any text editor. The copy lives directly in the HTML — search for
the sentence you want to change and edit it in place.

To preview locally:

```
cd ohler-coach-site
python3 -m http.server 8000
```

Then open http://localhost:8000

## Deploying

Push to `main`. GitHub Pages rebuilds automatically within a minute or two.

## Booking

All CTAs point to https://cal.com/simonohler/hello
