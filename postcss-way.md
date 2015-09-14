# Практика PostCSS
!favicon ./favicon.ico
!theme   ../showbox-ai
!lang    ru

[Андрей Ситник](http://sitnik.ru/), [Злые марсиане](https://evilmartians.com/)

<style>
.slide.cover {
    h2 {
        color: white;
    }
}
.slide.with-l-code {
    pre {
        font-size: 80%;
    }
}
.slide.with-2-sides {
    pre, p {
        float: left;
        clear: left;
        width: 350px;
        &:nth-of-type(2) {
            float: right;
            clear: right;
        }
    }
}
</style>

## Практика **PostCSS**

!image postcss.svg

Андрей Ситник, Злые марсиане

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
  font-size: 116%;
  margin-top: 25px;
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

## Наши клиенты

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

## Наш опенсорс

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

## *Глава 1* Что такое PostCSS?
!cover start.jpg

## 1 000 000 загрузок в месяц

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
</div>

<style>
.stat {
  margin-top: 100px;
  height: 300px;
  position: relative;
}
.line {
  display: inline-block;
  background: #0080e0;
  width: 34px;
}
</style>

## Пользователи PostCSS

<p>

!image yandex.svg
!image wordpress.svg
!image taobao.svg
!image vk.svg

</p>

<style>
p {
  padding-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
img {
  max-height: 90px;
  max-width: 320px;
  padding: 40px;
}
</style>

## Схема работы

<div class="postprocessing">
    <div class="step is-css">
        CSS
        <span class="position">
            <div class="note">карта кода</div>
        </span>
    </div>
    <div class="step is-important">Парсер</div>
    <div class="step">Плагин</div>
    <div class="step">Плагин</div>
    <div class="step is-important">Стригифайр</div>
    <div class="step is-css">
        Новый CSS
        <span class="position">
            <div class="note">новая карта</div>
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
.slide:first-child:after {
  display: none;
}
.step.is-css {
  padding: 0;
  height: auto;
  line-height: 1.1;
  border: none;
}
.step.is-css:after {
  display: none;
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

## Использование

```js
gulp.task('css', () => {
    let postcss = require('gulp-postcss');

    return gulp.src('src/*.css')
        .pipe( ***postcss([plugin1, plugin2])*** )
        .pipe( gulp.desc('build/') );
});
```

## *Глава 2* Чем не является PostCSS
!cover monkeys.jpg

<style>
h2 {
  text-shadow: 1px  1px 1px black, -1px  1px 1px black,
               1px -1px 1px black, -1px -1px 1px black;
}
</style>

## 1. Не конкурент Sass

```js
.pipe( ***sass***() )
.pipe( ***postcss***([
    require('cssnext'),
    require('postcss-autoreset'),
    require('postcss-font-magician'),
    require('postcss-assets'),
    require('grid'),
    require('cssnano')
]) )
```

## 2. Не только полифил «CSS4»
!type with-l-code

```css
@define-mixin hover $color {
    background-color: $color;
    &:hover {
        background-color: color($color l(+5%));
    }
    &:active {
        background-color: color($color l(-5%));
    }
}
```

## 3. Не только трансформация CSS

```js
postcss([
    require('***postcss-flexbugs-fixes***'),
    require('***stylint***'),
    require('***doiuse***'),
    require('postcss-browser-reporter')
])
```

## 4. Нет одного пути PostCSS

<figure>
  <blockquote>
    <p>
      Свобода ничего не стоит, если она не включает
      в себя свободу ошибаться
    </p>
  </blockquote>
  <figcaption>— Махатма Ганди</figcaption>
</figure>

## *Шаг 1* Изоляция
!cover alone.jpg

## Компонентный подход

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

## Проблемы

1. Конфликт селекторов
2. Наследование стилей

## *Проблема 1* Конфликт селекторов
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

## *Решение 1* [postcss-bem](https://github.com/ileri/postcss-bem)
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

## *Решение 2* [CSS Modules](https://github.com/css-modules/css-modules)
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

## CSS Modules

```js
import ***styles*** from './logo.css';

class Logo extends React.Component {
    render() {
        return <div className={ ***styles.name*** }>Our</div>;
    }
}
```

## Что выбрать

**CSS Modules:**

- Виджеты для других сайтов
- Рендер на клиенте

**БЭМ**

- Статичные сайты

## *Проблема 2* Наследование свойств

```html
<Header>
    ***background: black***
    <Logo>
        ***color: black***
    </Logo>
</Header>
```

## *Решение* [postcss-autoreset](https://github.com/maximkoretskiy/postcss-autoreset)
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

## [postcss-initial](https://github.com/maximkoretskiy/postcss-initial) — полифил для IE
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

## Идеальная изоляция

- CSS Modules
- `postcss-autoreset`
- `postcss-initial`

## *Шаг 2* Полифилы будущего
!cover future.jpg

## *cssnext* Автопрефиксер
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

## *cssnext* Свои медиа-выражения

```css
@custom-media --phones (width ***<=*** 1000px);

@media (***--phones***) { }
```

## *cssnext* Свои селекторы

```css
@custom-selector :--button button, input[type=submit];

***:--button*** { }
```

## Новые селекторы

```css
.menu ***:any-link*** {
    color: white
}

.item***:not***(:first-child, .is-special) {

}
```

## [postcss-will-change](https://github.com/postcss/postcss-will-change)

```css
.rotator {
    ***will-change***: transform;
}
```

## *Шаг 3* Магия
!cover magic.jpg

<style>
h2 {
    position: absolute;
    bottom: 80px;
    text-shadow: 1px  1px 1px black, -1px  1px 1px black,
                 1px -1px 1px black, -1px -1px 1px black;
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

## *Опционально* [RTLCSS](https://github.com/MohammadYounes/rtlcss)

!image rtlcss.png

<style>
img {
    display: block;
    width: 700px;
    margin: 0 auto;
}
</style>

## *Шаг 4* Шаблонизация
!cover lang.jpg

<style>
h2 {
    color: black;
}
</style>

## *Правило 1* Используйте пакеты плагинов

```js
postcss([
    require('***precss***')
]);
```

## PreCSS

```css
***$blue:*** color(#cc00000 l(+10%));
@define-mixin icon color { }

.logo {
    ***&***.is-big {
        ***@mixin*** icon $blue;
    }
}
```

## Выбор шаблонизатора
!type with-2-sides

**Старый проект:**

**Новый проект проект:**

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
