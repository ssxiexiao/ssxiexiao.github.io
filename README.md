# Homepage Maintenance

This folder contains the static site that can be opened directly by clicking `index.html`.

## Source of truth

Update metadata in:

- `data/site.json`

Template file:

- `index.template.html`

## Regenerate the homepage

Run the build script located outside this folder:

- `../build_homepage.py`
- or double-click `../build_homepage.bat` on Windows

That script first tries to sync matched paper metadata from DBLP, then writes the final static `index.html`.

Optional import:

- `python ../build_homepage.py --import-latest-ccf-a`

This optional flag checks the Google Scholar profile, finds the latest missing CCF-A paper, enriches it with DBLP metadata, appends it to `data/site.json`, and then rebuilds the homepage. It is off by default.

## Add a new paper

1. Put the preview image in `images/`.
2. Put the PDF in `papers/`.
3. Add one paper object to `data/site.json`.
4. Run the external build script.

Recommended asset naming:

- use lowercase kebab-case filenames
- image example: `images/vismimic.png`
- pdf example: `papers/vismimic.pdf`

Required paper fields:

- `title`
- `authors`
- `venue`
- `year`
- `image`

Optional fields:

- `pdf`
