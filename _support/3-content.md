---
title: Adding Content
icon: file-edit
toc: true
---

### Creating news posts

To create a new post, you can create a new markdown file inside the `_posts` directory by following the recommended file naming format:
```
YEAR-MONTH-DAY-title.MARKUP
```
Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. For example, the following are examples of valid post filenames:

```
2011-12-31-new-years-eve-is-awesome.md
2012-09-12-how-to-write-a-blog.md
```

Post requires front matter, everything in between the first and second --- are part of the YAML Front Matter, and everything after the second --- will be rendered with Markdown and show up as “Content”.
The following is a post file with different configurations you can add as example:

```yaml
---
layout: post
title: How To Travel On Low Budget
---
```

You can rebuild the site in many different ways, but the most common way is to run `bundle exec jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To keep things more organized, add post images to `/assets/posts/` directory, and add theme images to `/assets/img/` directory.

### Adding images to posts
To add an image to a post or page use the following codes:
Local image from `/assets/posts/` directory:


{% raw %}
```yaml
{% include image.html img="girl.jpg" alt="Alt for image" caption="Girl on a rock" %}
```
{% endraw %}

External wide image with lightbox:
{% raw %}
```yaml
{% include image.html img="https://source.unsplash.com/TT-ROxWj9nA.jpg" lightbox="true" alt="Alt for image" caption="Image in lightbox" %}
```
{% endraw %}

### Adding table of contents
Add the following to the front matter of the support post:
```
toc: true
```

### Responsive videos
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

To create a draft post, create the post file under the `_drafts` directory, and you can find more information in [Working with Drafts](https://jekyllrb.com/docs/drafts/).

### Creating home page

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

### Support Posts

Create new support post entries in `_support` folder, similar to creating posts, but with following front matter settings:

```yml
---
title: Category hosting Setting up new domain and page
icon: heart
---
```

All available icons can be found [here](https://getuikit.com/docs/icon#library).

### Creating changelog page

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
