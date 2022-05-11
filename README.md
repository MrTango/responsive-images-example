# responsive-images-example

Responsive images example, srcset and art direction in combination.

A basic setup could be as follows:

```html
<picture class="image-size-large">
  <!-- desktop: -->
  <source
    srcset="https://picsum.photos/id/1011/800 800w,
            https://picsum.photos/id/1011/1000 1000w,
            https://picsum.photos/id/1011/1200 1200w,
            https://picsum.photos/id/1011/1600 1600w"
    >
  <img src="https://picsum.photos/id/1011/800" width="800" height="800">
</picture>
```

It will draw the image with a default width of 800px and will choose the best image depending on what is in cache and what is needed for the current vieport and screen resolution (1x, 2x, 3x).
The browser will pic the image by it self, you don't have any control over it.

For the use case of `art direction` we need to use multiple source tags with media queries:

```html
<picture class="image-size-small">
  <!-- desktop: -->
  <source media="(min-width:800px)"
    srcset="https://picsum.photos/id/1011/400 400w,
            https://picsum.photos/id/1011/800 800w,
            https://picsum.photos/id/1011/1000 1000w,
            https://picsum.photos/id/1011/1200 1200w"
    sizes="400px"
    >
  <!-- smartphone -->
  <source media="(max-width:799px)"
    srcset="https://picsum.photos/id/1012/400 400w,
            https://picsum.photos/id/1012/800 800w,
            https://picsum.photos/id/1012/1000 1000w,
            https://picsum.photos/id/1012/1200 1200w"
    sizes="90vw"
    >
  <img src="https://picsum.photos/id/1012/400"  width="400" height="400">
</picture>
```
