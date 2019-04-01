## 缩进
使用 soft tab（4个空格）。
```
.element {
    position: absolute;
    top: 10px;
    left: 10px;
    border-radius: 10px;
    width: 50px;
    height: 50px;
}
```

## 分号
每个属性声明末尾都要加分号。
```
.element {
    width: 20px;
    height: 20px;
    background-color: red;
}
```

## 空格
- 以下几种情况不需要空格：
  - 属性名后
  - 多个规则的分隔符,前
  - important !后
  - 属性值中(后和)前
  - 行末不要有多余的空格
- 以下几种情况需要空格：
  - 属性值前v
  - 选择器>, +,~前后
  - { 前
  - !important !前
  - @else 前后
  - 属性值中的,后
  - 注释 /\* 后和 \*/ 前

```
/* not good */
.element {
    color :red! important;
    background-color: rgba(0,0,0,.5);
}

/* good */
.element {
    color: red !important;
    background-color: rgba(0, 0, 0, .5);
}

/* not good */
.element ,
.dialog{
    ...
}

/* good */
.element,
.dialog {

}

/* not good */
.element>.dialog{
    ...
}

/* good */
.element > .dialog{
    ...
}

/* not good */
.element{
    ...
}

/* good */
.element {
    ...
}

/* not good */
@if{
    ...
}@else{
    ...
}

/* good */
@if {
    ...
} @else {
    ...
} 
```

## 空行
- 以下几种情况需要空行：
  - 文件最后保留一个空行
  - } 后最好跟一个空行，包括scss中嵌套的规则
  - 属性之间需要适当的空行，具体见属性声明顺序
  
```
/* not good */
.element {
    ...
}
.dialog {
    color: red;
    &:after {
        ...
    }
}

/* good */
.element {
    ...
}

.dialog {
    color: red;

    &:after {
        ...
    }
}
```

