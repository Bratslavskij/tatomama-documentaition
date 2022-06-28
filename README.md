<h1>Авторські права © | 2016 - 2022 | ТатоМама | Україна 🇺🇦 | Всі права захищені</h1>
<h2>Browser Sync</h2>
<img src="https://avatars.githubusercontent.com/u/10654171?s=200&amp;v=4" width="100" height="100" alt="BrowserSync">
<p>Команда запуску Browser Sync у VSCode: </p>
Skip to content
 
Search or jump to…
Pulls
Issues
Marketplace
Explore
 
@Bratslavskij 
verlok
/
vanilla-lazyload
Public
 Watch 111 Fork 650
 Star 6.9k
Code
Issues
7
Pull requests
Actions
Projects
Wiki
Security
Insights
 master 
vanilla-lazyload/README.md
Go to file
 
 
864 lines (629 sloc)  59.9 KB
Raw Blame

 
LazyLoad is a lightweight (2.4 kB) and flexible script that **speeds up your web application** by deferring the loading of your below-the-fold images, animated SVGs, videos and iframes to **when they will enter the viewport**. It's written in plain "vanilla" JavaScript, it leverages the [IntersectionObserver](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API) API, it supports [responsive images](https://alistapart.com/article/responsive-images-in-practice), it optimizes your website for slower connections, and can enable native lazy loading. See [all features](#-all-features-compared) for more.

[![vanilla-lazyload (latest)](https://img.shields.io/npm/v/vanilla-lazyload/latest.svg)](https://www.npmjs.com/package/vanilla-lazyload)
[![vanilla-lazyload (downloads)](https://img.shields.io/npm/dy/vanilla-lazyload.svg)](https://www.npmjs.com/package/vanilla-lazyload)
[![](https://data.jsdelivr.com/v1/package/npm/vanilla-lazyload/badge)](https://www.jsdelivr.com/package/npm/vanilla-lazyload)

➡️ Jump to: [👨‍💻 Getting started - HTML](#-getting-started---html) - [👩‍💻 Getting started - Script](#-getting-started---script) - [🥧 Recipes](#-recipes) - [📺 Demos](#-demos) - [😋 Tips & tricks](#-tips--tricks) - [🔌 API](#-api) - [😯 All features compared](#-all-features-compared)

---

**Love this project? 😍 [Buy me a coffee!](https://ko-fi.com/verlok)**

---

## 👨‍💻 Getting started - HTML

In order to make your content be loaded by LazyLoad, you must use some `data-` attributes instead of the actual attributes. Examples below.

### Lazy image:

```html
<img alt="A lazy image" class="lazy" data-src="lazy.jpg" />
```

### Lazy image with low quality placeholder:

```html
<img alt="A lazy image" class="lazy" src="lazy-lowQuality.jpg" data-src="lazy.jpg" />
```

### Lazy responsive image with `srcset` and `sizes`:

```html
<img
  alt="A lazy image"
  class="lazy"
  data-src="lazy.jpg"
  data-srcset="lazy_400.jpg 400w, 
    lazy_800.jpg 800w"
  data-sizes="100w"
/>
```

To have a low quality placeholder, add the `src` attribute pointing to a very small version of the image. E.g. `src="lazy_10.jpg"`.

### Lazy responsive image with hi-dpi support using the `picture` tag:

```html
<picture>
  <source media="(min-width: 1200px)" data-srcset="lazy_1200.jpg 1x, lazy_2400.jpg 2x" />
  <source media="(min-width: 800px)" data-srcset="lazy_800.jpg 1x, lazy_1600.jpg 2x" />
  <img alt="A lazy image" class="lazy" data-src="lazy.jpg" />
</picture>
```

To have a low quality placeholder, add the `src` attribute pointing to a very small version of the image to the `img` tag. E.g. `src="lazy_10.jpg"`.

### Lazy responsive image with automatic _WebP_ format selection, using the `picture` tag:

```html
<picture>
  <source
    type="image/webp"
    data-srcset="lazy_400.webp 400w, 
      lazy_800.webp 800w"
    data-sizes="100w"
  />
  <img
    alt="A lazy image"
    class="lazy"
    data-src="lazy.jpg"
    data-srcset="lazy_400.jpg 400w, 
      lazy_800.jpg 800w"
    data-sizes="100w"
  />
</picture>
```

To have a low quality placeholder, add the `src` attribute pointing to a very small version of the image to the `img` tag. E.g. `src="lazy_10.jpg"`.

### Lazy background image

⚠ **IMPORTANT NOTE**: To display content images on your pages, always use the `img` tag. This would benefit the SEO and the accessibility of your website. To understand if your images are content or background, ask yourself: "would my website user like to see those images when printing out the page?". If the answer is "yes", then your images are content images and you should avoid using background images to display them.

#### Single background image:

```html
<div class="lazy" data-bg="lazy.jpg"></div>
```

#### Single background, with HiDPI screen support:

```html
<div class="lazy" data-bg="lazy.jpg" data-bg-hidpi="lazy@2x.jpg"></div>
```

#### Multiple backgrounds:

```html
<div
  class="lazy"
  data-bg-multi="url(lazy-head.jpg), 
    url(lazy-body.jpg), 
    linear-gradient(#fff, #ccc)"
>
  ...
</div>
```

#### Multiple backgrounds, HiDPI screen support:

```html
<div
  class="lazy"
  data-bg-multi="url(lazy-head.jpg),
    url(lazy-body.jpg),
    linear-gradient(#fff, #ccc)"
  data-bg-multi-hidpi="url(lazy-head@2x.jpg),
    url(lazy-body@2x.jpg),
    linear-gradient(#fff, #ccc)"
>
  ...
</div>
```

