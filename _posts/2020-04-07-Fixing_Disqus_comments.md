---
layout: post
title:  "Fixing Disqus comments"
tags: [web]
comments: true
---


If you want to add comments to your site the simplest option is to use [Disqus service](https://disqus.com) that integrated into default themes of Jekyll.

Initially, I didn't like its cartoon style, but short googling gave its strong pluses:

1. It works (at least should and will after fixing toward the end of this post)
1. It's free
1. It's built-in into Jekyll

some minuses:

1. Tracks and uses users' data for advertising
1. Predefined "cartoonish" style in the free option

The initial setup was relatively easy, after registration, adding your short registered name to `_config.yml`:  

``` YAML
# Disqus Comments
disqus:
  # Leave shortname blank to disable comments site-wide.
  # Disable comments for any post by adding `comments: false` to that post's YAML Front Matter.
  shortname: "balzes"
```

and then the tricky step - the comments wouldn't appear on your local server that you get using the command:  
`bundle exec jekyll serve`

If you use GitHub pages by pushing your sources into your GitHub repository named `<your_user>.github.io` and then try to access it on `https://<your_user.>.github.io` it works.

In my case, I copied the content of `_site` after running `bundle exec jekyll build` on to external hosting (just for fun and self-study, GitHub's Pages are awesome) and the comments didn't appear.

The debugging showed that inside a theme folder, there is `_includes\disqus_comments.html` that contains the following check:  
{% raw %}

``` Liquid
{%- if page.comments != false and jekyll.environment == "production" -%}
```

by adding `{{jekyll.environment}}` into `*.md` or `*.html` file and looking on published page uncovered that it replaced with a string `development`.

And __the fix__ was to define a local variable `JEKYLL_ENV=production` by running :  
  
`JEKYLL_ENV=production bundle exec jekyll build`  

That's it!  

Some additional takeaway from this post: if you want to include in your post text that contains `{% some text %}` or `{{ some text }}` it will be processed by [Liquid](https://shopify.github.io/liquid/), the template language used by Jekyll, as a command and cause an error or will be replaced by a matching variable value, so to do it, you should escape the text using:
{% endraw %}

``` Liquid
{{"{%"}} raw %}
{{"{%"}} some text %}
{{"{%"}} endraw %}
```

and in case you want to include `{{"{% endraw "}}%}` itself, you can divide it into variable + string e.g.:  
{% raw %}
`{{"{% "}} endraw %}`
{% endraw %}

this trick was found in a comment here: [https://stackoverflow.com/questions/19352368/show-raw-tags-in-post-generated-by-jekyll](https://stackoverflow.com/questions/19352368/show-raw-tags-in-post-generated-by-jekyll)
