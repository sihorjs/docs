# Preloading

```html
<style type="text/css">
  /* Inline critical styles here */
</style>
<!-- Nullifying onload handler is needed in order to avoid doubling request -->
<link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'" />
<noscript><link rel="stylesheet" href="styles.css" /></noscript>
```


`as` attribute - script, style, font, image
`type` - MIME type

https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display
