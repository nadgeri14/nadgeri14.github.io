# Abhishek Nadgeri's homepage

A single, static academic homepage for <https://nadgeri14.github.io/>. Plain HTML
and CSS with a self-hosted serif font, and no framework, third-party requests, or
build. Two small inline scripts power the light/dark toggle (top-right): the page
starts in the visitor's OS setting, and a choice made with the button is
remembered in their browser. Without JavaScript the page shows in light mode and
the button stays hidden.

## Edit

- **`index.html`** contains all homepage content, CSS, and the toggle scripts.
  Colors are defined once at the top of the CSS (`:root` for light, and
  `:root[data-theme="dark"]` for dark); the single blue accent is reserved for
  links. Papers appear newest first with a year, title,
  authors, and a venue tag. On larger screens the list scrolls inside the page:
  a visible scrollbar, a faded bottom edge, and a "3 more papers" pill (counted
  by a small script; clicking it scrolls down) show that more papers follow. On
  phones and in print it shows in full. To add the RLVR paper, copy the first publication `<li>` and
  update its citation. Wrap your name in `<strong>`.
- **`headshot.jpg`** (480×600) is the photo shown on the page, a 4:5 crop of
  **`photo.jpg`**, your original from `Desktop/IMG_0254.jpg`. The original is
  preserved as supplied and is used as the link-preview image. If you replace
  the photo, export a new 4:5 crop as `headshot.jpg`.
- **`fonts/`** holds Source Serif 4 (roman with optical sizes, and italic),
  licensed under the SIL Open Font License in `fonts/OFL.txt`. Other text, such
  as the links and section labels, uses the system sans-serif font.
- **`cv.pdf`** should contain your actual CV. It is not included yet; add it to
  the repository root to activate the existing CV link.
- **`favicon.svg`** is the blue favicon.
- Update the footer's visible month/year and its `datetime` attribute after edits.
- Email is written as `[at]` / `[dot]`, without a plaintext `mailto:` address.

Paper titles, author order, and venues were checked against the linked
OpenReview / author repositories, AAAI proceedings, ACL Anthology, and arXiv
records. Google Scholar could not be retrieved during setup. The two 2020
papers are ordered by their publication months (November, then October).

## Preview

Run this from the repository root (opening `index.html` directly also works,
though some browsers block the web font from `file://` pages):

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Then visit <http://127.0.0.1:8000>.

## GitHub Pages

In the repository's **Settings → Pages → Build and deployment**, select
**GitHub Actions** as the source. Push to `master`, or run **Deploy homepage to
GitHub Pages** manually from the Actions tab. The workflow publishes only the
homepage, favicon, both photos, `fonts/`, and `cv.pdf` (when present).

You can also use **Deploy from a branch → master → / (root)**: `.nojekyll`
lets GitHub Pages serve the HTML directly. In that case, disable the Actions
workflow to avoid two deployment mechanisms.

The former al-folio template files remain in the repository for reference;
the homepage and Actions deployment do not use them.
