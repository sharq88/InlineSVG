# InlineSVG

This is a jQuery plugin that takes an image selector
as an argument having a SVG as source. Then it inlines
the SVG so that the SVG stroke and path can be manipulated
using plain CSS.

## Usage ##

### HTML ###
```html
<img
    class="svg"
    src="http://addc.digitaslbiacademy.com/img/icon/svg/00-login.svg"
    alt="" />

```

### CSS ###
```css
.svg path stroke {
    color: #00ff88;
}
```

### JS ###
```javascript
$('.svg').inlineSVG();

```

## Use callbacks ##

```javascript
$('.svg').inlineSVG({
    eachAfter: function () {
        // this - is replaced <svg> DOM-element
        console.log('One element is replaced');
    },
    allAfter: function () {
        console.log('All elements is replaced');
    },
    beforeReplace: function ($img, $svg, next) {
        $svg.attr('title', $img.attr('alt'));
        next();
    }
});
```

## License ##

[MIT](./LICENSE-MIT)
