# Mixins
## Position

The position mixins `absolute`, `fixed`, and `relative` provide a shorthand variant to what is otherwise three CSS properties. The syntax is as follows:

```
fixed|absolute|relative: top [n] | right [n] | bottom [n] | left [n]
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

## Clearfix
Clearfixing causes containers to expand to contain floated contents. A simple example is shown [here](http://learnlayout.com/clearfix.html).

The clearfix mixin takes no arguments and expands to a form that provides extremely robust browser support.

```stylus
.clearfix
  clearfix()
```

```css
.clearfix:before,
.clearfix:after {
  content: "";
  display: table;
}
.clearfix:after {
  clear: both;
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

## Hide text
The `hide-text` function hides text in an element. Usefull to replace text with image, but leave text for SEO.

```stylus
button
  hide-text()
  background url('assets/img/lorem.jpg')
```

```css
button {
    text-indent: 101%;
    white-space: nowrap;
    overflow: hidden;
    background: url('assets/img/lorem.jpg');
}
```

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


## Font-face
This function lets you add custom font faces and use it in font-family property.

```stylus
$fontspath = '/assets/fonts/'
font-face(ExpletusSans, ExpletusSans-Regular, Expletus_Sans)
font-face(ExpletusSansBoldItalic, ExpletusSans-BoldItalic, Expletus_Sans, bold, italic)
```
where arguments are: *font name, filename, folder name (optional, default = ''), font weight (optional, default = normal), font style (optional, default = normal).*

`$fontspath` is used to define path to fonts folder (default value = '.').
```css
@font-face {
  font-family: ExpletusSans;
  font-weight: normal;
  font-style: normal;
  src: local('☺'), url("/assets/fonts/Expletus_Sans/ExpletusSans-Regular.woff") format('woff');
}
@font-face {
  font-family: ExpletusSansBoldItalic;
  font-weight: bold;
  font-style: italic;
  src: local('☺'), url("/assets/fonts/Expletus_Sans/ExpletusSans-BoldItalic.woff") format('woff');
}
```
