---
layout: post
title: "Welcome to Tessera"
date: 2025-05-17
categories: blog
image: /assets/img/tessera.webp
---

Tessera is a Jekyll theme designed with content creators in mind, but like any other Jekyll theme, it can be used by anyone.

Tessera features three main components: two side panels and a central content area. The theme is highly modular, allowing you to easily customize any component by overriding the `_includes`.

## Installation

Add this line to your Jekyll site's `Gemfile`:

```ruby
gem "tessera-jekyll-theme"
```

Then add this line to your Jekyll site's `_config.yml`:

```yaml
theme: tessera-jekyll-theme
```

And then execute:

```
$ bundle
```

Or install it manually with:

```
$ gem install tessera-jekyll-theme
```
### GitHub Pages
Instead of doing the above steps, define this in your `_config.yml`, removing also `theme`:

```
# theme: something # remove this
remote_theme: itszariep/Tessera # add this
```


## Dependencies
Tessera needs the following Jekyll plugins to function properly:

  - jekyll-paginate (Pagination in main page)
  - jekyll-archives (See posts matching category)
  
  
## Post-install setup
### Search
Search needs /`search.json`:

```
{% raw %}
---
layout: null
---
[
  {% for post in site.posts %}
    {
      "title": "{{ post.title | escape }}",
      "url": "{{ site.baseurl }}{{ post.url }}",
      "date": "{{ post.date | date: "%B %-d, %Y" }}",
      "content": "{{ post.content | strip_html | strip_newlines | escape }}"
    }{% unless forloop.last %},{% endunless %}
  {% endfor %}
]
{% endraw %}
```

### Pagination
Pagination needs setup on `_config.yml`:

```
paginate: 9
paginate_path: "/page:num/"
```

### Social links
Like any other Jekyll theme, you need to setup your social links on `_config.yml`:

```
social_links:
  - name: Twitter
    url: https://twitter.com/yourprofile
    icon: twitter
  - name: GitHub
    url: https://github.com/yourprofile
    icon: github
  - name: LinkedIn
    url: https://linkedin.com/in/yourprofile
    icon: linkedin
```


## Usage

To start customizing Tessera, copy any of the `_includes` components you'd like to modify. You’ll probably want to copy most or all of them:

* `toppane.html`: Header
* `leftpane.html`: Left side of the page
* `postgrid.html`: Post grid of the main page
* `pagination-controls.html`: Pagination controls for the main page
* `postcontent.html`: Content of a post
* `userbox.html`: User box displayed below the post content
* `comments.html`: Optional (currently unimplemented) comments section; by default, an example using Utterances is commented out. You can integrate any custom comment system via JavaScript.
* `rightpane.html`: Right side of the page
* `searchbar.html`: Search bar (requires JavaScript)
* `bottompane.html`: Footer for all pages

## Contributing

Bug reports and pull requests are welcome on GitHub at [https://github.com/itszariep/tessera](https://github.com/itszariep/tessera). This project aims to be a safe and welcoming space for collaboration. All contributors are expected to adhere to the [Contributor Covenant](https://www.contributor-covenant.org/) code of conduct.

## Development

To set up your environment for theme development, run:

```
$ bundle install
```

Your theme is set up just like a regular Jekyll site! To test it, run:

```
$ bundle exec jekyll serve
```

Then open your browser at [http://localhost:4000](http://localhost:4000). This starts a Jekyll server using your theme. Add pages, documents, data, etc., as usual to test your theme's content. As you modify the theme or its content, your site will automatically regenerate. Refresh the browser to see the changes.

When your theme is released, only the files in `_layouts`, `_includes`, `_sass`, and `assets` that are tracked by Git will be bundled.
To add a custom directory to your theme gem, update the regular expression in `tessera.gemspec` accordingly.

## License

This theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).