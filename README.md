![Scrollissimo](https://habrastorage.org/files/997/93c/cec/99793ccec1464bb594f44f569396f184.png)

Javascript plugin for smooth scroll-controlled animations


[![GitHub release](https://img.shields.io/github/release/promo/scrollissimo.svg?style=flat-square)]()

[![Build Status][travis-image]][travis-url]

Scrollissimo animates Greensock's tweens and timelines on user's scroll.

Comparing Scrollissimo and another default plugins [here](http://promo.github.io/scrollissimo/examples/paperfly). 

## Get started

### Download

Scrollissimo is available for downloading from repository. Also bower users can install Scrollissimo by command:

```bash
bower install scrollissimo
```

### Connect
The first step you need is to include Greensock:

```html
    <script src="http://cdnjs.cloudflare.com/ajax/libs/gsap/latest/TweenLite.min.js"></script>
    <script src="http://cdnjs.cloudflare.com/ajax/libs/gsap/latest/TimelineLite.min.js"></script>
    <script src="http://cdnjs.cloudflare.com/ajax/libs/gsap/latest/plugins/CSSPlugin.min.js"></script>
```

... or just:

```html
    <script src="http://cdnjs.cloudflare.com/ajax/libs/gsap/latest/TweenMax.min.js"></script>
```

... and Scrollissimo of course:

```html
    <script src="scrollissimo/dist/scrollissimo.min.js"></script>
```

To support touch devices you also need to include touch adapter:

```html
    <script src="scrollissimo/dist/scrollissimo.touch.min.js"></script>
```

Next we will trigger Scrollissimo on each scroll event:

```html
<script>
    $(document).ready(function(){
        $(window).scroll(function(){
            Scrollissimo.knock();
        });
    });
</script>
```

**NOTE:** for touch devices support you must also attach scrollissimo.touch.min.js.

### Now lets animate something!
Let we have a div called *Divy*:

```html
<div id="Divy"></div>
```
```css
#Divy{
    position: fixed;
    top: 0;
    left: 0;
    
    height: 50px;
    width: 50px;
    
    background: red;
}
```

Now we will animate Divy's width. At the begining of page its width will be equal to 50px. And as we scroll its width will be grow up to 300px after we have scrolled for 1000 pixels.
The first let's create Grensock's tween.

```js
var divyTween = TweenLite.to(document.getElementById('divy'), 1000, { width: 300 });
```

Then we need to add this tween to Scrollissimo.

```js
Scrollissimo.add(divyTween, 0, 6);
```

The second argument is start scroll value in pixels.
The third argument is a maximal speed of this animation. 1 approximately equal to 6% of tween's length per second. You must find your own value for each animation.

That is all you need to do to make a simple animation. Result you may see [here](https://jsfiddle.net/e5udtvaL/3/).

Animating timelines is similar to tween`s animating.
    
[travis-url]: http://travis-ci.org/Promo/scrollissimo
[travis-image]: http://img.shields.io/travis/Promo/scrollissimo.svg?branch=master&style=flat-square
