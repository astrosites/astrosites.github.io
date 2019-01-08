---
layout: page
title: Building Options
nav-order: 5
---

There are several different paths you can take when building a GitHub pages ready website, however there are three popular options as of right now.

# Build it yourself

It's not uncommon for those with a little webdev experience to simply build your own website. However, in 2019, few people are building pages from scratch! Building a page yourself still doesn't mean writing a bunch of your own code!

Right now, the most popular method for building your own webpage is to use Bootstrap components. [Bootstrap](https://getbootstrap.com/) is a collection of HTML, CSS, and JavaScript **components** which you can choose and pick for your own website. For example, if you wish to have something on your website that produces a slideshow of pictures, you can simply grab Bootstrap's [Carousel component](https://getbootstrap.com/docs/4.1/components/carousel/) and integrate it into your own page. 

Web development has a **huge** community around it and there is an enormous amount of material and code out there already that already implements what you want to implement! So do a google search before you start writing anything yourself.

If you are interested in going this route, one option is use [Gulp](https://gulpjs.com/) to manage and build their site as they edit the raw components of it.

# HTML5 Templates

Many people choose to use simple website templates that look *really* nice and build a small website out of those. There are tons of **free**, **easy to customize**, and **beautiful** templates already out there for you to download, customize, and make into your own webpage. For a list of free templates, check out:
- [HTML5 UP](https://html5up.net/)
- [Templated](https://templated.co/)
- [Themewagon](https://themewagon.com/theme_tag/free/)

# Static Site Generators

Static site generators are a programmatic way to generate a website. You can find information about many of the popular static site generators at [staticgen.com](https://www.staticgen.com/). The website generators you'll find here are written in several different lanaguages, are built for different audiences, and fulfill different needs. Below, we discuss two static site generators which are particularly relevant to hosting with GitHub and those familiar with Python.

## Jekyll

**Themes**: [https://jekyllthemes.io/](https://jekyllthemes.io/)

**Guide**: [https://www.taniarascia.com/make-a-static-website-with-jekyll/](https://www.taniarascia.com/make-a-static-website-with-jekyll/)

[Jekyll](https://jekyllrb.com/) is a static website and blog generator built in the programming language Ruby. GitHub Pages is actually set up to natively work with Jekyll. Instead of pushing raw HTML to GitHub for them to serve, you can instead push your Jekyll files and configuration and GitHub will use Jekyll to build your site for you. Since GitHub officially uses Jekyll, it reamins a very popular option for building your own website or blog with GitHub as your hosting solution.

Building sites with Jekyll isn't really any harder than building one using HTML templates. When building a site with Jekyll, you simply edit a few text files (really **Markdown** files) which then get pushed through a bunch of templated HTML and Jekyll's site generation software to build a static webpage for you. In simple terms, you specify the raw content on your page, you choose a [Jekyll theme](https://jekyllthemes.io/) which determines the layout of your content on a webpage, and Jekyll builds the site for you using your content and the theme. The beauty of this set up is that your content is separate from your theme. If you want to change how your website looks, you don't need to make many edits to any of the files you wrote yourself, you simply swap in a new theme. 

If you are interested in migrating a blog from WordPress to Jekyll, check out [this tool on GitHub](https://github.com/benbalter/wordpress-to-jekyll-exporter).

## Pelican

**Themes**: [http://www.pelicanthemes.com/](http://www.pelicanthemes.com/)

**Guide**: [http://nafiulis.me/making-a-static-blog-with-pelican.html](http://nafiulis.me/making-a-static-blog-with-pelican.html)

[Pelican](https://blog.getpelican.com/) is esentially Jekyll, but written in Python. Since the astronomy community is so integreated with Python, some may find it easier to use and customize Pelican. However, since most website building with either Jekyll or Pelican comes down to writing your own content and letting the theme determine the layout, one ends up not needing to customize the underlying website builder very often. Pelican has many [themes](http://www.pelicanthemes.com/) that you can choose from for your site, however the selection of themes is a bit more limited than the for Jekyll themes, since Pelican has a smaller userbase.

Also, since Pelican is not officially supported by GitHub pages, you cannot simply push your Pelican files to GitHub and have GitHub build your site for you. This isn't a big concern however, since you can build your site using Pelican on your own computer and then push the generated static site to GitHub (as we have done with the HTML templates).

# Other options

## Sphinx

[Sphinx](http://www.sphinx-doc.org/en/master/) is a documentation generator built in Python. If you are interested in creating and publishing documentation for a project or a code base online, then Sphinx is probably your best bet. 