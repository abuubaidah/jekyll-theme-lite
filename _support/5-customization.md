---
title: Customization
icon: code
toc: true
---

### Theme Color Customization

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
/assets/css/main.scss
```

### Further Development

Install [UIkit](https://getuikit.com/) font end framework dependency via Npm:
```bash
npm install
```
Enable live browser reload with the following:
```bash
bundle exec jekyll s --livereload
```
