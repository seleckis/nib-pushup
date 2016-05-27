# Mixins
## Position

The position mixins `absolute`, `fixed`, and `relative` provide a shorthand variant to what is otherwise three CSS properties. The syntax is as follows:

```
fixed|absolute|relative: top|bottom [n] left|right [n]
```

The following example will default to (0,0):

```stylus
#back-to-top
  fixed bottom right
```

```css
#back-to-top {
  position: fixed;
  bottom: 0;
  right: 0;
}
```

You may also specify the units:

```stylus
#back-to-top
  fixed bottom 10px right 5px
```

```css
#back-to-top {
  position: fixed;
  bottom: 10px;
  right: 5px;
}
```

## Clearfix
Clearfixing causes containers to expand to contain floated contents. A simple example is shown [here](http://learnlayout.com/clearfix.html).

The clearfix mixin takes no arguments and expands to a form that provides extremely robust browser support.

```stylus
.clearfix
  clearfix()
```

```css
.clearfix {
  zoom: 1;
}
.clearfix:before,
.clearfix:after {
  content: "";
  display: table;
}
.clearfix:after {
  clear: both;
}
```

## Border Radius
Nib's `border-radius` supports both the regular syntax as well as augmenting it to make the value more expressive.

```stylus
button
  border-radius 1px 2px / 3px 4px

  button
    border-radius 5px

  button
    border-radius bottom 10px
```

```css
button {
  border-radius: 1px 2px/3px 4px;
}
button {
  border-radius: 5px;
}
button {
  border-top-left-radius: 10px;
  border-bottom-right-radius: 10px;
}
```

## Responsive Images
The `image` mixin allows you to define a `background-image` for both the normal image, and a doubled image for devices with a higher pixel ratio such as retina displays. This works by using a @media query to serve an "@2x" version of the file.

```stylus
#logo
  image '/images/branding/logo.main.png'

#logo
  image '/images/branding/logo.main.png' 50px 100px
```

```css
#logo {
  background-image: url("/images/branding/logo.main.png");
}
@media all and (-webkit-min-device-pixel-ratio: 1.5) {
  #logo {
    background-image: url("/images/branding/logo.main@2x.png");
    background-size: auto auto;
  }
}
#logo {
  background-image: url("/images/branding/logo.main.png");
}
@media all and (-webkit-min-device-pixel-ratio: 1.5) {
  #logo {
    background-image: url("/images/branding/logo.main@2x.png");
    background-size: 50px 100px;
  }
}
```

## Ellipsis
The `overflow` property is augmented with a "ellipsis" value, expanding to what you see below.

```stylus
button
  overflow ellipsis
```

```css
button {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

## Reset
Nib comes bundled with [Eric Meyer's style reset](eric-meyer) and [Nicolas Gallagher's _Normalize_](normalize) support and, you can choose to apply the global or any specifics that you wish. To view the definitions view [`reset.styl`](https://github.com/tj/nib/blob/master/lib/nib/reset.styl).

[eric-meyer]: http://meyerweb.com/eric/tools/css/reset/
[normalize]: https://github.com/necolas/normalize.css

> CSS Reset

- `global-reset()`
- `nested-reset()`
- `reset-font()`
- `reset-box-model()`
- `reset-body()`
- `reset-table()`
- `reset-table-cell()`
- `reset-html5()`

> Normalize

- `normalize-html5()`
- `normalize-base()`
- `normalize-links()`
- `normalize-text()`
- `normalize-embed()`
- `normalize-groups()`
- `normalize-forms()`
- `normalize-tables()`
- `normalize-css()`

[Read more][normalize-about] about Normalize or see the original CSS [here][normalize-css].

[normalize-about]: http://nicolasgallagher.com/about-normalize-css/
[normalize-css]: https://github.com/necolas/normalize.css/blob/master/normalize.css

## Border
This shorthand lets you create a border by just specifying a color, with defaults for width and style.

```stylus
.foo
  border red
```

```css
.foo {
  border: 1px solid red;
}
```

## Shadow Stroke
Creates a text outline using text-shadow.

```stylus
.foo
  shadow-stroke(red)
```

```css
.foo {
  text-shadow: -1px -1px 0 red, 1px -1px 0 red, -1px 1px 0 red, 1px 1px 0 red;
}
```

## Sizes
This shorthand lets you set width and height in one go.

```stylus
.foo
  sizes 5em 10em
```

```css
.foo {
  width: 5em;
  height: 10em;
}
```

## Font-face
This function lets you add custom font faces and use it in font-family property.

```stylus
$fontpath = '/assets/fonts'
font-face(Expletus Sans, ExpletusSans-Regular, Expletus_Sans)
font-face(Expletus Sans, ExpletusSans-BoldItalic, Expletus_Sans, bold, italic)
```
where arguments are: font name, filename, folder name, font weight (optional), font style (optional).
`$fontpath` is a variable to define path to fonts folder. It has default value of '.'.
```css
@font-face {
  font-family: Expletus Sans;
  font-weight: 400;
  font-style: normal;
  src: local('☺'), url("/assets/fonts/Expletus_Sans/ExpletusSans-Regular.woff2") format('woff2'), url("/assets/fonts/Expletus_Sans/ExpletusSans-Regular.woff") format('woff'), url("/assets/fonts/Expletus_Sans/ExpletusSans-Regular.ttf") format('truetype');
}
@font-face {
  font-family: Expletus Sans;
  font-weight: bold;
  font-style: italic;
  src: local('☺'), url("/assets/fonts/Expletus_Sans/ExpletusSans-BoldItalic.woff2") format('woff2'), url("/assets/fonts/Expletus_Sans/ExpletusSans-BoldItalic.woff") format('woff'), url("/assets/fonts/Expletus_Sans/ExpletusSans-BoldItalic.ttf") format('truetype');
}
```

# Aliases
These aliases are provided purely for convenience.

official    | aliases
----------- | ----------
nowrap      | no-wrap  
white-space | whitespace
