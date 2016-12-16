前端代码规范建议，Emmet：HTML、CSS代码速写神器
===========================================

## 内容：

* 前端（HTML、CSS、JavaScript）代码规范建议
* Emmet工具介绍（常用HTML、CSS的人可以看看，用不到的可以忽略）

## 前端代码规范建议

### 通用规范建议

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

* 两个空格代替缩进
* UTF-8编码
* 文件名、目录名
  - 一律小写，优先英文单词，多个单词以连字符`-`连接，只能出现小写英文字母，数字和连字符。
  - 同时适用于目录的命名。

### HTML规范
* HTML5
  - 不要省略应该有的结束标签，例如`<li></li>`。
  - `meta`、`link`、`img`、`input`等这样的元素省略结尾的“/”。
  - `script`标签省略`type="text/javascript"`属性。
* IE兼容模式

```html
  <meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

* 结构

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <!-- css -->
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <!-- 文档 -->
  <h1>标题</h1>
  <p>文章</p>
  <!-- JavaScript -->
  <script src="base.js"></script>
</body>
</html>
```

* 属性值必须用双引号

```html
<img src="logo.png" alt="Logo">
```

* 属性的定义顺序

```html
<img src="logo.png" alt="Logo" id="logo" class="hide site-logo">
```

* 标签和属性名
  - 标签和属性起名使用小写英文字母。
  - 自定义属性名使用data-开头，命名优先使用英文单词，多个单词以连字符`-`连接。
  - disabled、checked、selected等属性省略属性值。

```html
<div class="banner" data-tool="banner" data-auto-stop="true"></div>
<input type="text" name="age" id="iAge" disabled>
```

* 语义化

```html
<header id="header">页头</header>
<section id="body">主体</section>
<footer id="footer">尾部</footer>
```

* class值的命名
  - 优先使用小写英文单词。
  - 多个英文单词以连字符`-`连接。
  - 注意先后顺序

```html
<p class="text-right article product-article">文章</p>
```

* id值的命名
  - 驼峰命名。
  - 一些特殊元素使用前缀，例如输入框可以使用“i”开头，按钮使用“btn”开头。
```html
<input type="text" name="userName" id="iUserName">
```
* 其他属性值
  - name的值推荐使用驼峰法。

### CSS规范
* 建议写法
  - 多个选择器各自逗号分隔独占一行。
  - 每条属性独占一行分号分隔独占一行。
  - 冒号后边加一个空格。
  - 大括号前加一个空格。

```css
.article,
.info {
  width: 100px;
  line-height: 20px;
  color: #000;
}
```

* 顺序
  - 定位方式
  - 显示属性
  - 元素属性
  - 元素内容属性

```css
.logo {
  position: absolute;
  left: 0;
  top: 0;
  z-index: 10;
  display: block;
  width: 100px;
  height: 50px;
  line-height: 50px;
  margin: 10px 5px;
  padding: 10px;
  border: 1px solid #ccc;
  background: #fff;
  color: #f00;
  font-size: 14px;
  text-align: center;
  text-indent: 2em;
}
```

* 不要限定类选择器
  - 例如：`ul.recommend`建议改为`.recommend-list`。
* 0值
  - 值为0时省略后面的单位。
* 颜色值
  - 尽量使用十六进制颜色值，可缩写成三位的建议使用缩写形式，同项目下大小写和缩写规则应保持一致。
  - 半透明颜色使用rgba值，每个颜色值逗号分隔，且逗号后加一个空格。
* 不要用*
  - 尽量避免使用*选择符。
* 不用#
  - 除特殊需要不要给id选择器定义样式。

### JS规范

* var
  - 禁止使用不带var的全局变量。
* 常量大写
  - 含义为常量的变量起名为全大写形式，多个单词用下划线`_`分隔。例如：`BASE_URL`。
* 命名
  - 一般的变量推荐使用英文单词，并以驼峰法命名。例如：`userName`。
* 一行。

```js
var a = 2;
```

* 字符串值使用单引号

```js
var nameString = 'Karl Liris';
```

* 判断布尔值变量视情况可省略条件值，或判断某个值是否为空也可如此。例如需要判断`name`是否为空，可直接使用`if(name){}`进行判断，例如：

  ```js
  if(isLogin){
    name = 'Karl Liris';
  }
  ```

  ```js
  isLogin ? 'Karl Liris' : 'unKnow';
  ```

* if语句

```js
if(isLogin && userId == '0'){
  console.log('已经登录');
}
```

* switch语句

```js
  switch(type){
    case 1:
      alert(1);
      break;
    case 2:
      alert(2);
      break;
    default:
      alert(0);
      break;
  }
```

* 函数

```js
function render(data, options, callback){
  $('#Title').html('Hi! Every Body.');
}
```

```js
var render = function(data, options, callback){
  $('#Title').html('Hi! Every Body.');
};
```

```js
render('Hi', {color: '#f00'}, function(){
  alert('done!');
});
```

```js
render({
  name: 'Karl Liris',
  age: 30
}, {
  color: '#f00',
  show: false
}, function(){
  alert('done!');
});
```

* 预先定义的空值
  - 类型为数字的值可定义为`0`。例如：`var num = 0;`。
  - 类型为字符串的值可定义为空字符串`''`。例如：`var name = '';`。
  - 类型为数组的值可定义为空数组的字面量形式。例如：`var list = [];`。
  - 其他情况可定义为`null`或对应的字面量形式的空值。例如：`var options = null;`。
* 数组

```js
var arrs = [1, '2', [
  'China',
  'USA'
]];
```

* 对象

```js
var obj = {name: 'Karl Liris'};
```

```js
var obj = {
  name: 'Karl Liris',
  age: 30,
  list: ['Karl', 'Liris'],
  books: ['HTML', [
    'CSS', 'Less'
  ]],
  sub: {isShow: false},
  options: {
    timeout: 300,
    limit: 100
  }
};
```

* 其他
……