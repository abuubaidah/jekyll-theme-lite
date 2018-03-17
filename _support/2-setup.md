---
title: Theme Setup
icon: settings
toc: true
---

### Site and author details

Add your site and author details in `_config.yml`:
```yaml
# Site title and description
title:              Lite
description:        Helpdesk Jekyll Theme

# Site base hostname & protocol, e.g. http://example.com
url:                "https://lite.jekyll.plus"

# Site logo, image or text
brand:
    image:          logo.svg  # e.g. logo.png, upload logo image file to /assets/img/ folder
    text:           Lite      # if the above "logo:" image variable  is not set, this text logo is displayed instead

# Default author settings
author:
    name:           John Smith
    github:         username    # Github username for avatar
```

### Main navigation bar
Set in the main navigation links in `_data/navigation_header.yml`:
```yaml
- title: About
  url: /about/
```

### Site footer setup

Edit copyright notice in `_config.yml`:
```yaml
footer:
    copyright:
```

Set in the navigation links in `_data/navigation_footer.yml`:
```yaml
- title: About
  url: /about/
```

### Enabling comments (via Disqus)

Optionally, if you have a Disqus account, you can tell Jekyll to use it to show a comments section below each post. To enable it, add the following lines to your Jekyll site:

```yaml
disqus:
    shortname: my_disqus_shortname
```

You can find out more about Disqus' shortnames [here](https://help.disqus.com/customer/portal/articles/466208).

Comments are enabled by default and will only appear in production, i.e., `JEKYLL_ENV=production`. If you don't want to display comments for a particular post you can disable them by adding `comments: false` to that post's YAML Front Matter.

### Adding Google analytics

To enable Google Anaytics, add the following lines to your Jekyll site:

```yaml
google_analytics: UA-NNNNNNNN-N
```

Google Analytics will only appear in production, i.e., `JEKYLL_ENV=production`
