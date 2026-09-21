# Optional: edit with Pages CMS

[Pages CMS](https://pagescms.org) is a free, open-source editor for websites stored on GitHub. It shows forms and a word-processor style editor instead of raw files. It saves your changes back to this repository.

You do not need Pages CMS. Editing on github.com works fine. Use Pages CMS if a future steward prefers forms.

## What is already set up

The file `.pages.yml` in the repository already describes this site for Pages CMS:

- **Essays** and **Reading List:** a list of pages, sorted by position. Each page has Title, Position in the list, Note from the family, and Text.
- **Other pages:** Home, About, the two list pages, and Site settings.
- **Media:** uploads go to the `images` folder.

`.pages.yml` does nothing until someone connects Pages CMS. It does not affect the website.

## Connect Pages CMS

1. Go to https://app.pagescms.org.
2. Sign in with GitHub.
3. When Pages CMS asks, install its GitHub App on the organization. Give it access to the `fundamentalsofliberty` repository only.
4. Open the repository in Pages CMS. You see Essays, Reading List, Other pages, and Media.

These steps describe the hosted version at the time of writing. If the screens look different, follow the current instructions at https://pagescms.org/docs.

## Use it safely

- Put family additions in **Note from the family**. Do not edit the author's **Text**.
- The editor may rewrite some Markdown formatting when you save a page, even if you only change the family note. After saving, open the page's **History** on github.com and check that the author's words did not change.
- Every save becomes a commit. The live site updates in 1 to 2 minutes.
- Add a line to `CONTENT-CHANGES.md` for each content change.

## Disconnect Pages CMS

On github.com, open the organization's **Settings > GitHub Apps**. Uninstall the Pages CMS app. The website keeps working.

## If you change the page format

If a technical helper adds a new front matter field to the pages, they must add it to `.pages.yml` too. Otherwise Pages CMS may remove that field when someone saves.
