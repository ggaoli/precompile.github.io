# CSS预编译
 http://ggaoli.github.io/precompile/
---
## 为什么要学习css预编译
CSS入门简单，深入就比较难，虽然样式简单，但难以维护。需要考虑大量的样式，覆盖、权重和很多!important。
## 什么是 css预处理器

CSS预处理器定义了一种新的语言，其基本思想是，用一种专门的编程语言，为CSS增加了一些编程的特性，将CSS作为目标生成文件，然后开发者就只要使用这种语言进行编码工作。通俗的说，CSS预处理器用一种专门的编程语言，进行Web页面样式设计，然后再编译成正常的CSS文件，以供项目使用。CSS预处理器为CSS增加一些编程的特性，无需考虑浏览器的兼容性问题，例如你可以在CSS中使用变量、简单的逻辑程序、函数等等在编程语言中的一些基本特性，可以让你的CSS更加简洁、适应性更强、可读性更佳，更易于代码的维护等诸多好处。

## css预处理器语言
现今市面上主要有 `Sass`、`Less`、`Stylus` 这三类预处理器语言。

###1、背景介绍
- Sass背景介绍
>Sass是对CSS的语法的一种扩充，诞生于2007年，最早也是最成熟的一款CSS预处理器语言，它可以使用变量、常量、嵌套、混入、函数等功能，可以更有效有弹性的写出CSS。Sass最后还是会编译出合法的CSS让浏览器使用，也就是说它本身的语法并不太容易让浏览器识别，因为它不是标准的CSS格式，在它的语法内部可以使用动态变量等，所以它更像一种极简单的动态语言。
注：Sass官网地址：[http://sass-lang.com][1]

- Less背景介绍
>2009年开源的一个项目，受Sass的影响较大，但又使用CSS的语法，让大部分开发者和设计师更容易上手。
注：LESS的官网：[http://lesscss.org][2]

- Stylus背景介绍
> Stylus，2010年产生，来自于Node.js社区，主要用来给Node项目进行CSS预处理支持，不过Stylus的人气相对于Sass和Less则逊色很多。

注：Stylus官网：[http://learnboost.github.com/stylus][3]
###2、Sass和Less对比

> * 实现方式
Less是基于JavaScript引擎，需要在客户端处理的。<br>
Sass是基于Ruby环境，是在服务器端处理的。<br>
相比之下less环境相对Sass简单
注：很多开发者不会选择LESS因为JavaScript引擎需要额外的时间来处理代码然后输出修改过的CSS到浏览器。关于这个有很多种方式，我选择的是只在开发环节使用LESS。
> * 使用率(热度)
国内前端团队使用LESS的同学会略多于Sass
国外则普遍使用Sass,热度高
> * 功能
Sass较Less略强大一些
> * 已有成熟框架对比
Sass在市面上有一些成熟的框架，比如说`Compass`，而且有很多框架也在使用Sass，比如说Foundation，bootstrap也开始使用sass

###3、Sass和Less语法对比
> * 混入(Mixins)——class中的class；
> * 参数混入——可以传递参数的class，就像函数一样；
> * 嵌套规则——Class中嵌套class，从而减少重复的代码；
> * 运算——CSS中用上数学；
> * 颜色功能——可以编辑颜色；
> * 名字空间(namespace)——分组样式，从而可以被调用；
> * 作用域——局部修改样式；
> * JavaScript 赋值——在CSS中使用JavaScript表达式赋值。

##Sass入门
###Sass环境安装
 编写scss代码，通过sass的工作引擎编译成css代码，最后的部署阶段，其实部署的是生成的css代码，从这个流程可以看出sass并不是万金流，使用命令行也好，使用服务端集成框架也好，使用图形用户界面工具也好，最关键的环节是输入css，从这里也可表现出sass就是帮助我们更快的写出具有高可维护性的css代码<br>

 - koala<br>
koala 是一款桌面程序，支持 less 、 sass 、 coffeescript 即时编译，帮助 web 开发者更高效地使用 less 、 sass 、 coffeescript 开发。
下载： [http://koala-app.com/index-zh.html][4]
 - 命令操作<br>
1.安装ruby环境 官网地址：[http://www.ruby-lang.org/en/][5]
下载RubyInstaller后记得勾选 add ruby executables to your PATH 选项
2.更改ruby包的sources
   -  **gem sources --remove https://rubygems.org/**
   -  **gem sources --add https://ruby.taobao.org/** （如果你系统不支持https，请将淘宝源更换成：gem sources -a http://gems.ruby-china.org）
   - **gem install sass**
   - **gem update**(更新ruby程序)
   - **gem install sass --vertion=3.3**
   - **gem list** (列出本地安装的所有ruby程序包)
   - **gem uninstall sass --vertion=3.3.0**(删除相应的程序包)
   - **vim main.scss**(创建scss文件)
   - **sass main.scss main.css**(将.scss文件编译成.css文件)
   - mkdir workspace(创建工作区)
   - cd workspace(进入工作区)

###Sass语法入门
####sass和scss的区别：
sass有两种语法，一种是`sass`（缩排写法）,这种语法的文件需要以.sass扩展名。另一种则是在sass的基础上，对css3扩从的`scss`，这种语法的文件需要以.scss扩展名。<br>
第一种sass语法，是不使用花国号，对空格 换行 敏感，通过缩排的方式来表达选择符，语法特点是更加简洁，像习惯编写ruby phthon的人可以可能会比较喜欢。<br>
第二种scss语法，延续之前的css语法，大多数地道的前端团队会选择scss
```
/*sass语法*/
h3
  color: #eee
  font-size:12px
  
/*scss语法*/
h3{
  color: #eee;
  font-size:12px;
}
```
使用命令行转换格式： sass-convert main.scss main.sass
在开始之前，我们先是用compass创建一个测试项目
compass create compass-syntax
监听当前目录下sass文件的变化
cd compass-syntax
compass watch
####嵌套(Nesting)
```
/***选择器嵌套***/
 .recom-r{
      ul{
        li{
        color:red;
          a{
            border: 1px 0  0 #ddd;
          }
          &:nth-child(1) a,&:nth-child(2) a{
            border-right:none;
          }
          &:nth-child(3) a,&:nth-child(4) a{
            border-bottom:none;
          }
        }
      }
    }
    //编译为
    .recom-r ul li{
     color:red;}
    .recom-r ul li a {
     border-bottom: 1px solid #ddd; }
   .recom-r ul li:nth-child(1) a, .products-recom .modcon .recom-r ul li:nth-child(2) a {
     border-right: none; }
  .recom-r ul li:nth-child(3) a, .products-recom .modcon .recom-r ul li:nth-child(4) a {
     border-bottom: none; }
     
     
     /***属性嵌套嵌套***/
     .abc{
      border:{
        style:solid;
        left:{
         width:4px;
         color:red;
        }
        right{
          width:1px;
          color:blue;
        }
      }
     }
     //编译为
     .abc{
       border-style: solid;
       border-left-width: 4px;
       border-left-color: red;
       border-right-width: 1px;
       border-right-color: blue; 
     }
```

####导入 @import
```
@import "reset" //这里是简写 _reset.scss,以下划线开头的scss文件默认不自动编译出来，是专门用来导入的文件
```

####变量 $
```
/***默认变量***/
$default-color: #2898fd;
body{
  color:$default-color;
}
//解析如下
body{
  color:#2898fd;
}
/***多值变量***/
$a-color:red blue yellow;
a{
  &:hover{color:$a-color,1}
  &:active{color:$a-color,2}
}
//解析如下
a:hover{color:red}
a:active{color:blue}

注：compass中采用中划线的方式命名
```

####注释
        /* */  标准的css注释方式 
        // 这种单行注释是不会解析到css文件中 
        
####混合(mixin)        
```
@mixin transition($transition){
  -webkit-transition: $transition;
  -moz-transition: $transition;
  -o-transition: $transition;
  transition: $transition;
}
a{
 @include transition(all 0.2s linear);
}
//编译为
a{
  -webkit-transition: all 0.2s linear;
  -moz-transition: all 0.2s linear;
  -o-transition: all 0.2s linear;
  transition: all 0.2s linear;
}
```
####运算
```
body{
  width:100%;
}
article{
  width:600px / 1200px *100%;
}
//编译为
body{
  width:100%;
}
article{
  width:50%；
}
```
####扩展/继承@extent
```
.a{
  color:red;
  font-size:12px;
  padding:10px;
}
.b{
   @extent .abc;
   margin:10px;
}
.c{
   @extent .abc;
  margin:20px;
}
//编译为
.a, .b , .c{
  color:red;
  font-size:12px;
  padding:10px;
}
.b{
   margin:10px;
}
.c{
   margin:20px;
}
```
####占位选择器%
```
%clear{
  &:before,
  &:before, {
    content: "";
    display: table;
    font: 0/0 a;
  }
  &:after {
    clear: both;
  }
}
.clearfix{
  @extent %clear;
}
.row{
  @extent %clear;
  width:1200px;
  margin:0 aut0;
}
//编译为
.row, .clearfix:before, .clearfix:after{
    content: "";
    display: table;
    font: 0/0 a;
}
 .clearfix:after, .row:after{
    clear: both;
 }
 .row{
  width:1200px;
  margin:0 aut0;
 }
```
####控制指令
```
/******@if******/
$type: monster;
p {
  @if $type == ocean {
    color: blue;
  } @else if $type == matador {
    color: red;
  } @else if $type == monster {
    color: green;
  } @else {
    color: black;
  }
}
//编译为
p {
    color: green; 
  }
  
/******@while******/
$i: 6;
@while $i > 0 {
  .item-#{$i} { width: 2em * $i; }
  $i: $i - 2;
}
//编译为
.item-6 {
    width: 12em;
}
.item-4 {
    width: 8em;
}
.item-2 {
    width: 4em; 
}

```
####选择器
> 子组合选择器 ` > ` :选择一个元素的直接子元素
>同层相邻组合选择器 `+` :选择紧跟在后面的同级元素
>同层全体组合选择器 `~` :选择所有跟在后的同层元素

####颜色函数
```
$ sass -i
>> rgb(200,40,88) //根据r:200,g:40,b:88计算出一个十六进制颜色值
得出：#c82858
>> rgba(#c82858,.65) //根据#c82858的65%透明度计算出一个rgba颜色值
得出：rgba(200, 40, 88, 0.65)
>> red(#c82858) //从#c82858颜色值中得到红色值200
得出：200
>> green(#c82858) //从#c82858颜色值中得到绿色值40
得出：40
>> blue(#c82858) //从#c82858颜色值中得到蓝色值88
得出：88
>> mix(#c82858,rgba(200,40,80,.65),.3) //把#c82858和rgba(200,40,88,.65)两颜色按比例混合得到一个新颜色
rgba(200, 40, 80, 0.65105)
>> lighten(red,10%)//将red颜色安装亮度值增加10%
得出：#ff3333
>> darken(red,10%)//将red颜色安装亮度值变暗10%
得出：#cc0000
>>complement(red)//获取red颜色的补充色
得出#00ffff
...
```
**注：详细参见[Sass官网][6]**

##Compass框架
###介绍
>Compass是一个强大的Sass框架，能够利用它写出可维护性更高的样式表。
Compass由三个主要部分组成：混合器和实用工具的类库，能够集成到应用开发环境中的开发系统，以及一个用于构建框架和扩展的平台。<br>
Compass自身包含了很多由Sass混合器和函数构成的模块，所有的这些模块在Compass的官网上都有详细的说明和示例。<br>
这些库会帮助你解决跨浏览器兼容问题，以及提供给你很多已经被证明过的优秀模式，比如说重置、网格布局、列表样式、表格辅助器等。
注：[Comapass官网][7]
###安装与使用

使用命令行：  gem install compass（这样就创建好了）
.e.g.<br>
比如说先创建一个文件夹 mkdir compasstext,
点击进入这个文件 cd compasstext,
创建compass项目的文件 compass create mallApp,
点击进入这个文件 cd mallApp,
这个时候我们想要清楚 可以输入 compass clean
如果想重新开始编译 可以输入 compass compile
> 常见的命令操作
自动编译：compass watch
清除： compass clean
重新开始编译：compass compile


###安装

##Sass调试
###1、Koala调试方式
> 1.Koala上点击相应的文件，然后就会出现右边的编译选项，即可选择是否开启source map，debug info <br>
> 2.打开Chrome浏览器，F12打开调试面板，点击调试面板右上角的齿轮图标打开设置，在general选项中勾选Enable CSS source map 和 Auto-reload generated CSS<br>
> 3.开启--sourcemap编译，f12打开调试面板，就可以看到原先右边的css文件变成了我们现在的scss文件<br>
> 4.点击scss文件，会跳到source里面的scss源文件，现在可以在里面进行修改，修改完成后可以右键选择save或save as命令，然后替换我们本地的scss源文件，刷新chrome就可以看到变化（注意，解析样式需要一定时间）。以后只要ctrl+s保存修改就可以在浏览器中看到修改效果了。

###2、命令行调试方式


  [1]: http://sass-lang.com
  [2]: http://lesscss.org
  [3]: http://learnboost.github.com/stylus
  [4]: http://koala-app.com/index-zh.html
  [5]: http://www.ruby-lang.org/en/
  [6]: http://sass-lang.com/
  [7]: http://compass-style.org
