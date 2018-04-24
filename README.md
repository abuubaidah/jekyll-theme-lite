# [Lite Jekyll Theme](https://lite.jekyll.plus/)

[![GitHub license](https://img.shields.io/github/license/ivanchromjak/jekyll-theme-lite.svg)](https://github.com/ivanchromjak/jekyll-theme-lite/blob/master/LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/ivanchromjak/jekyll-theme-lite.svg)](https://github.com/ivanchromjak/jekyll-theme-lite/issues)
[![Tip Me via PayPal](https://img.shields.io/badge/PayPal-tip%20me-0070ba.svg?logo=paypal)](https://www.paypal.me/ivanchromjak)
[![Twitter](https://img.shields.io/twitter/url/https/github.com/ivanchromjak/jekyll-theme-lite.svg?style=social)](https://twitter.com/intent/tweet?text=Wow:&url=https%3A%2F%2Fgithub.com%2Fivanchromjak%2Fjekyll-theme-lite)

Lite is a Jekyll theme for customer self-service support site. Theme [demo](https://lite.jekyll.plus/) site.

![screenshot](https://lite.jekyll.plus/assets/img/screenshot.png)

## Features

* Changelog page
* Faq page
* Image lightbox
* Google maps
* Github avatar
* Contact form (FormSpree)
* Disqus comments for posts
* SEO tags
* Google Analytics

## Contents
- [Installation](#installation)
- [Home Page](#home-page)
- [Support Posts](#support-posts)
- [Changelog Page](#changelog-page)
- [Content](#content)
  - [Google Map](#google-map)
  - [Images](#images)
  - [Videos](#videos)
  - [Comments](#comments)    
- [Contributing](#contributing)
- [Development](#development)
- [Credits](#credits)

## Installation

Install the dependencies with [Bundler](http://bundler.io/):

```bash
bundle install
```

Run the following to generate your site:
```bash
bundle exec jekyll serve
```

You can find more on [Deployment Methods](https://jekyllrb.com/docs/deployment-methods/) page on Jekyll website.

### Google analytics

To enable Google Anaytics, add the following lines to your Jekyll site:

```yaml
  google_analytics: UA-NNNNNNNN-N
```

Google Analytics will only appear in production, i.e., `JEKYLL_ENV=production`

### Updating favicon

You can find the current favicon (favicon.png) inside the theme `/assets/img/` directory, just replace it with your new favicon.

## Home Page

To create a home page, just create a `index.md` file inside the root directory. The following is a YAML Front Matter example for a page:

```yaml
---
layout: home
hero:
  title: How Can We Help?
  subtitle: SELF SERVICE KNOWLEDGE BASE
cta:
  title: Didn't find an answer to your question?
  button_text: Contact Us   
  button_url: /contact/
filter: true
---
```

Home page category boxes are added in `_data/navigation_home.yml`, e.g.:
```yml
- title: Getting Started
  desc: Get your account up and running in just few easy steps
  icon: settings
  doc: usage

- title: Account and Billing
  desc: Managing your account, creating new users and exporting data
  icon: credit-card
  doc: drafts
```

All available icons can be found [here](https://getuikit.com/docs/icon#library).

## Support Posts

Create new support post entries in `_support` folder, similar to creating posts, only the title is required in front matter:

```yml
---
title: Category hosting Setting up new domain and page
---
```

### Adding Table of contents
Add the following to the front matter of the support post:
```
toc: true
```

## Changelog page

Create  new page with the following front matter:

```yml
---
layout: changelog
title: Changelog
permalink: /changelog/
---
```

Changelog enties are added in `_data/changelog.yml`:

```yml
- title: Version 0.6.0
  date: Aug 15, 2017
  list:
  - Added style support for radio and checkbox in Firefox
  - Removed class from Section component
```

## Contact Form (via FormSpree)

To display Google map on contact page, add the following in your page content, replacing latitude, longitude and zoom values:

Submit the form and confirm your email address at [FormSpree](https://formspree.io/). Then add the following include to a page, replacing the email address:

```yaml
{% include formspree.html email="john@company.com" redirect="/thanks" %}
```

## Content

### Google Map

To display Google map on contact page, add the following in your page content, replacing latitude, longitude and zoom values:

```yaml
{% include map.html latitude="40.6700" longitude="-73.9400" zoom="16" %}
```

### Images
To keep things more organized, add post images to `/assets/posts/` directory, and add theme images to `/assets/img/` directory.

To add an image to a post or page use the following:
Local image from `/assets/posts/` directory:
```yaml
{% include image.html img="girl.jpg" alt="Alt for image" caption="Girl on a rock" %}
```
External image in lightbox:
```yaml
{% include image.html img="https://source.unsplash.com/TT-ROxWj9nA.jpg" lightbox="true" alt="Alt for image" caption="Image in lightbox" %}
```


### Videos
Embed local videos:
```html
<video controls playsinline uk-video="automute: true">
    <source src="http://www.quirksmode.org/html5/videos/big_buck_bunny.mp4" type="video/mp4">
    <source src="http://www.quirksmode.org/html5/videos/big_buck_bunny.ogv" type="video/ogg">
</video>
```
Embed YouTube videos:
```html
<iframe src="http://www.youtube.com/embed/YE7VzlLtp-4?autoplay=0&amp;showinfo=0&amp;rel=0&amp;modestbranding=1&amp;playsinline=1" width="600" height="340" frameborder="0" allowfullscreen uk-responsive uk-video="automute: true"></iframe>
```

### Comments

Optionally, if you have a Disqus account, you can tell Jekyll to use it to show a comments section below each blog post. To enable it, add the following lines to your Jekyll site:

```yaml
disqus:
    shortname: my_disqus_shortname
```

You can find out more about Disqus' shortnames [here](https://help.disqus.com/customer/portal/articles/466208).

Comments are enabled by default and will only appear in production, i.e., `JEKYLL_ENV=production`. If you don't want to display comments for a particular post you can disable them by adding `comments: false` to that post's YAML Front Matter.


## Development

Install [UIkit](https://getuikit.com/) font end framework dependency via Npm:
```bash
npm install
```
Enable live browser reload with the following:
```bash
bundle exec jekyll s --livereload
```

### Customization

To modify the primary color, open `/_sass/theme/variables.scss` and replace the color values e.g.:

```scss
// Primary color
$tm-primary-color: #0089ff;
// Body background
$tm-body-background: linear-gradient(to top, #0065fd 0%, #0089ff 100%);
```

Further style customisation can be done in the following files:
```
/_sass/theme/mixins.scss
/_sass/theme/variables.scss
```

## Contributing

Having trouble working with the theme or found a bug or typo? Interested in adding a feature or fixing a bug? Submit an issue or pull request.

Before requesting features or submitting a pull requests, please ask yourself if it is something that most people will use, if not sure just ask.

### Pull Requests
When submitting a pull request:

1. Clone the repository
2. Create a branch off of master branch and give it a meaningful name e.g. new-feature-name.
3. Open a pull request on GitHub and describe the feature or fix.


## Author

Lite was developed by [Ivan Chromjak](https://ivanchromjak.com).

## Credits

- Google analytics https://www.google.com/analytics/
- Google maps https://www.google.com/maps
- UIkit front end framework https://getuikit.com/
- Jekyll https://jekyllrb.com/
- FormSpree https://formspree.io/
