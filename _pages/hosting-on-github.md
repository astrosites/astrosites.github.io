---
layout: page
title: Hosting on GitHub
nav-order: 2
---

GitHub Pages makes it easy for you to **easily** and **freely** share a *static* webpage with the world. Static webpages are exactly what they sound like: their content is mostly static as a user interacts with it. In practice, this just means that your webpage does not talk to any servers as a user browses the page. While this does limit the functionality of your site (you won't be making a YouTube or Twitter clone on GitHub), hosting a static site means your site will always be **secure**, **quick to load**, and **responsive**. This is in direct contrast to dynamic sites developed with, e.g. Wordpress, which are plagued by security issues and can get very slugish as your webpage gets larger and the number of users accesssing your site increases.

Static webpages are **simple**, **easy**, and **free**, so they are one of the preferred ways to make a site in 2018.

# Creating a GitHub Pages Repository

**Guide**: [https://pages.github.com/](https://pages.github.com/)

### Workflow Specific to This Tutorial

1. Fork the AstroSites template repository to your personal GitHub by going to `https://github.com/astrosites/template --> Fork [found in upper right-hand corner]`.

2. Rename the AstroSites template repository to `<your_username>.github.io` by going to `https://github.com/<your_username>/template -> Settings`. The repository **MUST** be called this, otherwise GitHub won't recognize that you are trying to use GitHub pages.

3. Navigate to your newly created repository and click "Settings" and scroll to "GitHub Pages". Ensure that your repository has GitHub Pages enabled and that `master branch` is chosen under "Source".

4. Clone the newly-renamed repository to your personal computer by going to a terminal and typing `git clone https://github.com/<your_username>/<your_username>.github.io`.

5. Edit the file 'index.html' within this repository to include your personal information.

6. When finished editing, do the following commands:
   - `git add -A`
     	  
	 **Note:** The flag `-A` adds all the files in your directory. If you only want to push certain files, do `git add <file_name>`.
   
   - `git commit -m "No Firelord Ozai, you're not wearing any pants!"`
   - `git push`

7. Return to `https://github.com/<your_username>/<your_username>.github.io` to view your new commits.

8. Visit the website `<your_username>.github.io` to see the changes in your website.

### General Workflow

1. Make a new repository by going to `https://github.com/<your_username> -> Repositories -> New` where `<your_username>` is replaced with your GitHub username.

2. Under "reposity name", put `<your_username>.github.io`. The repository **MUST** be called this, otherwise GitHub won't recognize that you are trying to use GitHub pages. Initialize the repository with a `README` file.

3. Navigate to your newly created repository and click "Settings" and scroll to "GitHub Pages". Ensure that your repository has GitHub Pages enabled and that `master branch` is chosen under "Source".

4. Create a new file `index.html` in your repository. This will act as your main landing page (when someone types in the url `http://<your_username>.github.io`, GitHub will serve up the file `index.html`).


# Using a custom domain name

## Purchasing a domain name

**Guide**: [https://help.github.com/articles/using-a-custom-domain-with-github-pages/](https://help.github.com/articles/using-a-custom-domain-with-github-pages/)

1. Go to [domains.google.com](domains.google.com) and purchase whatever domain you want ($12 / year usually).
2. Create a file called CNAME in the main directory of your github repo. Add the lines `<your_domain>` and `www.<your_domain>` (e.g. `example.com` and `www.example.com`).
3. Open up the DNS settings for your site on [https://domains.google.com/registrar](https://domains.google.com/registrar).
4. Under "Name servers", click "Use the Google Domains name servers".
5. Under "Custom resource records", create the following records:
    - @, A, 1h, 192.30.252.153, (click the + button) 192.30.252.154
    - www, CNAME, 1h, `https://<your_username>.github.io/.<your_domain_name>.`
    These records tell Google's DNS to point to GitHub to find your page.

## Securing your site with HTTPS

**Guide**: [https://gist.github.com/cvan/8630f847f579f90e0c014dc5199c337b](https://gist.github.com/cvan/8630f847f579f90e0c014dc5199c337b)

By default, github pages doesn't support access to your site with HTTPS with a custom domain. This means that whenever someone clicks on your site after a google search, they'll see a warning saying your site might be trying to steal your data. We don't want this!

1. Set up a free cloudflare account here: [https://www.cloudflare.com/](https://www.cloudflare.com/) and add your website to your account.
2. Under the DNS settings for your site on Cloudflare, go to "DNS Records".
3. Set up the following DNS Records:
    - A, `<your_domain_name>`, 192.30.252.153, Automatic TTL
    - A, `<your_domain_name>`, 192.30.252.154, Automatic TTL
    - CNAME, www, `<your_domain_name>`
    
    Note: `<your_domain_name>` should be like `example.com`, **NOT** `www.example.com` nor `http://example.com`

4. Scroll down to Cloudflare Nameservers and take note of the two nameservers provided to you.
    - For me they are lorna.ns.cloudflare.com and phil.ns.cloudflare.com
5. Under the Crypto settings for your site on Cloudflare, scroll to "SSL" and ensure that Full SSL encryption is being used.
6. Scroll to "Always use HTTPS" and flick the switch to "On".
7. Go back to the DNS settings at [https://domains.google.com/registrar](https://domains.google.com/registrar) and go to "Name servers".
8. Click "Use custom name servers" and input the two name servers provided to you by Cloudflare.
