---
layout: post
title: "Modifyng HTML Components"
date: 2025-05-16
categories: Tutorial
image: /assets/img/thumb/modifyng-html-components.jpg
---


# Customizing HTML Components in the Tessera Jekyll Theme

Welcome! In this article, we’ll explore how to customize HTML components in the **Tessera** Jekyll theme.

Tessera is designed to be modular, meaning you don’t need to copy the entire theme or full HTML files to make changes. Instead, you can override individual components.

---

## How Tessera Handles Components

Tessera stores its HTML components in the `/_includes/` directory. It's **not recommended** to modify files in the `_layouts/` directory, as layouts typically just reference includes anyway.

To customize a component, simply create a modified copy of it in your Jekyll site's own `/_includes/` directory. Jekyll will automatically use your version instead of the default one provided by the theme.

---

## Available components:

| File Name             | Description           |
|-----------------------|-----------------------|
| authors.html          | Authors description   |
| bottompane.html       | Page bottom footer    |
| comments.html         | Comments section      |
| customheaders.html    | Custom HTML headers   |
| head.html             | Common HTML headers   |
| leftpane.html         | Left Side section     |
| pagination-controls.html | Pagination controls|
| postcontent.html      | Post content          |
| postgrid.html         | Post grid on Index page|
| rightpane.html        | Right side section    |
| searchbar.html        | Search bar            |
| sharebtn.html         | Share button on posts |
| toppane.html          | Page top header       |
| userbox.html          | Author box on posts   |

> `customheaders.html` is useful if you don't want/need to edit all head.html, for example when you only add Google Search console verification header

---

## Example: Modifying `rightpane.html`

Let’s say you want to customize the `rightpane.html` component. Here’s what you need to do:

1. Copy the original `/_includes/rightpane.html` file from the Tessera theme.
2. Paste it into your site’s local `/_includes/` directory.
3. Make your edits directly in your copy.

Once placed in your site’s `/_includes/`, Jekyll will prioritize your version during the build process.

Here’s an example of a modified version from [ItsZariep's website](https://github.com/ItsZariep/itszariep.github.io/blob/main/_includes/rightpane.html) :


```
<!-- Right Pane -->

<!-- You can remove or replace any section if required, copying _includes/rightpane.html on your page -->

<div id="right-container">

<!-- Banner Image or title-->
<!-- This image is displayed at the top of the right pane. -->
<a href="{{ '/' | relative_url }}"><img class="rp-banner" src="{{ '/assets/img/common/banner.webp' | relative_url }}" width="90%" /></a>

	<!-- Search Form -->
	<!-- A simple GET form that allows users to perform a search query. -->
	<!-- The search input is sent to the '/search' route. -->
		{% include searchbar.html %}
	
	<div class="rp-ytvideo">
		<iframe width="90%" height="210"
			src="https://www.youtube-nocookie.com/embed/videoseries?list=UULFpXpA76utFJBs9LdUHuhl-Q"
			title="YouTube playlist"
			frameborder="0"
			allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture;"
			allowfullscreen>
		</iframe>
		<figcaption>Ultimo video en youtube</figcaption>
	</div>

	<!-- Entries Section -->
	<!-- Displays a list of recent blog posts. -->
	<div class="rightpaneposts">
	<h2>Entradas</h2>
		<ul>
			<!-- Loop through the latest 5 posts in the site. -->
			{% for post in site.posts limit:5 %} 
				<li>
					<!-- Each post is linked to its full page. -->
					<a class="rp-post-link" href="{{ post.url | relative_url }}">
						<!-- Post title is shown here with a small heading. -->
						<h6 class="rp-post-title">{{ post.title }}</h6>
					</a>
				</li>
			{% endfor %}
		</ul>
	</div>
</div>
```