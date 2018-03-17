---
title: Addon Includes
icon: plus
toc: true
---

### Google Map Include

To display Google map on contact page, add the following in your page content, replacing latitude, longitude and zoom values:

{% raw %}
```yaml
{% include map.html latitude="40.6700" longitude="-73.9400" zoom="16" %}
```
{% endraw %}

### Contact Form Include (via FormSpree)

To display Google map on contact page, add the following in your page content, replacing latitude, longitude and zoom values:

Submit the form and confirm your email address at [FormSpree](https://formspree.io/). Then add the following include to a page, replacing the email address:

{% raw %}
```yaml
{% include formspree.html email="john@company.com" redirect="/thanks" %}
```
{% endraw %}
