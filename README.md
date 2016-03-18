## 百度ife春季训练营（i can fly）团队

```javascript
//基础设施==
var gulp = require('gulp'),
    plumber = require('gulp-plumber');
var uglify = require('gulp-uglify'), //js压缩
    webpack = require('webpack-stream'), //webpack打包加入gulp流处理
    webpackConfig = require('./webpack.config');
gulp.task("pagesBuild", function() {
    gulp.src('static/js/**/*.js')
        .pipe(plumber())//错误信息处理
        .pipe(webpack(webpackConfig))//采用webpack的形式打包，后面会讲到
        .pipe(uglify())//JS压缩混淆
        .pipe(gulp.dest(BUILDDIR + '/js'))//输出的构建目录
});
```

## 说明：
### 自动化构建
* 目前选用gulp作为构建工具,请在目录下运行
```
npm install
gulp dev
```
目前选用插件
* connect（自动刷新）
* del（文件删除）
* gulp-livereload（自动刷新页面）
* gulp-plumber（错误处理）  
* gulp-uglify（js压缩、混淆）
* gulp-less（less编译）
* gulp-csso（css压缩）
* gulp-autoprefixer（css属性浏览器前缀添加）
* gulp-file-include（文件包含）
* webpack-stream（webpack流处理）

### 代码处理
#### CSS
* 采用LESS进行预处理
* [引入百度EST的LESS mixin库（点击查看文档）](https://github.com/ecomfe/est/blob/dev/doc/api.md) 

#### JS
* 采用webpack进行JS打包处理
* 功能模块放在static/js/modules,页面模块放到static/js/pages


### 任务
* [任务一：面向零基础的HTML代码编写](https://github.com/fe-icanfly/task1)
* [任务二：基于任务1的HTML代码，实现简单的CSS代码编写](https://github.com/fe-icanfly/task2)
* [任务三：HTML、CSS布局入门，三栏式布局的实践](https://github.com/fe-icanfly/task3)
* [任务四：HTML、CSS布局深入，定位和居中问题的实践](https://github.com/fe-icanfly/task4)
* [任务五：基于任务1的HTML代码，实现一个稍微复杂的CSS代码编写](https://github.com/fe-icanfly/task5)
* [任务六：按照设计图，通过HTML/CSS实现一个像报纸杂志一样的页面布局排版](https://github.com/fe-icanfly/task6)
* [任务七：按照设计图，通过HTML/CSS实现一个产品官网](https://github.com/fe-icanfly/task7)
* [任务八：网格/栅格化布局学习与实践](https://github.com/fe-icanfly/task8)
* [任务九：按照设计图，通过HTML/CSS实现一个复杂的业务系统页面](https://github.com/fe-icanfly/task9)
* [任务十：学习和练习Flex布局](https://github.com/fe-icanfly/task10)
* [任务十一：移动Web开发入门，按照设计稿实现一个移动端的页面](https://github.com/fe-icanfly/task11)
* [任务十二：CSS 3新特性的小练习](https://github.com/fe-icanfly/task12)

### 这十二个任务并非所有人都要去完成，而是需要大家按照自己当前的能力水平来合理评估和选择。
* 对于零基础的同学而言，建议路径为：任务1-2-3-4-5-6/7（/表示或）
* 对于有一定基础，但没做过完整页面的同学，建议路径为：3-4-5-6/7-8-9
* 对于有过页面实践，但没做过太复杂页面的同学，建议路径为：3-4-6/7-8-9
* 对于已经经验很丰富的同学，可以直接做：7-9
* 任务10-11提供给对移动端开发有兴趣的同学进行挑战
* 任务12提供给初学者，并且对CSS 3各种新特性有兴趣的同学进行挑战
