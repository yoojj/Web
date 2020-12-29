# CSS Preprocessor
: CSS 전처리기   
: CSS 확장 사용          
: 믹스인, 중첩, 변수, 구문 등 기능을 사용하고 컴파일러나 트랜스파일러를 통해 CSS 파일로 변환     


**종류**   
- [SASS](#sass)
- [LESS](#less)
- Stylus
- CSS-Crush
- ...


**도구**  
- [PostCSS](#postcss)



## SASS
: ruby와 node 기반 컴파일러 지원    
: sass와 scss 두 가지 문법 제공         


```bash
# ruby sass
$ gem install sass
$ sass -v


# node sass
$ npm install node-sass
$ node-sass -v
```



## LESS
: 변수, 함수, 연산, 중첩, 스코프 등 스크립트 특징 확장  

- SimpLESS
- Crunch


```html
<link rel="stylesheet/less" href="style.less">
<script src="less.min.js"></script>
```



## PostCSS
: node 기반 플러그인으로 전처리기처럼 사용 가능        
: 필요한 기능에 맞는 플러그인을 선택해 사용    

**플러그인 목록**  
https://github.com/postcss/postcss/blob/master/docs/plugins.md


```bash
# postcss-cli
$ npm install postcss-cli

# autoprefixer 사용
$ postcss --use autoprefixer -o example.css ./css/*.css


# + gulp
$ npm install gulp-postcss autoprefixer

## postcss.config.js
var gulp = require('gulp');
var postcss = require('gulp-postcss');
var autoprefixer = require('autoprefixer');

gulp.task('css', () => {
    const plugins = [
        autoprefixer({browsers: ['last 1 version']}),
    ]
    return gulp.src('./css/*.css')
        .pipe(postcss(plugins))
        .pipe(gulp.dest('생성'));
});


# + webpack
$ npm install postcss postcss-loader autoprefixer   

## postcss.config.js
module.exports = {
    plugins: [
        require('autoprefixer')({
            'browsers': ['last 1 versions']
        })
    ]
}
```



[top](#)
