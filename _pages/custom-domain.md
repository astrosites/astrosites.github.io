---
layout: page
title: Custom Domain Names
nav-order: 4
---

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
    - Some examples are lorna.ns.cloudflare.com and phil.ns.cloudflare.com.


5. Under the Crypto settings for your site on Cloudflare, scroll to "SSL" and ensure that Full SSL encryption is being used.

6. Scroll to "Always use HTTPS" and flick the switch to "On".

7. Go back to the DNS settings at [https://domains.google.com/registrar](https://domains.google.com/registrar) and go to "Name servers".

8. Click "Use custom name servers" and input the two name servers provided to you by Cloudflare.
