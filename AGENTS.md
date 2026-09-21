# Rules for AI helpers

You are helping a family look after **fundamentalsofliberty.com**. The site was online from 2011 to 2018. The author's family restored it from archived copies and now looks after it.

The people who ask you for help may not be technical. Explain what you will do, in plain language, before you do it.

## Hard rules

1. **Never change the author's words.** This includes spelling, capital letters, punctuation, dashes, quotation marks, and opinions. The author's words are the Markdown body of each file in `index.md`, `about.md`, `essays/`, and `reading-list/`. Change them only when the owner asks for that exact change. Then log it (rule 3).
2. **Family additions go in the `family_note` front matter field.** Never add family text inside the author's body text. The layout shows family notes in a separate, labeled box.
3. **Log every content change** in `CONTENT-CHANGES.md`: date, page, what changed, who asked.
4. **This repository is public.** Never add passwords, account numbers, private email addresses, phone numbers, or private family documents. The author's Word documents and notes are in a private family archive, outside GitHub. Keep them out of this repository.
5. **Keep the site simple.** The site must build on GitHub Pages with no setup.
   - Do not add Jekyll plugins, themes, Node.js, npm, build tools, or GitHub Actions.
   - Do not add external scripts, analytics, trackers, ads, or fonts from other websites.
   - Do not add a contact form. The site has no server.
6. **Keep every old address working.** Do not rename or move a page file unless the owner asks. If a page moves, add the old address to `_data/legacy_urls.yml`, and tell the owner.
7. **Update the docs** (`README.md`, `STEWARDSHIP.md`, `guides/`) when you change how something works.
8. **Do not publish the author's name** on the site or in this repository unless STEWARDSHIP.md records that the family decided to. The original site never named him.
9. **Prefer small changes.** One task, one commit, with a clear commit message.

## How the site works

- Jekyll, built by GitHub Pages (Jekyll 3.10, kramdown GFM). No custom plugins.
- `_config.yml`: site title, footer line, top menu (`nav`), and `sections`.
- Page files have short front matter:
  - `title` (required)
  - `order` (essays and reading list items only; 1 is first)
  - `family_note` (optional, Markdown)
- `_config.yml` `defaults` give every file in `essays/` and `reading-list/` the `sequence` layout. That layout adds "Essay 2 of 5" and previous and next links.
- The home page and the two list pages build their lists from `order`. Nobody edits a table of contents by hand.
- `_data/legacy_urls.yml` maps old WordPress `?page_id=` numbers to new addresses. `_includes/legacy-redirect.html` does the redirect.
- Fonts are in `assets/fonts/` (Libre Caslon, SIL Open Font License). Colors and sizes are in `assets/css/site.css`. The gold `#AA9B55` is the author's original background color. Keep it.
- `.pages.yml` configures Pages CMS, an optional form-based editor. If you add a front matter field, add it to `.pages.yml` too, or Pages CMS may drop it.

## Recipes

**Add an essay or reading list item**

1. Copy an existing file in the same folder. Name the new file with lowercase words and hyphens, for example `essays/the-meaning-of-rights.md`.
2. Set `title`. Set `order` to the next number.
3. Put the text below the front matter.
4. Check that no two files in the folder have the same `order`.

**Reorder pages:** change the `order` numbers. Do not rename files.

**Add a picture:** put the file in `images/` with a lowercase, hyphenated name. Use `![Short description of the picture](/images/file-name.jpg)`. Always write a real description. Keep files under 500 KB. Resize large photos to 1200 pixels wide.

## Check your work

Before you finish, confirm each item:

- [ ] The author's body text is unchanged, unless the owner asked for a specific change.
- [ ] Every page still has `title`. Every essay and reading list item still has a unique `order`.
- [ ] No passwords, private contact details, or private documents were added.
- [ ] `CONTENT-CHANGES.md` has a new line for any content change.
- [ ] Links you added start with `/` (inside the site) or `https://` (outside the site).
- [ ] If you can run Jekyll: `jekyll build` finishes with no errors. See `guides/for-technical-helpers.md`.
- [ ] You told the owner what changed, and how to see it on the live site in 1 to 2 minutes.
