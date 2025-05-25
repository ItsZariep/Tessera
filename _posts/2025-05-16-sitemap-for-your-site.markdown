---
layout: post
title: "Sitemap supporton your site"
date: 2025-05-16
categories: Tutorial
image: /assets/img/thumb/sitemap-support.jpg
---

Welcome! This guide explains how to get RSS support on your site

This method doesn't require any plugin, only a file	.

---

You'll probably need a sitemap to manage your site with tools like `Google's Search Console` or `Bing Webmaster Tools`.

## Setting up

Create `/sitemap.xml` on your site's root path with following content:

```
{% raw %}
---
layout: null
permalink: /sitemap.xml
---

<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">

	{%- assign baseurl = site.url | append: site.baseurl -%}

	{%- for page in site.pages -%}
		{%- unless page.sitemap == false or page.permalink contains '404' -%}
			<url>
				<loc>{{ baseurl }}{{ page.url | xml_escape }}</loc>
				{%- if page.date -%}
					<lastmod>{{ page.date | date_to_xmlschema }}</lastmod>
				{%- endif -%}
				<priority>0.5</priority>
			</url>
		{%- endunless -%}
	{%- endfor -%}

	{%- for post in site.posts -%}
		<url>
			<loc>{{ baseurl }}{{ post.url | xml_escape }}</loc>
			<lastmod>{{ post.date | date_to_xmlschema }}</lastmod>
			<priority>0.8</priority>
		</url>
	{%- endfor -%}
</urlset>

{% endraw %}
```

That's all!, your sitemap is now available on `[yourpageurl]/sitemap.xml` and you can use it on search engines webmaster tools