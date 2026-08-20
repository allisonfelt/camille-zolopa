# camille-zolopa

Personal academic website for Camille Zolopa, PhD candidate in Counselling
Psychology at McGill University.

Plain HTML and CSS — no build step, no dependencies.

## Local preview

From the repo root:

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Files

- `index.html` — all page content
- `style.css` — all styling

## Adding the CV

The CV section has a commented-out download button. To enable it, add a
`Camille_Zolopa_CV.pdf` to the repository root and uncomment that button in
`index.html`.

Use a web copy of the CV with phone numbers and any other private contact
details removed — everything committed here is publicly downloadable.

## Editing content

Everything is in `index.html`, in plain sections: About, Education, Research,
Publications, Presentations, Clinical Experience, Service, CV, Contact. To add
a publication, copy an existing `<li>` inside the relevant `<ol class="pub-list">`
and edit it.

## Hosting

Set up for GitHub Pages: repository Settings → Pages → deploy from the `main`
branch, root folder.
