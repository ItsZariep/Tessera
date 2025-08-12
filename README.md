# Tessera

Tessera is a Jekyll theme designed with content creators in mind, but like any other Jekyll theme, it can be used by anyone.

[Hugo variant](https://codeberg.org/ItsZariep/Tessera)

Tessera features three main components: two side panels and a central content area. The theme is highly modular, allowing you to easily customize any component by overriding the `_includes`.

## Example:

See [Tessera example page](https://itszariep.github.io/Tessera) for a vanilla example, or [My blog](https://itszariep.github.io/) (in Spanish) for a version with modifications and a real use case.

You can also look at [Webpages created with Tessera](https://github.com/ItsZariep/Tessera/wiki/Webpages-created-with-Tessera) to see more functional websites

## Installation

> [!WARNING]
> Do not fork or clone this branch! It is not intended for use. Please fork [gh-pages](https://github.com/ItsZariep/Tessera/tree/gh-pages) branch instead:
> 1. **Uncheck** the “Copy the `main` branch only” option during the fork process.
> 2. In your forked repository:
>    - Delete the `main` branch.
>    - Rename the `gh-pages` branch to `main`.

---

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

### Choosing Posts or Chapters

Post are useful for blogs or content where date is important, Chapters is useful for books/folders where date is not important and sections are necessary.

In your index page define `indextype: chapters` or `indextype: posts`:

```
---
layout: home
title: Home
paginate: 9
indextype: posts
---

> [!NOTE]
> You can have both indexes as long both pages have `home` layout and a proper indextype

```

#### Chapters

to enable Chapters, you need to set:

```
collections:
  chapters:
    output: true
    permalink: /:name/
```

After that, on your chapters sites you need to set `section` and `order`:

```
section: Web
order: 1
```

### Search
Search needs /`search.json`:

```
---
layout: null
---
[
	{% for post in site.posts %}
		{
			"title": "{{ post.title | escape }}",
			"url": "{{ site.baseurl }}{{ post.url }}",
			"date": "{{ post.date | date: "%B %-d, %Y" }}",
			"content": "{{ post.content | strip_html | strip_newlines | escape }}",
			"tags": "{{ post.tags }}"
		}{% unless forloop.last %},{% endunless %}
	{% endfor %}
]
```

### Social Media Preview on non-post pages
set this on your `_config.yml`:
```
defaults:
  -
    scope:
      path: ""
      type: "pages"
    values:
      image: /preview.jpg
```

> Image need to be always /preview.jpg


## Authors

1.  Optionally set default author in `_.config.yml`:

```
defaults:
  - 
    scope:
      path: ""
      type: "pages"
    values:
      image: /preview.jpg
  -
    scope:
      path: ""
      type: "posts"
    values:
      author: "Tessera"
      image: /preview.jpg

```

2. Create `assets/img/authors/[Author Name].webp`
3. Create `about/[Author Name].md`
4. Create `_includes/authors.html and set your data`:

```
{% case include.author %}
	{% when "[YOUR NAME]" %}
		Cool Description
	{% when "Tessera" %}
		Cool Description
	{% else %}
		Unknown Author
{% endcase %}
```

> You can add multiple authors, for example with "Tessera", files would be `assets/img/authors/Tessera.webp` and `about/Tessera.md`

### Pagination
Pagination needs setup on two files:

on `_config.yml`:

```
paginate: 9
paginate_path: "/page:num/"
```

on `index.html`

```
---
layout: home
title: [Your index title]
paginate: 9
---
```

> 9 is the number of post per section, you can change it to have more o less post on grid per section


### Archives (Categories)
Archives needs setup on `_config.yml`:

```
jekyll-archives:
  enabled:
    - categories
  layout: archive
  permalinks:
    category: '/categories/:name/'
```

> [!NOTE]  
> Github Pages does not support Jekyll Archives, if you want this feature please use Github Actions instead

### Date format
Date format is configurable on `_config.yml`:

```
date_format: "%d/%m/%Y" # dd/mm/yy
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

## Customizing

### Layouts
To start customizing Tessera, copy any of the `_includes` components you'd like to modify:

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

### Styles
Create `assets/css/custom.css`, this file will serve as override without having to modify entire CSS, so you can edit specific elements you want.

You can see common modifications on [Wiki](https://github.com/ItsZariep/Tessera/wiki/Common-modifications-and-additions:)

## Contributing

Bug reports and pull requests are welcome on GitHub at [https://github.com/itszariep/tessera](https://github.com/itszariep/tessera). This project aims to be a safe and welcoming space for collaboration. All contributors are expected to adhere to the [Contributor Covenant](https://www.contributor-covenant.org/) code of conduct.

## License

This theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
