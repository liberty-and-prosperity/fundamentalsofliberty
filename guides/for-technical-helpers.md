# For technical helpers

Read AGENTS.md first. The main constraint: a non-technical person must be able to keep this site running for decades.

## Architecture

- Static site. Jekyll, built by GitHub Pages on each push to `main`. GitHub Pages uses Jekyll 3.10 with kramdown (GFM input).
- No plugins beyond GitHub Pages defaults. No theme gem. No JavaScript apart from the legacy redirect. No external requests: fonts are self-hosted.
- Plain CSS, no Sass.

## File map

```
_config.yml                 site settings, nav, sections, layout defaults, exclude list
_layouts/default.html       HTML shell: head, masthead, footer
_layouts/home.html          home page body plus generated table of contents
_layouts/page.html          simple page (About, 404)
_layouts/section.html       list page for a section (essays/index.md, reading-list/index.md)
_layouts/sequence.html      essay or reading list item: position label, prev/next
_includes/section-list.html ordered list of a section's pages (by front matter "order")
_includes/family-note.html  renders page.family_note
_includes/legacy-redirect.html  ?page_id=N redirect, map in _data/legacy_urls.yml
assets/css/site.css         all styles (tokens in :root)
assets/fonts/               Libre Caslon Text and Display, woff2, OFL
images/                     all content images
CNAME                       custom domain for GitHub Pages (keep it)
.pages.yml                  Pages CMS schema (optional editor)
```

## Conventions

- Section membership comes from the folder, through `defaults` in `_config.yml`. Pages do not need `layout` or `section` in front matter.
- A page with `order` is listed. A page without `order` (the section `index.md`) is not.
- `permalink: pretty`. Addresses are `/folder/file-name/`. File names are part of the public URL, so do not rename files.
- Internal links in content are root-relative (`/essays/...`). This works because the site runs on the apex custom domain. If the site ever runs under a sub-path (for example `ORG.github.io/fundamentalsofliberty/` with no custom domain), internal links will break. Keep the custom domain.

## Preview locally (pwsh)

Option 1, Docker (no Ruby install):

```powershell
cd path\to\fundamentalsofliberty
docker run --rm -it -p 4000:4000 -v "${PWD}:/site" -w /site ruby:3.3 `
  bash -c "bundle install && bundle exec jekyll serve --host 0.0.0.0"
```

Then open http://localhost:4000. The first run takes a few minutes.

Option 2, Ruby on Windows: install Ruby+Devkit from https://rubyinstaller.org. Use **Ruby 3.3**. The `github-pages` gem pins Jekyll 3.10, which does not run on Ruby 3.4.

```powershell
cd path\to\fundamentalsofliberty
bundle install
bundle exec jekyll serve
```

Then open http://127.0.0.1:4000 in a browser. Press Ctrl+C in that window to stop the server.

Notes from a setup that worked (Windows 11, Ruby 3.3.12, 2026-09-21):

- The first `bundle install` took about 15 minutes and printed nothing while it worked out which gems it needed. This is normal. Later runs take seconds.
- If the computer has more than one Ruby, put the one you want first, for that window only:

```powershell
$env:Path = "C:\Ruby33-x64\bin;$env:Path"
```

- `bundle exec jekyll build` writes the finished site to `_site`. Git ignores that folder.

`Gemfile` pins the `github-pages` gem so the local build matches GitHub.

## Before you push

- [ ] `bundle exec jekyll build` has no errors or warnings.
- [ ] Home, both list pages, one essay, one reading list item, About, and 404 render correctly on desktop and on a phone-width window.
- [ ] `/?page_id=467` redirects to Preamble to the Constitution.
- [ ] Previous and next links are correct at both ends of each section.
- [ ] The author's body text is unchanged (compare with `git diff`).
- [ ] Docs match any structural change.

## Design notes

- Palette: the author's gold `#AA9B55` (the background he chose in January 2011), ink `#231F17`, paper `#FFFDF7`, link red `#8C1C13` (his original link color, darkened for contrast).
- Type: Libre Caslon. Caslon was the typeface of the first printed Declaration of Independence. Display cut for titles, Text cut for reading.
- One column, about 37rem wide, left-aligned.
- Print styles hide navigation, so essays print cleanly. The author planned to hand out printed essays.

## Restoration source

The site was rebuilt in 2026 from Wayback Machine captures (2016 to 2018) with a conversion script. The raw captures and the author's Word documents are in the private family archive. `CONTENT-CHANGES.md` lists every editorial decision.