## 换行
- 以下几种情况不需要换行：
  - { 前
- 以下几种情况需要换行：
  - { 后和 } 前
  - 每个属性独占一行
  - 多个规则的分隔符,后

```
/* not good */
.element
{color: red; background-color: black;}

/* good */
.element {
    color: red;
    background-color: black;
}

/* not good */
.element, .dialog {
    ...
}

/* good */
.element,
.dialog {
    ...
}
```

## 注释
- 注释统一用/* */（scss及less中也不要用//），具体参照例子的写法
- 缩进与下一行代码保持一致
- 可位于一个代码行的末尾，与代码间隔一个空格

```
/* Modal header */
.modal-header {
    ...
}

/*
 * Modal header
 */
.modal-header {
    ...
}

.modal-header {
    /* 50px */
    width: 50px;

    color: red; /* color red */
}
```

## 引号
- 最外层统一使用双引号
- url的内容要用引号
- 属性选择器中的属性值需要引号

```
.element:after {
    content: "";
    background-image: url("logo.png");
}

li[data-type="single"] {
    ...
}
```

## 命名
- css 元素名称以及 id 和类名的命名也是区分大小写的（但是属性和值不区分）
- 类名使用小写字母，以中划线-分隔
- id 采用驼峰式命名
- less 及 scss 中的变量、函数、混合、placeholder 采用驼峰式命名

```
/* class */
.element-content {
    ...
}

/* id */
#myDialog {
    ...
}

/* 变量 */
$colorBlack: #000;

/* 函数 */
@function pxToRem($px) {
    ...
}

/* 混合 */
@mixin centerBlock {
    ...
}

/* placeholder */
%myDialog {
    ...
}
```

## 属性顺序
按以下顺序书写，各组属性间空一行
1. 位置
2. 大小
3. 内容
4. 其他

```
.declaration-order {
    display: block;
    float: right;

    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 100;

    border: 1px solid #e5e5e5;
    border-radius: 3px;
    width: 100px;
    height: 100px;

    font: normal 13px "Helvetica Neue", sans-serif;
    line-height: 1.5;
    text-align: center;

    color: #333;
    background-color: #f5f5f5;

    opacity: 1;
}
```

## 颜色
- 使颜色16进制用小写字母
- 颜色16进制尽量用简写

```
/* not good */
.element {
    color: #ABCDEF;
    background-color: #001122;
}

/* good */
.element {
    color: #abcdef;
    background-color: #012;
}
```

## 属性简写
- 属性简写需要你非常清楚属性值的正确顺序，而且在大多数情况下并不需要设置属性简写中包含的所有值，所以建议尽量分开声明会更加清晰
- margin 和 padding 相反，需要使用简写
- 常见的属性简写包括
  -  font
  -   background
  -   transition
  -   animation

```
/* not good */
.element {
    transition: opacity 1s linear 2s;
}

/* good */
.element {
    transition-delay: 2s;
    transition-timing-function: linear;
    transition-duration: 1s;
    transition-property: opacity;
}
```

## 媒体查询
尽量将媒体查询的规则被包含在他们相关的规则，不要将他们一起放到一个独立的样式文件中，或者丢在文档的最底部，这样做只会让大家以后更容易忘记他们。

```
button {
    font-size: 0.875rem;
    padding: .5em 1em;
    border: .125em solid #e3e3e3;
    @media (min-width: 48rem){
      font-size: 1.125rem;
    }
    @media (min-width: 62rem){
      font-size: 1.375rem;
    }
}
```

## 其他
- 不允许有空的规则
- 元素选择器用小写字母
- 去掉小数点前面的0
- 去掉数字中不必要的小数点和末尾的0
- 属性值0后面不要加单位
- 禁止使用expression表达式
- 禁止滥用!important
- 同个属性不同前缀的写法需要在垂直方向保持对齐，具体参照右边的写法
- 无前缀的标准属性应该写在有前缀的属性后面
- 不要在同个规则里出现重复的属性，如果重复的属性是连续的则没关系
- 不要在一个文件里出现两个相同的规则
- 用 border: 0; 代替 border: none;
- 在保证选择器准确的情况下尽量简化选择器 (尽量不超过4级，最多4级)，不写多余的选择器(如class/id前的标签选择器、li上一级的的ul/ol、dt/dd上一级的dl等，在保证准确的前提下能去掉的都去掉)（在scss中如果超过4层应该考虑用嵌套的方式来写
- 尽量少用*选择器
- 避免使用 @import语句。如果使用了@import语句，一定要将它们写在样式表开头，保证它的优先级低于样式表中的其他规则；与 <link> 标签相比，@import 指令要慢很多，不光增加了额外的请求次数，还会导致不可预料的问题。替代办法有以下几种
  - 使用多个 \<link\> 元素
  - 通过 Less 或 Sass 类似的 CSS 预处理器将多个 CSS 文件编译为一个文件
  - 通过 Rails、Jekyll 或其他系统中提供过 CSS 文件合并功能

```
-ms-transform:rotate(7deg);         /* -ms代表ie内核识别码 */
-moz-transform:rotate(7deg);        /* -moz代表火狐内核识别码 */
-webkit-transform:rotate(7deg);     /* -webkit代表谷歌内核识别码 */
-o-transform:rotate(7deg);          /* Opera15以前加 -o-，Opera15及以后加 -webkit- */
transform:rotate(7deg);             /* 统一标识语句,符合w3c标准 */

----------------------------------------------------------------------------------

/* not good */
.element {
}

/* not good */
LI {
    ...
}

/* good */
li {
    ...
}

/* not good */
.element {
    color: rgba(0, 0, 0, 0.5);
}

/* good */
.element {
    color: rgba(0, 0, 0, .5);
}

/* not good */
.element {
    width: 50.0px;
}

/* good */
.element {
    width: 50px;
}

/* not good */
.element {
    width: 0px;
}

/* good */
.element {
    width: 0;
}

/* not good */
.element {
    border-radius: 3px;
    -webkit-border-radius: 3px;
    -moz-border-radius: 3px;

    background: linear-gradient(to bottom, #fff 0, #eee 100%);
    background: -webkit-linear-gradient(top, #fff 0, #eee 100%);
    background: -moz-linear-gradient(top, #fff 0, #eee 100%);
}

/* good */
.element {
    -webkit-border-radius: 3px;
       -moz-border-radius: 3px;
            border-radius: 3px;

    background: -webkit-linear-gradient(top, #fff 0, #eee 100%);
    background:    -moz-linear-gradient(top, #fff 0, #eee 100%);
    background:         linear-gradient(to bottom, #fff 0, #eee 100%);
}

/* not good */
.element {
    color: rgb(0, 0, 0);
    width: 50px;
    color: rgba(0, 0, 0, .5);
}

/* good */
.element {
    color: rgb(0, 0, 0);
    color: rgba(0, 0, 0, .5);
}
```