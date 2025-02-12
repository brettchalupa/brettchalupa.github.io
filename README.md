# www.brettchalupa.com

The website of Brett Chalupa, built with [Jekyll](http://jekyllrb.com).

## Developing

1. Clone the repository
2. Install the dependencies - `bundle install`
3. Start up the Jekyll server and show drafts - `just up`
4. Make changes

## Hosting & Deploying

The site is hosted and served via GitHub Pages. New changes get deployed
by pushing to `master` branch.

## Authoring Content

[jekyll-compose](https://github.com/jekyll/jekyll-compose) can be used
to create content more easily, with commands like:

- `bundle exec jekyll post "My New Post"`
- `bundle exec jekyll draft "My New Draft"`

## Plugins

The site makes use of plugins that GitHub Pages supports with Jekyll.
See the `gems:` section in `_config.yml` for the full list.

- [jekyll-seo-tag](https://github.com/jekyll/jekyll-seo-tag) - easy
  SEO-goodness in the site
- jemoji - using emojis in the content :sun_with_face:
- jekyll-sitemap - generating a sitemap
- jekyll-feed - generating an Atom feed

## License

All content and code are copyright (c) 2011-2021 Brett Chalupa

[See the License page](http://www.brettchalupa.com/license) for the full
details on how the code and content are licensed.
