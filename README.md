# Ben Workman's academic website

A small, dependency-free academic website built with HTML and CSS. The design
is original and uses the clean, single-page structure common on economics
researchers' websites.

## Preview locally

From this folder, run:

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000). Stop the server with
`Control-C`.

## Personalize the site

### Email

The site currently uses `benworkm@mit.edu`.

### Photo

Add a portrait at `assets/profile.jpg`. A portrait around 800 × 1000 pixels
works well. Then change this line in `index.html`:

```html
src="assets/profile-placeholder.svg"
```

to:

```html
src="assets/profile.jpg"
```

Also change the image's `alt` text from "Placeholder portrait for Ben Workman"
to "Ben Workman".

### CV

Edit the academic CV in `files/cv.tex`. Rebuild the linked PDF from the project
root with:

```bash
latexmk -pdf -outdir=files files/cv.tex
```

### Working papers

Put PDFs in the `papers` directory—for example,
`papers/teacher-labor-markets.pdf`. GitHub serves these as normal files, so a
publicly published site would make that PDF available at:

```text
https://YOUR-DOMAIN/papers/teacher-labor-markets.pdf
```

To list a paper, remove the "Working papers will appear here" paragraph in
`index.html` and uncomment/copy the sample `<article class="paper">` block.
The paper title links to the PDF, and the native `<details>` element provides
the expandable abstract.

Use short, stable, lowercase filenames with hyphens and no spaces. Updating a
PDF at the same path keeps its URL unchanged.

### Publications and other writing

These sections already exist in `index.html` but have the `hidden` attribute.
Remove `hidden` when there is content to show, then add entries using the same
article structure as working papers.

## GitHub and publishing

The GitHub repository is private, so only collaborators can see its source.
Preview it locally while it is private.

When the site is ready to be public:

1. Decide whether to use `ben-workman.github.io` or keep this repository and
   publish it as a project site.
2. In the repository's GitHub settings, open **Pages**.
3. Select **Deploy from a branch**, then choose `main` and `/ (root)`.

GitHub Pages sites are normally public even when the source repository is
private. Do not enable Pages until the content and PDFs are ready for public
viewing.
