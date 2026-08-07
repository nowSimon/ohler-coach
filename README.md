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

Header and hero CTAs point to https://cal.com/simonohler/hello
Step 1 in "how we can work together" points to https://cal.com/simonohler/tonic

## Rules

- **Bump the `?v=` number on every `styles.css` link when the CSS changes.** All three
  pages reference `styles.css?v=N`. Without the bump, browsers serve cached CSS against new
  HTML and the page looks broken in ways that don't reproduce for anyone else.

- **`[ TBD ]` placeholders are Simon's to write. Never invent them.** Never carry lorem
  ipsum in from anywhere — replace it with a visible placeholder.
- The port is ahead of the MailerLite site, not behind it. Simon pulls unfinished sections
  down from live while they get finished here. Diff `www.ohler.coach` to catch copy he
  wrote there, but never delete a section from this repo just because MailerLite no longer
  shows it.
- Legal pages carry real details: Jessnerstr. 16, 10247 Berlin · USt-IdNr DE323603657.
  No phone in the Impressum — email alone satisfies §5 DDG per ECJ C-298/07.
- Google Fonts loads from Google's servers and is disclosed in the Datenschutz.
  Self-hosting the fonts would remove that disclosure.
