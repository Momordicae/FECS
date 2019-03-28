## 命名
- 区分大小写，变量命名只允许有字母、数字、$ 和 _ 下划线
- 对 JQ 对象变量命名时，使用 $var 的形式

## 惯例
- 注释符 \/* 后和 */ 前均有一个空格
- 防止变量提升，应先声明后使用
- 不应该使用硬编码，并且重复几次
- 不应该有两个配置属性，含义不明，如 this.opts 和 this._options
- 若两次以上引用同一对象的属性，应该定义到局部变量再引用：
```
var options = this._options;
```
- 不应该同时使用两种属性命名风格，如 colModel 和 table_body
- 局部变量名应该尽可能短，而方法名应该尽可能完整，如不应该同时即有 fromatTpl 又有 parseTemplate
- 局部变量名不需要用下划线开头，仅对象私有属性和私有方法有此必要；变量名不需要带类型属性，如 _thdoms 叫 ths 就好
- 使用高阶函数，for 循环基本可以避免使用
- JQ 对象名习惯以 $ 开头，以便区分 DOM 对象；JQ 查询应尽量使用 context
```
this.$table = $('table', this.$element);
```
- JQ DOM 操作和原生 DOM 操作不应该混用

## 注释
- 沿用业界成文规范，包括脚本同时包括样式，最初由 YUI Compressor 制定
```
/**
 * 这里的注释内容【会】被压缩工具压缩
 */

/*！
 * 这里的注释内容【不会】被压缩工具压缩
 * 与上面一个注释块不同的是，第2个*换成了!
 */
```

常常把文件的关键信息放在第2种注释内容里，@key desc格式来书写，常用的关键词有：

| 关键词 | 描述 |
| ------ | ------ |
| @auhor | 作者 |
| @param | 参数 |
| @example | 示例 |
| @link | 链接 |
| @namespace | 命名空间 |
| @auhor | 依赖模块 |
| @return | 返回值 |
| @version | 版本号 |

其中，param关键词的格式为：
```
/**
 * @param {String} 参数描述
 */
```

## 其他
- 分号  
分号表示语句的结束。大多数情况下，如果你省略了句尾的分号，Javascript会自动添加。
> 不要省略句末的分号。

- with语句  
with可以减少代码的书写，但是会造成混淆。
> 不要使用with语句。

- 相等和严格相等  
Javascript有两个表示"相等"的运算符："相等"（==）和"严格相等"（===）。
> 不要使用"相等"（==）运算符，只使用"严格相等"（===）运算符。

- 全局变量   
Javascript最大的语法缺点，可能就是全局变量对于任何一个代码块，都是可读可写。这对代码的模块化和重复使用，非常不利。
> 避免使用全局变量；如果不得不使用，用大写字母表示变量名，比如UPPER_CASE。

- Javascript会自动将变量声明"提升"（hoist）到代码块（block）的头部。  
> 所有变量声明都放在函数的头部。  
> 规则10：所有函数都在使用之前定义。

- 自增和自减运算符   
自增（++）和自减（--）运算符，放在变量的前面或后面，返回的值不一样，很容易发生错误。
事实上，所有的++运算符都可以用"+= 1"代替。
> 不要使用自增（++）和自减（--）运算符，用+=和-=代替。

- 区块  
如果循环和判断的代码体只有一行，Javascript允许该区块（block）省略大括号。
> 总是使用大括号表示区块。

- new命令   
Javascript使用new命令，从建构函数生成一个新对象。
```
var o = new myObject();
```
这种做法的问题是，一旦你忘了加上new，myObject()内部的this关键字就会指向全局对象，导致所有绑定在this上面的变量，都变成全部变量。如果不得不使用new，为了防止出错，最好在视觉上把建构函数与其他函数区分开来。
> 不要使用new命令，改用Object.create()命令。  
> 建构函数的函数名，采用首字母大写（InitialCap）；其他函数名，一律首字母小写。