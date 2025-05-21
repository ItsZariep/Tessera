---
layout: post
title: "RSS support on your site"
date: 2025-05-16
categories: Tutorial
image: /assets/img/thumb/rss-support.jpg
---

Welcome! This guide explains how to get RSS support on your site

This method doesn't require any plugin, only a file	.

---

## Setting up

Create `/feed.xml` on your site's root path with following content:

```
{% raw %}
---
layout: null
permalink: /feed.xml
---

<?xml version="1.0" encoding="UTF-8"?>
<rss version="2.0">
	<channel>
		<title>{{ site.title | xml_escape }}</title>
		<link>{{ site.url }}</link>
		<description>{{ site.description | xml_escape }}</description>
		<language>es</language>
		<lastBuildDate>{{ site.time | date_to_rfc822 }}</lastBuildDate>

		{% for post in site.posts %}
		<item>
			<title>{{ post.title | xml_escape }}</title>
			<link>{{ site.url }}{{ post.url }}</link>
			<guid isPermaLink="true">{{ site.url }}{{ post.url }}</guid>
			<description>{{ post.excerpt | xml_escape }}</description>
			<pubDate>{{ post.date | date_to_rfc822 }}</pubDate>
		</item>
		{% endfor %}
	</channel>
</rss>
{% endraw %}
```

That's all!, Tessera theme by itself already has the reference for `/feed.xml` in theme's [`head.html`](https://github.com/ItsZariep/Tessera/blob/main/_includes/head.html), so no extra steps are needed.