# Quiet Buddy website

The website for [Quiet Buddy](https://github.com/Quiet-Buddy/noise-meter), a free Android app that turns a phone into a friendly noise meter for a family home. This repository is published with GitHub Pages at https://quiet-buddy.github.io/.

Plain HTML and one CSS file. No build step and no JavaScript framework.

## Folder layout

```
index.html          Language chooser (redirects to en/, es/ or eu/)
404.html            Trilingual "Page not found" page
assets/site.css     The only stylesheet
en/                 English pages (index.html, privacy.html)
es/                 Spanish pages (same file names as en/)
eu/                 Basque pages (same file names as en/)
.github/workflows/  pages.yml (deploys to Pages), check.yml (checks internal links)
.nojekyll           Tells GitHub Pages to serve the files as they are
```

Buddy is drawn as inline SVG in each page. There are no image files.

## Preview locally

From the repository root:

```sh
python3 -m http.server
```

Then open http://localhost:8000/. Use http://localhost:8000/en/ to go straight to the English pages.

## Translations

Each language folder mirrors `en/`. Keep the same file names in every folder, so `en/privacy.html` has a counterpart at `es/privacy.html` and `eu/privacy.html`.

- Translate the visible text inside the HTML. Keep the structure, the inline SVG and the scripts the same as in the English page.
- Update `lang`, `hreflang`, `og:locale` and the `<title>` and `<meta name="description">` of each translated page.
- The language switcher links and the `hreflang` alternates are already present in the English pages. Keep them consistent when you copy them.
- Spanish (`es/`) and Basque (`eu/`) copy needs review by a native speaker before it goes live.

## Checks

The "Check site" workflow runs on pull requests and checks internal links with lychee in offline mode. It does not check external URLs.

## Deployment

Pushing to `main` deploys the site through the "Deploy site" workflow. It can also be started by hand from the Actions tab.
