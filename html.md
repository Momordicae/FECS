## DOCTYPE
页面文档类型统一使用HTML5 DOCTYPE. 代码如下：
```
<!DOCTYPE html>
```

## 编码
声明方法遵规循HTML5的范. 代码如下：
```
<meta charset="utf-8" />
```

## 语义化
使用符合语义的标签书写 HTML 文档, 选择恰当的元素表达所需的含义。

-  结构元素
   - p 表示段落. 只能包含内联元素, 不能包含块级元素;
   - li 本身无特殊含义, 可用于布局. 几乎可以包含任何元素;
   - br 表示换行符;
   - hr 表示水平分割线;
   - h1 - h6 表示标题， 其中 h1 用于表示当前页面最重要的内容的标题;
   - blockquote 表示引用, 可以包含多个段落. 请勿纯粹为了缩进而使用blockquote, 大部分浏览器默认将 blockquote 渲染为带有左右缩进;
   - pre 表示一段格式化好的文本；

- 头部元素
   - title 每个页面必须有且仅有一个 title 元素;
   - base 可用场景：首页、频道等大部分链接都为新窗口打开的页面;
   - link用于引入 css 资源时, 可省去 media(默认为all) 和 type(默认为text/css) 属性;
   - styletype 默认为 text/css, 可以省去;
   - scripttype 属性可以省去; 不赞成使用lang属性; 不要使用古老的<!– //–>这种hack脚本, 它用于阻止第一代浏览器(Netscape 1和Mosaic)将脚本显示成文字;
   - noscript 在用户代理不支持 JavaScript 的情况下提供说明；

- 文本元素
   - a 存在 href 属性时表示链接, 无 href 属性但有 name 属性表示锚点;
   - em,strong em 表示句意强调, 加与不加会引起语义变化, 可用于表示不同的心情或语调; strong 表示重要性强调, 可用于局部或全局, strong强调的是重要性, 不会改变句意;
   - abbr 表示缩写;
   - sub,sup 主要用于数学和化学公式, sup还可用于脚注;
   - span 本身无特殊含义;
   - ins,del 分别表示从文档中增加(插入)和删除；

- 媒体元素
   - img 请勿将img元素作为定位布局的工具, 不要用他显示空白图片; 必要时给img元素增加alt属性;
   - object 可以用来插入Flash;

- 列表元素
   - dl 表示关联列表, dd是对dt的解释; dt和dd的对应关系比较随意：一个dt对应多个dd、多个dt对应一个dd、多个dt对应多个dd, 都合法; 可用于名词/单词解释、日程列表、站点目录;
   - ul 表示无序列表;
   - ol 表示有序列表, 可用于排行榜等;
   - li 表示列表项, 必须是ul/ol的子元素;

- 表单元素
   - 推荐使用 button 代替 input, 但必须声明 type;
   - 推荐使用 fieldset, legend 组织表单；
   - 表单元素的 name 不能设定为 action, enctype, method, novalidate, target, submit 会导致表单提交混乱；

## 大小写，属性值
元素的标签和属性名必须小写, 属性值必须加双引号。

## html模板
```
<!DOCTYPE HTML>
<html lang="zh-cmn-hans">
<head>
<meta charset="utf-8">
<meta name="renderer" content="webkit|ie-comp|ie-stand">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no" />
<title>title不可缺少，控制在25个字、50个字节以内。“二级栏目 - 一级栏目 - 网站名称”。</title>
<meta name="keywords" content="关键词,5个左右,单个8汉字以内">
<meta name="description" content="网站描述，字数尽量空制在80个汉字，160个字符以内！">
<link rel="Bookmark" href="/favicon.ico" >
<link rel="Shortcut Icon" href="/favicon.ico" />
<!--[if lt IE 9]>
<script>
       (function(){var e="abbr, article, aside, audio, canvas, datalist, details, dialog, eventsource, figure, footer, header, hgroup, mark, menu, meter, nav, output, progress, section, time, video".split(', ');var i=e.length;while(i--){document.createElement(e[i])}})()
    </script>
<![endif]-->
<link href="http://www.a.com/css/style.css" rel="stylesheet" type="text/css" />
<script type="text/javascript" src="http://libs.baidu.com/jquery/1.8.2/jquery.js"></script>
</head>
<body>
<header>   <!--头部-->  </header>
<div>      <!--内容-->  </div>
<footer>   <!--头部-->  </footer>
<!--End of Footer-->
<script type="text/javascript" src="http://www.a.com/Lib/a.min.js"></script>

<!--下方是cnzz统计代码，请在自己项目中干掉--> 
<script type="text/javascript">var cnzz_protocol= ...</script>
</body>
</html>
```

