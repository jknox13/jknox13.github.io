---
layout: post
title:  "Jekyll Basics"
date:   2019-08-10 14:25:00 -0700
categories: web ruby
---
This site is generated with [Jekyll](https://jekyllrb.com/). Here are some brief 
notes on using Jekyll.

## What is Jekyll?
From the [Jekyll docs](https://jekyllrb.com/docs/): "Jekyll is a simple, 
extendable, static site generator" written in Ruby by 
[Git-hub](https://github.com/)'s co-founder Tom Preston. Jekyll can be used to 
easily create personal blogs, project pages, etc., and can be hosted for free on 
Git-hub.

## Initial Set-up
To get started, simply go to the [Jekyll docs](https://jekyllrb.com/docs/) page 
and follow the instructions there to:
1. Install `ruby`
2. Install `jekyll` and `bundler` gems
3. Initalize a new `jekyll` site
4. Serve the site locally.

To get a better understanding of how to customize your new site, head to the 
step-by-step [tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/) which 
is where most of the information below comes.

## Liquid
[Liquid](https://shopify.github.io/liquid/) is an open-source templating 
language developed by [Shopify](https://www.shopify.com/) and written in Ruby.  
Liquid has three main components that ...:

- **Objects**: {% raw %} tells Liquid where to put content, and are denoted by 
  double curly braces (i.e. `{{ page.title }}` {% endraw %}
- **Tags**: {% raw %} create logic and control flow for templates, and are 
  denoted by `{%` and `%}` {% endraw %}.
- **Filters**: {% raw %} change the output of a Liquid object via piping (i.e.  
  `{{ page.title | downcase }}`). {% endraw %}

## Front Matter
Front Matter is a YAML snippet at the top of a file between two triple dashed 
lines. Front Matter is used to set variables for use in this page, and are 
accessed under the `page` variable:

{% highlight ruby %}
---
foo: 13
---
...
{% raw %}{{ page.foo }}{% endraw %}
{% endhighlight %}

## Layouts
Layouts are templates that wrap around your content, and are useful if you want 
several pages on your site to have the same general structure (layout). Layouts 
you write should be placed in the `_layouts` directory.

## Includes
Say you want to include a snippet of HTML in several different pages but don't 
want to reproduce this code, you can use the `include` tag to include content 
from a file in the `_includes` directory.

## Data
Load from YAML, JSON, and CSV files placed in the `_data` directory using the 
`data` tag.

## Assets
Place CSS, JS, images and other assets in the `assets` directory -- typically 
within their own respective subdirectories (i.e. `/assets/css/styles.scss`).

## Blogging
All posts should live in the `_posts` directory. Filenames for blog posts must 
conform to the naming convention: `_posts/{date}-{title}.{extention}` (i.e.  
`_posts/2019-04-20-half-baked.md`).
