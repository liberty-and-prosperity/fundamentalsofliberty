# Editing content

This guide shows how to change pages on github.com. You need a GitHub account with access to the repository.

Every change is saved forever in the history. You cannot break anything permanently.

## What a page file looks like

```markdown
---
title: "The Purpose of Government"
order: 2
family_note: >-
  An optional note from the family goes here.
---

Q: What is the distinguishing feature of government?

A: Government has a legal monopoly on the use of coercive violence.
```

- The part between the two `---` lines is the **front matter**.
  - `title`: the page title. Keep the quotation marks.
  - `order`: the position in the list. `1` is first. Only essays and reading list items have it.
  - `family_note`: optional. See below.
- Everything below the second `---` is **the author's text**. Do not change it.

## Add or change a family note

A family note shows in a shaded box labeled "Note from the family." Use it to add context, a working link, or a correction, without touching the author's words.

1. Open the page file on github.com. Click the pencil icon.
2. Add these lines inside the front matter, just above the second `---`:

   ```yaml
   family_note: >-
     Write the note here. Every line of the note starts with two spaces.
   ```

3. Click **Commit changes**.
4. Add a line to `CONTENT-CHANGES.md`.

## Add a new essay or reading list item

1. Open the `essays` folder (or `reading-list`).
2. Click **Add file > Create new file**.
3. Name the file with lowercase words and hyphens, ending in `.md`. Example: `the-meaning-of-rights.md`. The name becomes the web address.
4. Type the front matter. Use the next free `order` number:

   ```markdown
   ---
   title: "The Meaning of Rights"
   order: 6
   ---
   ```

5. Type or paste the text below the front matter. Leave a blank line between paragraphs.
6. Click **Commit changes**.

The new page appears automatically in the menus, the home page table of contents, and the previous and next links.

## Change the order of pages

Change the `order` numbers in the page files. Do not rename the files. Renaming a file changes its web address and breaks links from other websites.

## Add a picture

1. Resize the picture to 1200 pixels wide or smaller. Name it with lowercase words and hyphens, for example `liberty-bell.jpg`.
2. Open the `images` folder. Click **Add file > Upload files**. Upload the picture. Click **Commit changes**.
3. In the page file, add this on its own line, with a blank line above and below:

   ```markdown
   ![A short description of the picture](/images/liberty-bell.jpg)
   ```

   The description helps readers who cannot see the picture. Always write one.

## Markdown in one minute

| You type | Readers see |
|---|---|
| `**bold**` | **bold** |
| `*italic*` | *italic* |
| `[Link text](https://example.com)` | [Link text](https://example.com) |
| `[Essays](/essays/)` | a link to a page on this site |
| `- item` on each line | a bulleted list |
| `1. item` on each line | a numbered list |
| a blank line | a new paragraph |

## Undo a change

1. Open the file on github.com. Click **History**.
2. Open the change before the mistake. Copy the old text.
3. Edit the file, paste the old text, and commit.

Or ask an AI helper to undo it (see README.md).

## Change the menu or footer

Open `_config.yml`. Edit the words in quotes near the top: `footer_text` and the `nav` list. Do not change the part below "TECHNICAL SETTINGS."
