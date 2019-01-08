---
layout: page
title: Hosting on GitHub
nav-order: 3
hide: true
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
