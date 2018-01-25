Solar Theme for Jekyll
======================

A stylish theme for [Jekyll](http://jekyllrb.com/) blogs, based on the [Solarized](http://ethanschoonover.com/solarized) color palette.

![Screenshot](http://i.imgur.com/UnnRhkt.png)


Features
-------

* **Two color schemes** — One for Solarized Dark and one for Solarized Light. Change import in `assets/css/styles.css` from `@import "customization/colors-light";` to `@import "customization/colors-dark";` to switch theme.
* **Linkblog support** — Solar will turn your post title into an external link if you add `external-url: http://example.org` to a post's YAML front matter.
* **Responsive Design** — We use grid system from `bootstrap v4` to implement responsive design.


Installation
--------------

There are two ways to use Solar. You can either clone-and-go, copying the repository and tweaking the contents to taste, or you can cherry-pick the files you want and integrate them into an existing Jekyll instance. 

If you're starting a new blog, you want to clone-and-go. Just `git clone https://github.com/redwallhp/solar-theme-jekyll.git`, make any changes you want to the template, pages or `_config.yml` and start blogging with Jekyll. Easy.

If you're wanting to replace the theme of an existing Jekyll blog, either option should work. If you want to replace files individually, the files and directories you want to make sure to copy are:

1. `_layouts`
2. `archives`
3. `assets`
4. `feed.xml`
5. `index.xml`
6. `_sass`

You'll also want to compare Solar's `_config.yml` with your own, making any appropriate changes.


Demo
-------

You can see a demo of Solar [right here on GitHub Pages.](https://yetanotheric.github.io/)


License
---------

GPLv2 or higher
