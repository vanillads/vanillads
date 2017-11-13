# mint

*[Jekyll](https://jekyllrb.com/) theme built with [foundation framework](http://foundation.zurb.com/)
and [Font Awesome framework](http://fontawesome.io/)*.

## Installation

The mint theme is built with Jekyll 3.5.1, Font Awesome framework 4.7.0,
Foundation framework 6.4.3.

Execute:

    $ bower install
    $ bundle install

## Contents At-A-Glance

Mint is a jekyll theme. It has all the necessary files and directories to have a
new Jekyll site up and running with zero-configuration.

### Layouts

Refers to files within the `_layouts` directory, that define the markup for your theme.

  - `default.html` &mdash; The base layout that lays the foundation for subsequent layouts. The derived layouts inject their contents into this file at the line that says ` {{ content }} ` and are linked to this file via [FrontMatter](https://jekyllrb.com/docs/frontmatter/) declaration `layout: default`.
  - `home.html` &mdash; The layout for your landing-page / home-page / index-page.
  - `page.html` &mdash; The layout for your documents that contain FrontMatter, but are not posts.
  - `post.html` &mdash; The layout for your posts.
  - `archive.html` &mdash; The layout for the page that contents your posts list.
  - `blog_by_category.html` &mdash; List posts by category layout.
  - `categories.html` &mdash; List all categories layout.
  - `contact.html` &mdash; Contact page layout.
  - `search.html` &mdash; Search page layout.

### Includes

Refers to snippets of code within the `_includes` directory that can be inserted in multiple layouts (and another include-file as well) within the same theme-gem.

  - `disqus_comments.html` &mdash; Code to markup disqus comment box.
  - `footer.html` &mdash; Defines the site's footer section.
  - `google-analytics.html` &mdash; Inserts Google Analytics module (active only in production environment).
  - `head.html` &mdash; Code-block that defines the `<head></head>` in *default* layout.
  - `header.html` &mdash; Defines the site's main header section. By default, pages with a defined `title` attribute will have links displayed here.
  - `post_meta` &mdash; Inserts post meta data (category, date, author).
  - `recent_posts` &mdash; Inserts recents posts links.

### Assets

Refers to various asset files within the `_assets` directory.
Contains the `main.scss`. This `main.scss` is what gets processed into the theme's main stylesheet `main.css` called by `_layouts/default.html` via `_includes/head.html`.

### Categories

Refers to files within the `_mint_categories` directory, that define the list of
categories of your website.

### Posts

Refers to files within the `_posts` directory. The `_posts` folder is where your
blog posts will live. Jekyll requires blog post files to be named according to
[the following format](https://jekyllrb.com/docs/posts/):

`YEAR-MONTH-DAY-title.MARKUP`

### Plugins

Mint comes with:
* [`jekyll-seo-tag`](https://github.com/jekyll/jekyll-seo-tag)
plugin preinstalled to make sure your website gets the most useful meta tags. See [usage](https://github.com/jekyll/jekyll-seo-tag#usage) to know how to set it up.
* [`jekyll-assets`](https://github.com/jekyll/jekyll-assets)
plugin preinstalled to create an asset pipeline.
* [jekyll-paginate-v2](https://github.com/sverrirs/jekyll-paginate-v2) plugin
preinstalled to display posts over multiple pages.

### Search

To build the search Mint comes with [lunr.js](https://lunrjs.com), a client side
full-text search engine. It’s a relatively small site so we can perform the
search entirely client side. If there were hundreds of blog posts, performing the
search client side may get slow and a backend search (using algolia search for
instance) may be a better option.

## Usage

### Customization

Edit the `_assets/css/_settings.scss` to modify the default styles of Foundation.
If there's something you can't customize with a variable, you can just write your
own CSS to add it in `_assets/css/main.scss`.

--

### Change the mailing list signup form
Change the mailing list signup form by specifying `site.signup_form_url`
in `_config.yml`.

### Change default date format

You can change the default date format by specifying `site.date_format`
in `_config.yml`.

```
# Mint date format
# refer to http://shopify.github.io/liquid/filters/date/ if you want to customize this:
  date_format: "%b %-d, %Y"
```

--

### Enabling comments (via Disqus)

Optionally, if you have a Disqus account, you can tell Jekyll to use it to show a comments section below each post.

To enable it, add the following lines to your Jekyll site:

```yaml
  disqus:
    shortname: my_disqus_shortname
```

You can find out more about Disqus' shortnames [here](https://help.disqus.com/customer/portal/articles/466208).

Comments are enabled by default and will only appear in production, i.e., `JEKYLL_ENV=production`

If you don't want to display comments for a particular post you can disable them by adding `comments: false` to that post's YAML Front Matter.

--

### Enabling Google Analytics

To enable Google Anaytics, add the following lines to your Jekyll site:

```yaml
  google_analytics: UA-NNNNNNNN-N
```

Google Analytics will only appear in production, i.e., `JEKYLL_ENV=production`

## Continuous Deployment
You can use [Netlify](https://www.netlify.com/) to host your site. Netlify will
run your build command and deploy the result whenever you push to your git repo.
The build command:
`bower install & jekyll build`
