# camille-zolopa

Personal academic website for Camille Zolopa, PhD candidate in Counselling
Psychology at McGill University.

**Live at <https://allisonfelt.github.io/camille-zolopa/>**

Plain HTML, CSS, and a little vanilla JavaScript. No build step, no
dependencies, no framework.

## Local preview

From the repo root:

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | All page content, plus the tab and motion scripts |
| `style.css` | All styling |
| `Camille_Zolopa_CV.pdf` | Downloadable CV (phone numbers redacted) |
| `portrait.jpg` | Hero portrait |
| `conference.jpg` | Denver conference photo, Presentations tab |
| `desk.jpg` | About tab |
| `memphis.jpg`, `reading.jpg` | Personal panel in the About rail |
| `favicon.svg`, `favicon.ico`, `apple-touch-icon.png` | CZ monogram icons |

## How the page is organized

One page, seven tabs: About, Research, Publications, Presentations,
Clinical, Service, Contact. Her name, the portrait, and a facts strip sit
above the tabs and stay visible.

Tabs are plain buttons wired up in the script at the bottom of
`index.html`. They support arrow-key navigation and deep links such as
`/#publications`. **Panels are visible by default in the markup and hidden
by the script on load**, so with JavaScript disabled the page degrades to
one long readable document. Don't add `hidden` to a panel in the HTML —
that breaks the no-JS fallback.

## Editing content

Everything lives in `index.html`.

To add a publication, copy an existing `<li>` in the right year group under
Publications and edit it. Wrap her name as
`<strong class="me">Zolopa, C.</strong>` so it picks up the accent colour.
DOI links use `class="doi"` with `target="_blank"`, which adds the external
arrow. Open-access articles carry `<span class="oa">Open access</span>`.

If a new year is needed, copy a whole `.year-group` block.

## Caching

`index.html` links the stylesheet as `style.css?v=YYYYMMDDHHMM`. GitHub
Pages serves CSS with a long cache lifetime, so **bump that version string
whenever you edit `style.css`**, or returning visitors keep the old styles.

## Images

Web copies only — resized, and converted to JPEG. Photos from phones often
arrive as HEIC, which Chrome and Firefox will not display, and at several
megabytes each. Convert and resize before committing, and don't keep the
originals in the repo.

## Hosting

GitHub Pages, deploying from `main` / root. Every push to `main` publishes
within about a minute.

A custom domain can be set under Settings → Pages → Custom domain; it needs
a `CNAME` file in the repo root and DNS records at the registrar.
