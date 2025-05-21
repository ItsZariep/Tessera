---
layout: post
title: "Custom search behavior"
date: 2025-05-16
categories: Tutorial
image: /assets/img/thumb/custom-search-behavior.jpg
---

Welcome! This guide explains how to change search behavior for matching results

---

Tessera uses the file `/search.json`:

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
			"content": "{{ post.content | strip_html | strip_newlines | escape }}",
			"tags": "{{ post.tags }}"
		}{% unless forloop.last %},{% endunless %}
	{% endfor %}
]
{% endraw %}
```

Search looks for title, content and tags, for exaple, if you want to exclude content, you can set 

```
"content": "",
```

or if you want to set another Jekyll variable, you can do:

```
"content": "{{ post.content | strip_html | strip_newlines | escape }} {{ post.image | escape }} ",
```

## Internal behavior

If you have JavaScript knowledge, you can put your modified version of search logic in your site's `/assets/js/search.js`
