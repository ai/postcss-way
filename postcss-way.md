# Практика PostCSS
!favicon ./favicon.ico
!theme ../showbox-ai

[Андрей Ситник](http://sitnik.ru/), [Злые марсиане](https://evilmartians.com/)

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

<style>
h2 {
  color: white;
}
</style>

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
  color: white;
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

## 3. Не только трансформация CSS

```js
postcss([
    require('***postcss-flexbugs-fixes***'),
    require('***stylint***'),
    require('***doiuse***'),
    require('postcss-browser-reporter')
])
```
