# learn-gulp
###使用node安装下面的库

node install gulp gulp-uglify gulp-minify-css gulp-imagemin
```js
//引入库
var gulp = require('gulp'),
	uglify = require('gulp-uglify'),
	minifyCSS = require('gulp-minify-css'),
	imagemin = require('gulp-imagemin')
    

//压缩css
gulp.task('css', function () {
    gulp.src('src/**/*.css')
        .pipe(minifyCSS())
        //压缩的目标位置
        .pipe(gulp.dest('dist'))
})

// 压缩图片
gulp.task('images', function () {
    gulp.src('images/**/.jpg')
        .pipe(imagemin({
            progressive: true
        }))
        .pipe(gulp.dest('dist'))
});

//压缩js
gulp.task('js', function () {
     gulp.src('src/**/*.js')
		.pipe(uglify())
        .pipe(gulp.dest('dist'))
})

//默认执行的任务
gulp.task('default', ['js','css','images']);
```
