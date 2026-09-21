# Put the site online

Follow these steps once, to publish the site on GitHub Pages and point the domain to it. Use the same steps to move the site to a new GitHub organization.

In the steps, `ORG` means the name of your GitHub organization.

## 1. Create a GitHub account and organization

1. Create a free account at https://github.com (skip this if you have one). Turn on two-factor authentication.
2. Click your profile picture > **Your organizations** > **New organization**. Choose the **Free** plan.
3. Name the organization. A name based on the site (for example `fundamentals-of-liberty`) makes the organization the unit you hand off. A family name also works if you expect more family projects. You can move the repository between organizations later, and GitHub redirects the old links.
4. Add a second person as an **Owner** as soon as possible.

## 2. Create the repository

1. In the organization, click **New repository**.
2. Name: `fundamentalsofliberty`. Visibility: **Public**. Do not add a README.
3. Upload the files:
   - **In the browser:** click **uploading an existing file**. Drag in every file and folder from this site folder. Include the files that start with a dot (`.pages.yml`, `.gitignore`). Commit.
   - **With git (pwsh):**

     ```powershell
     cd path\to\fundamentalsofliberty
     git init -b main
     git add .
     git commit -m "Restore Fundamentals of Liberty"
     gh repo create ORG/fundamentalsofliberty --public --source . --push
     ```

     This needs [Git](https://git-scm.com) and the [GitHub CLI](https://cli.github.com) (`gh`).

## 3. Turn on GitHub Pages

1. In the repository, open **Settings > Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**. Branch: `main`. Folder: `/ (root)`. Click **Save**.
3. Wait 1 to 2 minutes. The **Actions** tab shows a green check when the site is built.

## 4. Add the custom domain in GitHub

1. The repository already has a file named `CNAME` that contains `fundamentalsofliberty.com`. Keep it.
2. In **Settings > Pages**, confirm that **Custom domain** shows `fundamentalsofliberty.com`. If it is empty, type it and click **Save**.
3. Until the DNS change in step 6 is done, the site will not load. This is normal.

## 5. Disconnect GoDaddy Website Builder

The domain currently shows a free GoDaddy Website Builder "coming soon" page. That page can keep its own DNS records.

1. Sign in to GoDaddy. Open the Website Builder site for the domain.
2. Unpublish or delete the site, or disconnect the domain from it.
3. Make sure domain forwarding is off for the domain.

## 6. Change the DNS records at GoDaddy

1. In GoDaddy, open **My Products**. Next to the domain, open **DNS**.
2. Delete the existing A and AAAA records for `@`, and the CNAME record for `www`.
3. Add the records in the table in [STEWARDSHIP.md](../STEWARDSHIP.md), section "DNS settings at GoDaddy."
4. Wait. Most changes work in under an hour. Some take up to 24 hours.
5. In GitHub **Settings > Pages**, wait for the DNS check to pass. Then tick **Enforce HTTPS**.

## 7. Verify the domain for the organization

This stops anyone else on GitHub from using the domain.

1. Open the organization's **Settings > Pages** (organization settings, not repository settings).
2. Click **Add a domain**. Type `fundamentalsofliberty.com`.
3. GitHub shows a TXT record. Add it at GoDaddy DNS.
4. Return to GitHub and click **Verify**.

## 8. Check the live site

- [ ] https://fundamentalsofliberty.com loads with a lock icon.
- [ ] https://www.fundamentalsofliberty.com goes to the same site.
- [ ] Every menu link works.
- [ ] An old address works: https://fundamentalsofliberty.com/?page_id=467 opens "Preamble to the Constitution."
- [ ] Update the Accounts table in STEWARDSHIP.md.
