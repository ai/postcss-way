# PostCSS in Practice
!favicon ./favicon.ico
!theme   ../showbox-ai
!lang    en

[Andrey Sitnik](http://sitnik.ru/en), [Evil Martians](https://evilmartians.com/)

<style>
.slide.cover {
    h2 {
        color: white;
    }
}
.slide.with-shadow {
    h2 {
        text-shadow: 1px  1px 1px black, -1px  1px 1px black,
                     1px -1px 1px black, -1px -1px 1px black;
    }
}
.slide.with-l-code {
    pre {
        font-size: 80%;
    }
}
.slide.with-2-sides {
    pre, p, ul, ol {
        float: left;
        clear: left;
        width: 350px;
        &:nth-of-type(2) {
            float: right;
            clear: right;
        }
    }
}
.rule {
    padding: 15px 20px;
    background: #fafaa2;
    margin: 0 -20px 48px -20px;
}
</style>

## **PostCSS** in Practice

!image postcss.svg

Andrey Sitnik, Evil Martians

<style>
img {
    position: absolute;
    top: 93px;
    right: 130px;
    width: 195px;
}
h2 {
    font-size: 80px;
    letter-spacing: 2px;
    position: relative;
    top: 10px;
}
h2 strong {
    display: block;
    font-size: 127%;
    margin: 15px 0 10px 0;
    position: relative;
    left: -4px;
}
p {
    font-family: "Open Sans Light";
    font-style: normal;
    position: absolute;
    bottom: 50px;
}
&::after {
    visibility: hidden;
}
</style>

##

!image martians.svg

<style>
img {
    display: block;
    width: 320px;
    margin: 80px auto 0 auto;
}
</style>

## Our Clients

!image gett.png
!image ebay.svg
!image groupon.svg

<style>
img {
    display: block;
    margin: 0 auto 55px auto;
}
img:nth-child(2) {
    margin-top: -35px;
    height: 120px;
}
img:nth-child(3) {
    width: 220px;
}
img:nth-child(4) {
    width: 365px;
}
</style>

## Our Open Source

<p>

!image autoprefixer.svg https://github.com/postcss/autoprefixer
!image postcss.svg https://github.com/postcss/postcss
!image evil-icons.svg http://evil-icons.io/
!image size-marks.svg https://github.com/romashamin/Size-Marks-PS

</p>

<style>
p {
    margin: 120px -30px 0 -30px;
    text-align: center;
}
a {
    float: left;
    display: block;
    background: rgba(0, 128, 224, 0);
}
a:hover {
    background: rgba(0, 128, 224, 0.1)
}
img {
    display: block;
    padding: 30px;
}
a:nth-child(1) img {
    width: 195px;
}
a:nth-child(2) img {
    width: 150px;
}
a:nth-child(3) img {
    width: 125px;
    position: relative;
    top: -15px;
}
a:nth-child(4) img {
    width: 140px;
}
</style>

## *Part 1* What is PostCSS?
!cover start.jpg

## Old Preprocessors

```css
a {
    ***<%=*** include clickable ***%>***
    color: ***<%=*** $link-color ***%>***;
}
```

## Inside PostCSS

<div class="postprocessing">
    <div class="step is-css">
        CSS
        <span class="position">
            <div class="note">source map</div>
        </span>
    </div>
    <div class="step is-important">Parser</div>
    <div class="step">Plugin</div>
    <div class="step">Plugin</div>
    <div class="step is-important">Stringifier</div>
    <div class="step is-css">
        New CSS
        <span class="position">
            <div class="note">new source map</div>
        </span>
    </div>
</div>

<style>
.postprocessing {
    position: relative;
    margin: 0 auto;
    width: 210px;
    top: -40px;
}
.step {
    height: 50px;
    line-height: 50px;
    border: 1px solid;
    text-align: center;
    position: relative;
    width: 100%;
    margin-top: 32px;
    margin-left: 3px;
    font-size: 115%;
}
.step:after {
    content: "↓";
    font-size: 70%;
    color: black;
    position: absolute;
    top: -46px;
    left: 97px;
}
.step:first-child {
    margin-top: 0;
}
.step:first-child:after {
    display: none;
}
.step.is-css {
    padding: 0;
    height: auto;
    line-height: 1.1;
    border: none;
}
.step.is-css:after {
    top: -27px;
}
.step.is-important {
    padding: 0;
    color: #0080e0;
    border-width: 4px;
    margin-left: 0;
    font-weight: bold;
}
.step.is-important:after {
    top: -48px;
}
.position {
    position: relative;
}
.note {
    position: absolute;
    top: 11px;
    left: 15px;
    font-size: 55%;
    white-space: nowrap;
}
</style>

## Usage

```js
gulp.task('css', () => {
    let postcss = require('gulp-postcss');

    return gulp.src('src/*.css')
        .pipe( ***postcss([ plugin1, plugin2 ])*** )
        .pipe( gulp.desc('build/') );
});
```

## [postcss-nested](https://github.com/postcss/postcss-nested)
!type with-2-sides

```css
.block {
    ***&_title*** {
        font-size: 200%;
    }
}
```

```js
***.block_title*** {
    font-size: 200%;
}
```

## *W3C Draft* [postcss-media-minmax](https://github.com/postcss/postcss-media-minmax)
!type with-2-sides

```css
@media (width ***<=*** 600px) {
    …
}
```

```css
@media (***max-***width: 600px) {
    …
}
```

## Why?

Break old preprocessors limits:

* Autoprefixer and polyfills
* Linters
* New syntaxes
* New ideas

## **1 000 000** downloads per month

<div class="stat">
    <div class="line" style="height: 0.67%"></div>
    <div class="line" style="height: 1.11%"></div>
    <div class="line" style="height: 2.56%"></div>
    <div class="line" style="height: 4.3%"></div>
    <div class="line" style="height: 5.41%"></div>
    <div class="line" style="height: 9.22%"></div>
    <div class="line" style="height: 13.1%"></div>
    <div class="line" style="height: 15.94%"></div>
    <div class="line" style="height: 20.56%"></div>
    <div class="line" style="height: 24.85%"></div>
    <div class="line" style="height: 27.34%"></div>
    <div class="line" style="height: 26.79%"></div>
    <div class="line" style="height: 33.45%"></div>
    <div class="line" style="height: 43.43%"></div>
    <div class="line" style="height: 48.81%"></div>
    <div class="line" style="height: 59.05%"></div>
    <div class="line" style="height: 71.5%"></div>
    <div class="line" style="height: 75.56%"></div>
    <div class="line" style="height: 89.25%"></div>
    <div class="line" style="height: 100%"></div>
    <div class="line" style="height: 121.14%"></div>
</div>

<style>
.stat {
    margin-top: 50px;
    height: 280px;
    position: relative;
}
.line {
    display: inline-block;
    background: #0080e0;
    width: 32px;
}
</style>

## PostCSS Users

<p>

!image google.svg
!image wordpress.svg
!image taobao.svg
!image webpack.png

</p>

<style>
p {
    padding-top: 20px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}
img {
    position: relative;
    max-height: 90px;
    max-width: 320px;
    padding: 40px;
    &:nth-of-type(4) {
        top: -30px;
        max-height: 180px;
    }
}
</style>

## *Part 2* Plugins
!cover connect.jpg
!type  with-shadow

## Plugins Set

```js
postcss([
    require('autoprefixer')({
        browsers: 'last 2 version'
    }),
    require('postcss-cssnext'),
    require('precss')
])
```

## *Problem* Implicit

```css
.icon {
    top: ***center***;
}
```

## *Solution* [postcss-use](https://github.com/postcss/postcss-use)

```css
***@use postcss-center;***

.icon {
    top: center;
}
```

## Rule 1

<div class="rule">
All plugins with custom syntax should be added by postcss-use
</div>

- Global: Autoprefixer, cssnext, postcss-url
- `@use`: lost, postcss-center, postcss-circle

## Rule 2

<div class="rule">
Start from plugins packs
</div>

- `precss`: Sass like features
- `cssnext`: polyfills for “CSS 4”
- `oldie`: IE 8 support

## *Part 3* Isolation
!cover alone.jpg

## Rule 3

<div class="rule">
Use PostCSS for maintable code, not only for syntax sugar
</div>

## CommonJS

```js
var moment = ***require***('moment');
```

## Components

<ul>
    <li>
        <code>logo/</code>
        <ul>
            <li><code>logo.js</code></li>
            <li><code>logo.css</code></li>
            <li><code>logo.svg</code></li>
        </ul>
    </li>
    <li>
        <code>header/</code>
        <ul>
            <li><code>header.js</code></li>
            <li><code>header.css</code></li>
        </ul>
    </li>
</ul>

## Build CSS and JS together

- webpack
- Gulp with Browserify

## Problems

1. Selectors conflict
2. Inherited properties

## *Problem 1* Selectors Conflict
!type with-2-sides

`logo.css`

`header.css`

```css
***.name*** {
    color: black;
}
```

```css
***.name*** {
    color: gray;
}
```

## *Solution 1* [postcss-bem](https://github.com/ileri/postcss-bem)
!type with-2-sides

```css
***@b*** Logo {
    ***@e*** name {
        color: gray;
    }
}
```

```css
.***Logo***-name {
    color: gray
}
```

## *Solution 2* [CSS Modules](https://github.com/css-modules/css-modules)
!type with-2-sides

```css
.name {
    color: gray;
}
```

```css
.***Logo***__name__***sVK0p*** {
    color: gray
}
```

## CSS Modules in JS

```js
import ***styles*** from './logo.css';

class Logo extends React.Component {
    render() {
        return <div className={ ***styles.name*** }>We</div>;
    }
}
```

## Choice

**CSS Modules:**

- Client-side render
- Third-part widgets

**BEM**

- Static websites

## *Problem 2* Inherited Properties

```html
<Header>
    ***background: black***
    <Logo>
        ***color: black***
    </Logo>
</Header>
```

## *Problem 3* Third-Part Widgets

```css
* {
    box-sizing: border-box;
}
div {
    margin-top: 10px;
}
```

## *Solution* [postcss-autoreset](https://github.com/maximkoretskiy/postcss-autoreset)
!type with-2-sides

```css
.logo {
    color: black;
}
.logo--big {
    width: 200px;
}
```

```css
.logo {
   *** all: initial; ***
    color: black;
}
.logo--big {
    width: 200px;
}
```

## *W3C Draft* [postcss-initial](https://github.com/maximkoretskiy/postcss-initial) — IE support
!type with-2-sides

```css
.logo {
    all: initial;
}
```

```css
.logo {
    color: black;
    background: white;
    box-sizing: content-box;
    line-height: normal;
    text-shadow: none;
    vertical-align: baseline;
    white-space: normal;
```

## The Best Isolation

- CSS Modules
- `postcss-autoreset`
- `postcss-initial`

## *Part 4* Explicit Code
!cover lang.jpg

<style>
h2 {
    color: black;
}
</style>

## Rule 4

<div class="rule">
Use PostCSS to reduce magic numbers in CSS
</div>

## [postcss-assets](https://github.com/borodean/postcss-assets)

Image sizes:

```css
.icon {
    width: ***width***('logo.png');
    height: ***height***('logo.png');
    background: inline('logo.png');
}
```

## [postcss-property-lookup](https://github.com/simonsmith/postcss-property-lookup)

Reference to other property:

```css
.icon {
    width: 20px;
    height: ***@width***;
}
```

## [postcss-contrast](https://github.com/stephenway/postcss-contrast)

Black or white font for best contrast with background:

```css
.menu {
    background: #dd3735;
    color: ***contrast***(@background);
}
```

## *W3C Draft* [postcss-custom-media](https://github.com/postcss/postcss-custom-media)

```css
@custom-media --phones (width <= 700px);
@custom-media --hidpi  (resolution >= 2dppx);

@media (***--phones***) { }
@media (***--phones***) and (***--hidpi***) { }
```

## Rule 5

<div class="rule">
Use PostCSS to hide hacks
</div>

## [autoprefixer](https://github.com/postcss/autoprefixer)
!type with-2-sides

```css
:fullscreen { }
```

```css
:***-webkit-***full-screen { }
:***-moz-***full-screen { }
:***-ms-***fullscreen { }
:fullscreen { }
```

## [postcss-color-rgba-fallback](https://github.com/postcss/postcss-color-rgba-fallback)
!type with-2-sides

```css
.popup {
    background:
        ***rgba***(153, 221, 153, 0.8);
}
```

```css
.popup {
    background: ***#99dd99***; /* IE 8 */
    background:
        rgba(153, 221, 153, 0.8);
}
```

<style>
pre {
    font-size: 80%;
}
</style>

## [postcss-font-magician](https://github.com/jonathantneal/postcss-font-magician)
!type with-2-sides

```css
body {
    font-family: ***Alice***;
}
```

```css
@font-face {
    font-family: Alice;
    font-style: normal;
    font-weight: 400;
    src: local("Alice"),
         url("//fonts.gstatic.com/….woff")
             format("woff");
}
body {
    font-family: Alice;
}
```

<style>
pre:nth-of-type(2) {
    font-size: 70%;
}
</style>

## [postcss-svg-fallback](https://github.com/justim/postcss-svg-fallback)
!type with-2-sides

```css
.icon {
    background: url(logo.svg);
    background-size: 20px 20px;
}
```

```css
.icon {
    background: url(logo.svg);
    background-size: 20px 20px;
}

.no-svg.icon {
    background: url(***logo-20x20.png***);
}
```

<style>
pre {
    font-size: 80%;
}
</style>

## [postcss-svg](https://github.com/Pavliko/postcss-svg)

```css
.icon {
    background: ***svg***('logo.svg', '***[fill]: #c00***');
}
```

## *Part 6* Linters
!cover control.jpg

## Rule 6

<div class="rule">
Use PostCSS for lint CSS, not only to transform it
</div>

## [stylelint](http://stylelint.io/)

More than 85 rules:

```js
"rules": {
    ***"indentation"***:          2,
    ***"number-leading-zero"***:  2,
    ***"color-no-invalid-hex"***: 2
}
```

## [postcss-flexbugs-fixes](https://github.com/luisrudge/postcss-flexbugs-fixes)
!type with-2-sides

IE 11 flexbox issues:

```css
.foo {
    flex: 1;
}
```

```css
.foo {
    flex: 1 1 0%;
}
```

## [doiuse](https://github.com/anandthakker/doiuse)

```
main.css:13:3: Pointer events not supported by: IE (9,10)
```

## [postcss-browser-reporter](https://github.com/postcss/postcss-browser-reporter)

!image reporter.png

<style>
img {
    display: block;
    width: 780px;
    margin: 0 auto;
}
</style>

## *Part 7* Dessert
!cover food.jpg
!type  with-shadow

## [postcss-write-svg](https://github.com/jonathantneal/postcss-write-svg)

```css
.arrow {
    ***@svg*** {
        polygon {
            fill: green;
            points: 50,100 0,0 0,100;
        }
    }
}
```

## [RTLCSS](https://github.com/MohammadYounes/rtlcss)

!image rtlcss.png

<style>
img {
    display: block;
    width: 700px;
    margin: 0 auto;
}
</style>

## *Part 8* Summary
!cover wow.jpg
!type  with-shadow

## PostCSS is not Sass Enemy
!type with-2-sides

**Legacy project:**

**New project:**

```js
.pipe( ***sass***() )
.pipe( postcss([
    ...plugins
]) )
```

```js
.pipe( postcss([
    ***precss***,
    ...plugins
]) )
```

## The Right Way to Use PostCSS

1. Use `postcss-use` for plugins with custom syntax
2. Start with plugins packs
3. Write isolated components
4. Reduce “magic numbers”
5. Hide hacks
6. Use Linters

##
!cover fin.jpg
!type  with-shadow

## Links

* [github.com/postcss/postcss](https://github.com/postcss/postcss)
* [@postcss](https://twitter.com/postcss)
* [@andreysitnik](https://twitter.com/andreysitnik)
* [@evilmartians](https://twitter.com/evilmartians)

!image martians.svg

<style>
&::after {
    visibility: hidden;
}
li {
    font-size: 180%;
    line-height: 1;
    margin-bottom: 40px;
    &::before {
        visibility: hidden;
    }
    &:first-child {
        margin-top: 70px;
    }
    &:nth-child(3) {
        margin-top: 90px;
    }
}
img {
    position: absolute;
    bottom: 70px;
    right: 100px;
    width: 250px;
}
</style>
