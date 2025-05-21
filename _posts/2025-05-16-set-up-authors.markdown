---
layout: post
title: "Set up authors"
date: 2025-05-16
categories: Tutorial
author: ItsZariep
image: /assets/img/thumb/set-up-authors.jpg
---

Welcome! This guide explains how to set up authors on your site.

This method doesn't require any plugin, is a base Jekyll feature.

---

### Adding author data

Tessera needs some files with author data:

1. `/assets/img/authors/[AUTHOR NAME].webp` : Author profile picture 
2. `/about/[AUTHOR NAME].md` : Author about page

Also, it needs an entry on `_includes/authors.html`:

```
{% raw %}
{% case include.author %}
	{% when "[YOUR NAME]" %}
		Cool Description
	{% when "Tessera" %}
		Cool Description
	{% else %}
		Unknown Author
{% endcase %}
{% endraw %}
```

> You can add multiple authors, for example with "Tessera", files would be `assets/img/authors/Tessera.webp` and `about/Tessera.md`

### Setting up a default author

If you already has entries with no author or want to have a "general" author, you can easily set up your site.

 `_config.yml`:
 
 
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
      author: "Tessera" # Replace with default author name
      image: /preview.jpg

```

## Set author on page

Simply put author: [Author Name] on the page info.

Example:

```
{% raw %}
---
layout: post
title: "Set up authors"
date: 2025-05-16
categories: Tutorial
author: Tessera
image: /assets/img/thumb/set-up-authors.jpg
---
{% endraw %}
```

---

Now, Tessera will show data about the post author at bottom of the page.