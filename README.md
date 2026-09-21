# Fundamentals of Liberty: start here

This folder is the complete website **fundamentalsofliberty.com**.

- The original site was online from 2011 to 2018. It never named its author. Whether to name him now is a family decision (see STEWARDSHIP.md, to-do 6).
- His family restored it in 2026 from archived copies of the original pages.
- You do not need to be technical to look after it. This file tells you how.

## The three rules

1. **The author's words stay as he wrote them.** Do not fix his spelling, punctuation, or opinions.
2. **Family additions go in a "family note."** A family note shows in a shaded box, so readers always know who wrote what. See [guides/editing-content.md](guides/editing-content.md).
3. **Keep the domain name paid.** A forgotten renewal is the most likely way to lose the site. See [STEWARDSHIP.md](STEWARDSHIP.md).

## Where things are

| Folder or file | What it holds | Safe for you to edit? |
|---|---|---|
| `index.md` | The home page text | Yes |
| `about.md` | The About page | Yes |
| `essays/` | One file per essay | Yes |
| `reading-list/` | One file per reading list item | Yes |
| `images/` | Pictures used on the pages | Yes (add new pictures here) |
| `_config.yml` | Site name, top menu, footer line | The top part only |
| `STEWARDSHIP.md` | Accounts, renewals, and what to do if the site breaks | Yes (keep it current) |
| `CONTENT-CHANGES.md` | A log of every change to the site's text | Yes (add a line for each change) |
| `guides/` | Step-by-step instructions | Yes |
| `AGENTS.md`, `CLAUDE.md` | Rules for AI helpers | Only if the rules change |
| `_layouts/`, `_includes/`, `assets/` | The design and page templates | No, not without help |
| `_data/`, `404.html`, `Gemfile`, `.pages.yml` | Technical files | No, not without help |

## Common tasks

**Fix a typo in a family note, or change the footer line**

1. Go to the repository on github.com and sign in.
2. Open the file (for example, `about.md` or `_config.yml`).
3. Click the pencil icon ("Edit this file").
4. Make the change.
5. Click **Commit changes**. Write a short description, for example "Fix typo in About note."
6. Wait 1 to 2 minutes. Then reload the website.

**Other tasks**

- Add a family note, add an essay, add a picture, or reorder pages: [guides/editing-content.md](guides/editing-content.md)
- Use a form-based editor instead of editing files: [guides/pages-cms.md](guides/pages-cms.md)
- Put the site online for the first time, or move it: [guides/go-live.md](guides/go-live.md)
- The site is down: [STEWARDSHIP.md](STEWARDSHIP.md), section "If the site is down"
- Hand the site to the next person: [STEWARDSHIP.md](STEWARDSHIP.md), section "Hand off the site"

## Get help from an AI assistant

AI assistants (for example, Claude) can do most tasks for you. Copy this message and change the last line:

```
I look after the website fundamentalsofliberty.com. It is a GitHub repository
that GitHub Pages publishes. I am not technical.
First, read README.md and AGENTS.md in the repository. Follow AGENTS.md exactly.
Explain each step in plain language before you do it.
My task: [describe what you want, for example "add a family note to the About page"]
```

- If the assistant can connect to GitHub, it can make the change for you.
- If it cannot connect, paste the contents of the file into the chat. Ask for the complete new file. Then paste it back on github.com.

## Words you will see

- **Repository (repo):** the folder on GitHub that holds every file of the site.
- **Commit:** a saved change. GitHub keeps every commit, so you can see and undo old changes.
- **GitHub Pages:** the free GitHub service that turns this repository into the live website.
- **Markdown:** the simple text format of the page files. `**bold**` shows as **bold**.
- **Front matter:** the lines between the two `---` lines at the top of a page file. They hold the title and settings.
- **Domain:** the address `fundamentalsofliberty.com`. It is rented every year or two from GoDaddy.
- **DNS:** the settings at GoDaddy that connect the domain to GitHub Pages.
