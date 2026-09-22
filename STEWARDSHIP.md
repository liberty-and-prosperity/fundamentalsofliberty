# Stewardship: accounts, renewals, and hand-offs

A small website usually dies for one of three reasons: the domain expires, nobody can log in, or a payment card expires. This file prevents all three.

> **This repository is public.** Never write passwords, account numbers, or private contact details here. Keep them in the family password manager.

## Who looks after the site

| Role | Person | Since |
|---|---|---|
| Current steward | _(fill in)_ | _(fill in)_ |
| Backup steward | _(fill in)_ | _(fill in)_ |

## Accounts

| What | Where | Account owner | Cost | Notes |
|---|---|---|---|---|
| Domain `fundamentalsofliberty.com` | GoDaddy | The author's original GoDaddy account (see to-do 2) | See GoDaddy | Auto-renew is on. Renews every 2 years, in December. |
| Website hosting | GitHub Pages | GitHub organization `liberty-and-prosperity` | Free | Publishes this repository. |
| This repository | GitHub | Same organization | Free | Must stay public for free GitHub Pages. |
| Private family archive | Shared family OneDrive folder | _(fill in)_ | Free | The author's Word documents and notes, plus the raw Wayback Machine download of the old site (`fundamentalsofliberty-archive.zip`). Contains old passwords. Keep it private, and outside GitHub. |
| Optional editor | Pages CMS | Signs in with GitHub | Free | Not required. See `guides/pages-cms.md`. |

## Every year (in November, before the December renewal)

- [ ] Sign in to GoDaddy. Confirm the renewal date and that auto-renew is on.
- [ ] Confirm the payment card on file is valid.
- [ ] Confirm that renewal emails reach at least 2 people (see to-do 1).
- [ ] Confirm that at least 2 people are owners of the GitHub organization.
- [ ] Open the website. Click through the menu.
- [ ] Update the "Who looks after the site" table if anything changed.

## DNS settings at GoDaddy

These records connect the domain to GitHub Pages. They are correct as of 2026. If GitHub changes them, GitHub's help page "Managing a custom domain for your GitHub Pages site" has the current values.

| Type | Name | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | liberty-and-prosperity.github.io |
| TXT | `_github-pages-challenge-liberty-and-prosperity` | _(value from GitHub, see guides/go-live.md)_ |

Remove any other A, AAAA, or CNAME records for `@` and `www`. Do not add domain forwarding.

## If the site is down

Check these in order. Stop when you find the problem.

1. **Is the domain expired?** Sign in to GoDaddy. Look at the domain status. If it expired, renew it right away. GoDaddy keeps an expired domain for a short grace period only.
2. **Did the DNS settings change?** Compare GoDaddy's DNS page with the table above. Fix any difference. Changes can take up to a few hours.
3. **Is GitHub Pages working?** Check https://www.githubstatus.com. In the repository, open **Settings > Pages**. Look for an error message.
4. **Did a recent change break the build?** In the repository, open the **Actions** tab. A red X means the last change did not publish. Open it to read the error. Undo the last change, or ask an AI helper (see README.md).
5. **Still stuck?** Ask an AI helper with the message in README.md. Describe what you see.

## Hand off the site

Do these steps together with the next steward.

1. In the GitHub organization, add the new steward as an **Owner**.
2. At GoDaddy, move the domain to an account the new steward controls, or add them to the current one.
3. Update the renewal email and payment card.
4. Give the new steward access to the private family archive.
5. Share any passwords through the family password manager, not by email.
6. Update the "Who looks after the site" table above. Commit the change.
7. The new steward reads README.md and makes one small test change.

## Open to-do list

1. **Send renewal emails to 2 people.** GoDaddy sends renewal notices to the account's email address. Use an address that forwards to 2 people. **Do not use an address at fundamentalsofliberty.com.** If the domain expires, that address stops working exactly when you need it.
2. **Move the domain to the steward's own GoDaddy account.** Not urgent while auto-renew works and you can sign in. Do it before a hand-off, or if the account ever asks for identity checks.
3. **Verify the domain for the GitHub organization.** This stops other GitHub users from taking over the domain. See guides/go-live.md, step 7.
4. **Check outside links once a year.** On 2026-09-21 every outside link was checked, including the 7 Amazon book links, and all of them work. Four links were repaired on 2026-09-16 (see CONTENT-CHANGES.md). Rule for a broken link: change only the link address to a page that serves the original purpose, keep the author's words, and log it. If no replacement exists, add a family note.
5. **Review the pictures.** Most photos on the essays came from the internet in 2010, and their owners are unknown. The wanted poster on "The Purpose of Government" shows a real person's name and face. Decide whether to keep it or replace it with a similar public-domain picture, and log the decision in CONTENT-CHANGES.md.
6. **Decide whether to name the author.** The original site never named him. Its footer said only "Fundamentals of Liberty" and "Proudly powered by WordPress." If the family decides to name him: change `footer_text` in `_config.yml`, add a family note on the About page if you want, update AGENTS.md rule 8, and log the decision in CONTENT-CHANGES.md.
7. **Complete the private family archive.** Add `fundamentalsofliberty-archive.zip` (the raw Wayback Machine download) to the family OneDrive folder next to the Word documents. Confirm that at least 2 family members can open the folder. The Wayback Machine is not guaranteed to keep its copies forever, so this zip is the family's own backup of the original site, including the full Five Books page.
8. **Save a copy of the "Choose Liberty" video.** The site's own YouTube channel ("LibertyFundamentals") and Vimeo account ("Fundamentals of Liberty") host it. Inactive accounts can be deleted. Download a copy to the family OneDrive folder, if the account settings allow it.
