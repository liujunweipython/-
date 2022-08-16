# Html5+Css3+移动web教程

# Web标准(重点)

## web标准的构成

主要包括结构、表现、行为三个方便

| 标准 | 说明                                                         |
| ---- | ------------------------------------------------------------ |
| 结构 | 结构用于对网页元素进行整理和分类，现阶段主要学的是HTML       |
| 表现 | 表现用于设置网页元素的版式、颜色、大小等外观样式，主要指的是CSS |
| 行为 | 行为是指网页模型的定义及交互的编写，现阶段主要学的是javascript |

web标准提出的最佳体验方案：结构、样式、行为相分离。

简单理解：结构写到html文件中，表现写到css文件中，行为写到JavaScript文件中。

# HTML标签(上)

## 目标：

- 能够说出标签的书写注意规范
- 能够写出HTMl骨架标签
- 能够写出超链接标签
- 能够写出图片标签并说出alt和title的区别
- 能够说出相对路径的三种形式

## 目录：

1. HTML语法规范
2. HTML基本结构标签
3. 开发工具
4. HTML常用标签
5. HTML中的注释和特殊字符

### HTML语法规范

1. HTMl标签是由尖括号包围关键词，例如**`<html>`** 。
2. HTMl标签通常是成对出现的，例如**`<html>`**和**`</html>`**，我们成为双标签。标签中的第一个标签是开始标签，第二个标签是结束标签。
3. 有些特殊的标签必须是单个标签(极少情况)，例如**`<br/>`**，我们称为但标签。

### HTML常用标签

#### 一.标题标签**`<h1>-<h6>`**(重要)

为了是网页更具有语义化，我们经常会在页面中使用到标题标签。html提供了6个等级的网页标题，

即**`<h1>-<h6>`**。

```html
<h1>我是一级标题</h1>
```

标签语义：作为标题使用，并且依据重要性递减。

特点：

1. 加了标题的文字会变的加粗，字号也会一次变大。
2. 一个标题独占一行。

#### 二.段落标签（重要）

在网页中，要把文字有条理地显示出来，就需要将这些文字分段显示。咋HTML标签中，**`<p>`**标签用于定义段落，它可以将整个网页分为若干个段落。

```html
<p>我是一个段落标签</p>
```

标签语义：可以把HTML文档分割为若干个段落。

特点：

1. 文本在一个段落中会根据浏览器窗口的大小自动换行。
2. 段落和段落之间保有空隙

#### 三.换行标签（重要）

在HTML中，一个段落中的文字会从左到右依次排列，直到浏览器窗口的右端，然后才自动换行。如果希望某段文本强制换行显示，就需要使用换行标签**`<br/>`**

```html
<br/>
```

标签语义：强制换行。

特点：

1. **`<br/>`**是个单标签。
2. **`<br/>`**标签只是简单的开始新的一行，跟段落不一样，段落之间会插入一些垂直的间距。

#### 四.案例总结

要求显示如下图：

![1651049372(1)](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/1651049372(1).jpg)

实现：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>体育案例</title>
</head>
<body>
    <h1>水花61分伊戈达拉制胜抢断 西决勇士再胜开拓者总分2-0</h1>
    <h4>数据统计：水花兄弟合砍61分</h4>
    <p>库里22投11中，三分14投4中，罚球11罚全中得到37分8篮板8助攻，职业生涯季后赛得分30+次数来到35次， 超过哈登排名现役第3位，仅次于詹姆斯和杜兰特。</p>
    <p>汤普森22投8中，三分8投4中得到24分3篮板2助攻，德拉蒙德-洛林得到16分10篮板7助攻5盖帽， 凯文-鲁尼得到14分7篮板2助攻，今天勇士有7名替补出场。</p>
    <h4>兄弟对决升级：小库里给哥哥造成压力</h4>
    <p>库里兄弟是NBA历史上第一对在分区决赛相遇的兄弟。在西决第1场中，小库里没有给哥哥造成压力， 他出场19分钟，7投1中只得到3分3篮板2助攻，在场期间输掉10分。</p>
    <p>但在西决第2场中，小库里攻防两端都打出杰出的表现，全场送出4次抢断，包括直接抢断自己的哥哥库里， 在防守端给库里造成了极大的困扰。</p>
    <p>作者：pink 老师<br/>2019-8-8</p>
</body>
</html>
```

#### 五.文本格式化标签

在网页中，有时需要为文字设置粗体、斜体、或者下划线等效果，这时就需要用到HTML中的文本格式化标签，使文字以特殊的方式显示。

标签语义：突出重要性，比普通文字更重要。

| 语义   | 标签                         | 说明                                          |
| ------ | ---------------------------- | --------------------------------------------- |
| 加粗   | <strong></strong>或者<b></b> | 推荐使用<strong></strong>标签加粗，语义更强烈 |
| 倾斜   | <em></em>或者<i></i>         | 推荐使用<em></em>标签倾斜，语义更强烈         |
| 删除线 | <del></del>或者<s></s>       | 推荐使用<del></del>标签删除线，语义更强烈     |
| 下划线 | <ins></ins>或者<u></u>       | 推荐使用<ins></ins>标签下划线，语义更强烈     |

==重点记住**加粗**和*倾斜*==

#### 六.`<div>`和`<span>`标签

`<div>`和`<span>`是没有语义的，它们就是一个盒子，用来装内容的。

```html
<div>这是头部</div>
<span>今日价格</span>
```

特点：

1. `</div>`标签用来布局，但是现在一行只能放一个`</div>`。大盒子
2. `<span>`标签用来布局，一行上可以放放多`<span>`。小盒子

#### 七.图像标签和路径(重点)

##### 图像标签

在HTML标签中，**`<img>`**标签用于定义HTML页面中的图像。

```html
<img src="图像url" />
```

单词image的缩写，意为图像。

src是**`<img>`**标签的==必须属性==，它用于==指定图像文件的路径和文件名==。

所谓属性：简单理解就是属于这个图像标签的特性。

图像标签的其他属性：

| 属性   | 属性值   | 说明                                   |
| ------ | -------- | -------------------------------------- |
| src    | 路径图片 | 必须属性，指定图片位置                 |
| alt    | 文本     | 替换文本，当图片不能显示的时候显示文字 |
| title  | 文本     | 提示文本，鼠标放在图像上，显示提示文字 |
| width  | 像素     | 设置图像的宽度                         |
| height | 像素     | 设置图像的高度                         |
| border | 像素     | 设置图像的边框粗细                     |

图像标签属性注意点：

1. 图像标签可以拥有多个属性，必须写在标签名的后面。
2. 属性之间不分先后顺序，标签名与属性、属性与属性之间均以空格分开。
3. 属性采取键值对的格式，即key="value"的格式，属性="属性值"。

重点掌握：

- 图像标签哪个属性是必须要写的？

  scr属性是必须的，指定图片位置路径

- 图像标签中alt和title属性区别？

  alt替换文本，当图片无法显示的时候显示alt中定义的文本。

  title提示文本，当鼠标放在图像上，会有文字提示。

##### 路径之相对路径

相对路径：以引用文件所在位置为参考，而建立出的目录路径。

这里简单来说，图片相对于HTML页面的位置

| 相对路径分类 | 符号 | 说明                                                        |
| ------------ | ---- | ----------------------------------------------------------- |
| 同一级路径   |      | 图像文件位于html文件同一级，如<img src="baidu.jpg"/>        |
| 下一级路径   | /    | 图像文件位于html文件下一级，如<img src="images/baidu.jpg"/> |
| 上一级路径   | ../  | 图像文件位于html文件上一级，如<img src="../baidu.jpg"/>     |

相对路径是从代码所在的这个文件出发，区寻找目标文件的，而我们这里所说的上一级、下一级和同一级就是图片相对于HTML页面的位置。

##### 路径之绝对路径

绝对路径：是指目录下的绝对位置，直接到达目标位置，通常是从盘符开始的路径。

例如："C:\Users\liuju\Desktop\前端图片\1651049372.jpg"或完整的网络地址https://raw.githubusercontent.com/liujunweipython/tuchuang/main/image-20220225160052475.png

#### 八.超链接标签(重点)

在HTML标签中，**`<a>`**标签用于定义超链接，作用是从一个页面链接到另一个页面。

1. 链接的语法格式

   ```html
   <a href="跳转目标" target="目标窗口的弹出方式"> 文本或者图像 </a>
   ```

   两个属性的作用如下：

   | 属性   | 作用                                                         |
   | ------ | ------------------------------------------------------------ |
   | href   | 用于指定链接目标的url地址，（必须属性）当为标签应用href属性时，它就具有了超链接功能 |
   | target | 用于指定链接页面的打开方式，其中_self为默认值，当前页面打开，_blank为在新窗口中打开 |

2. 链接分类：

   - 外部链接：例如 **`<a href="https://www.baidu.com/">百度</a>`**
   - 内部链接：网站内部页面之间的相互链接，直接链接内部页面名称即可，例如**`<a href="index.html"> 首页</a>`**
   - 空连接：如果当时没有确定链接目标时， **`<a href="#">首页</a>`**
   - 下载链接：如果**href**里面地址是一个文件或者压缩包，会下载这个文件。
   - 网页元素链接：在网页中的各种网页元素，如文本、图像、表格、音频、视频等都是可以添加超链接。
   - 锚点链接：当我们点击链接，可以快速定位到页面中的某个位置。
     - 在链接文本的href属性中，设置属性值为==#名字==的形式，如**`<a href="#two">第二季</a>`**
     - 找到目标位置标签，里面添加一个id属性=刚才的名字，如**`<h4 id="two">第二季介绍</h4>`**

#### 九.注释和特殊字符

##### 9.1注释

如果需要在html文档中添加一些便于阅读和理解但又不需要显示在页面中的注释文字，就需要使用注释标签。HTML中的==注释以**`"<!--" 开头， 以 " -->"`** 结束。==

```html
<!-- 注释语句 -->      vscode工具中快捷键是：ctrl + /
```

一句话：注释标签里面的内容是给程序猿看的，这个代码是不执行不显示到页面中的。

##### 9.2特殊字符

在html页面中，一些特殊的符号很难或者不方便直接使用，此时我们就可以使用下面的字符来替代。

| 特殊字符 | 描述           | 字符的代码(英文;号) |
| -------- | -------------- | ------------------- |
|          | 空格符         | `&nbsp;`            |
| <        | 小于号         | &lt；               |
| >        | 大于号         | &gt；               |
| &        | 和号           | &amp；              |
| ￥       | 人民币         | &yen；              |
| ©        | 版权           | &copy；             |
| ®        | 注册商标       | &reg；              |
| °        | 摄氏度         | &deg；              |
| ±        | 正负号         | &plusmn；           |
| ×        | 乘号           | &times；            |
| ÷        | 除号           | &divide；           |
| ²        | 平方 （上标2） | &sup2；             |
| ³        | 立方 （上标3） | &sup3；             |

# HTML标签(下)

## 目标：

- 能够书写表格
- 能够写出无需列表
- 能够写出3～4个常用的input表单类型
- 能够写出下拉列表表单
- 能够使用表单元素实现注册页面
- 能够独立查阅w3c文档

## 目录：

1. 表格标签
2. 列表标签
3. 表单标签
4. 综合案例
5. 查阅文档

### 一.表格标签

表格是实际开发中非常常用的标签：

#### 1.表格的主要作用：

表格主要**用于显示、展示数据**，因为它可以让数据显示的非常规整，可读性非常好。特别是后台展示数据的时候，能够熟练运用表格就显得很重要。一个清爽简约的表格能够把复杂的数据表现的很有条理。

表格不是用来布局页面的，而是用来**展示数据**的。

#### 1.2.表格的基本语法

```html
<table>
    <tr>
        <td>单元格内的文字</td>
        ...
    </tr>
   ...
</table>
```

- `<table> </table>`是用于定义表格的标签。
- `<tr></tr>`标签用于定义表格中的行，必须嵌套在`<table> </table>`标签中。
- `<td></td>`用于定义表格中的单元格，必须嵌套在`<tr></tr>`标签中。
- 字母td指表格数据（table data），即单元格中的内容。

#### 1.3.表头单元格

一般表头单元格位于表格的第一行或第一列，**表头单元格里面的文本内容加粗剧中显示**。

`<th>`标签标识html表格的表头部分(table head的缩写)

```html
<table>
    <tr>
      <th>姓名</th> 
      ...
    </tr>
  ...
</table>
```

#### 1.4.表格属性

表格标签这部分属性实际开发中不常用，后面通过css来设置。

目的有两个：

1⃣️记住这些英语单词后面css会使用

2⃣️直观感受表格的外观形态

| 属性名      | 属性值              | 描述                                            |
| ----------- | ------------------- | ----------------------------------------------- |
| align       | left、center、right | 规定表格相对周围元素的对齐方式                  |
| border      | 1或""               | 规定表格单元是否拥有边框，默认为"",表示没有边框 |
| cellpadding | 像素值              | 规定单元格边沿与其他内容之间的空白，默认1像素   |
| cellspacing | 像素值              | 规定单元格之间的空白，默认2像素                 |
| width       | 像素值或百分比      | 规定表格的宽度                                  |

#### 1.5.案例：小说排行榜

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>小说排行榜</title>
</head>
<body>
    <table align="center" border="" cellspacing="0" width="500" height="249">
        <tr>
            <th>排名</th> 
            <th>关键词</th> 
            <th>趋势</th>
            <th>今日搜索</th> 
            <th>最近七日</th> 
            <th>相关链接</th> 
        </tr>
        <tr>
            <td>1</td> 
            <td>鬼吹灯</td> 
            <td><img src="down.jpg"></td> 
            <td>345</td> <td>123</td> 
            <td><a href="">贴吧</a> <a href="">图片</a> <a href="">百科</a></td>
        </tr>
        <tr>
            <td>2</td> 
            <td>盗墓笔记</td> 
            <td><img src="down.jpg" ></td> 
            <td>124</td> <td>675432</td> 
            <td><a href="">贴吧</a> <a href="">图片</a> <a href="">百科</a></td>
        </tr>
        <tr>
            <td>3</td> 
            <td>西游记</td> 
            <td><img src="up.jpg"></td> 
            <td>212</td> <td>7654</td> 
            <td><a href="">贴吧</a> <a href="">图片</a> <a href="">百科</a></td>
        </tr>
        <tr>
            <td>4</td> 
            <td>东游记</td> 
            <td><img src="up.jpg" ></td> 
            <td>23</td> <td>75645</td> 
            <td><a href="">贴吧</a> <a href="">图片</a> <a href="">百科</a></td>
        </tr>
        <tr>
            <td>5</td> 
            <td>甄嬛传</td> 
            <td><img src="down.jpg"></td> 
            <td>121</td> <td>7667</td> 
            <td><a href="">贴吧</a> <a href="">图片</a> <a href="">百科</a></td>
        </tr>
        <tr>
            <td>6</td> 
            <td>水浒传</td>
             <td><img src="up.jpg" >
            </td> <td>654736</td> 
            <td>234514</td> 
            <td><a href="">贴吧</a> <a href="">图片</a> <a href="">百科</a></td>
        </tr>
        <tr>
            <td>7</td> 
            <td>三国演义</td> 
            <td><img src="up.jpg" ></td> 
            <td>234</td> <td>7686</td> 
            <td><a href="">贴吧</a> <a href="">图片</a> <a href="">百科</a></td>
        </tr>
    </table>
    
</body>
</html>
```

#### 1.6.表格结构标签 

使用场景：因为表格可能很长，为了更好的表示表格的语义，可以将表格分割成 表格头部 和表格主体两大部分。

在表格标签中，分别用：**`<thead>`标签 表格的表头区域，<tbody`>`标签 表格的主体区域，**这样可以更好的分清表格结构

#### 1.7.合并单元格

特殊情况下，可以把多个单元格合并为一个单元格，这里会最简单的合并单元格即可。

- 合并单元格方式：

  跨行合并：rowspan='合并单元格的个数'

  跨列合并：colspan='合并单元格的个数'

  ![image-20220509181426798](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/image-20220509181426798.png)

- 目标单元格(写合并代码)

  跨行：最上侧单元格为目标单元格，写合并代码

  跨列：最左侧单元格为目标单元格，写合并代码

- 合并单元格三部曲

  - 先确定是跨行还是跨列合并
  - 找到目标单元格，写上合并方式=合并单元格数量。比如：`<td clospan='2'> </td>`
  - 删除多余的单元格

### 二.列表标签

表格标签是用来显示数据的，那么列表就是用来布局的。

列表最大的特点就是整齐、整洁、有序、它作为布局更加自由和方便。

根据使用场景不同，**列表可以分为三大类：无序列表、有序列表、自定义列表**。

#### 2.1.无序列表(重点)

`<ul>`标签表示html页面中的无序列表，一般会以项目符号呈现列表项，而列表项使用`<li>`标签定义。

无序列表的基本语法如下：

```html
<ul>
    <li>列表项1</li>
    <li>列表项2</li>
    <li>列表项3</li>
</ul>
```

- 无序列表的各个列表项之间没有顺序级别之分，是并列的。
- `<ul></ul>`中只能嵌套`<li><li>`,直接在`<ul></ul>`标签中输入其他标签或者文字是不被允许的。
- `<li>与<li>`之间相当于一个容器，可以容纳所有元素。
- 无序列表会带有自己的样式属性，但在实际使用时，我们会用css来设置。

**重点：新增知识点**

去掉li前面的项目符号(去掉小圆点)

语法：

```css
在样式中加	list-style: none;
li {
		list-style: none;
}
```

#### 2.2.有序列表(理解)

有序列表即为有排列顺序的列表，其各个列表会按照一定的顺序定义。

在html标签中，`<ol>`标签用于定义有序列表，列表排序以数字来显示，并且使用`<li>`标签来定义列表项。

有序列表的基本语法如下：

```html
<ol>
    <li>列表项1</li>
    <li>列表项2</li>
    <li>列表项3</li>
</ol>
```

- `<ol></ol>`中只能嵌套`<li><li>`,直接在`<ol></ol>`标签中输入其他标签或者文字是不被允许的。
- `<li>与<li>`之间相当于一个容器，可以容纳所有元素。
- 有序列表会带有自己的样式属性，但在实际使用时，我们会用css来设置。

#### 2.3.自定义列表(重点)

自定义列表的使用场景：

自定义列表常用于对术语或名字进行解释和描述，自定义列表的列表项前没有任何项目符号

![截屏2022-05-10 17.17.06](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/%E6%88%AA%E5%B1%8F2022-05-10%2017.17.06.png)

在html标签中，`<dl>`标签用于定义描述列表(或自定义列表)，该标签会与 `<dt>`(定义项目/名字)和`<dd>`(描述每一个项目/名字)一起使用。

自定义列表语法如下：

```html
<dl>
    <dt>名词1</dt>
    <dd>名词1解释1</dd>
  	<dd>名词1解释2</dd>
</dl>
```

- `<dl></dl>`中只能包含`<dt></dt>`和`<dd></dd>`。
- `<dt></dt>`和`<dd></dd>`个数没有限制，经常是一个`<dt></dt>`对应多个`<dd></dd>`。

#### 2.4列表总结

| 标签名    | 定义       | 说明                                                         |
| --------- | ---------- | ------------------------------------------------------------ |
| <ul></ul> | 无序列表   | 里面只能包含li，没有顺序，使用较多。li里面可以包含任何标签   |
| <ol></ol> | 有序列表   | 里面只能包含li，有顺序，使用相对较少。li里面可以包含任何标签 |
| <dl></dl> | 自定义列表 | 里面只能包含dt和dd，dt和dd里面可以放任何标签                 |

### 三.表单标签

#### 3.1为什么需要表单

使用表单目的是为了收集用户信息。

在网页中，我们也需要跟用户进行交互，收集用户资料，此时就需要表单。

#### 3.2表单组成

在html中，一个完整的表单通常由**表单域、表单控件(也称为表单元素)和提示信息**三个部分构成。

![截屏2022-05-11 17.01.49](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/%E6%88%AA%E5%B1%8F2022-05-11%2017.01.49.png)

#### 3.3表单域

表单域是一个包含表单元素的区域

在html标签中，`<form>`标签用于定义表单域，以实现用户信息的收集和传递

**`<form>`会把它范围内的表单元素信息提交给服务器。**

表单域语法：

```html
<form action="url地址" method="提交方式" name="表单域名城">
    各种表单控件
</form>
```

| 属性   | 属性值   | 作用                                               |
| ------ | -------- | -------------------------------------------------- |
| action | url地址  | 用于指定接收并处理表单数据的服务器程序的url地址    |
| method | get/post | 用于设置表单数据的提交方式，其取值为get或psot      |
| name   | 名称     | 用于指定表单的名称，以区分同一个页面的多个表单域。 |

#### 3.4表单控件

在表单域中可以定义各种表单元素，这些表单元素就是允许用户在表单中输入或者选择的内控件

##### 3.4.1input输入表单元素

英文单词中，input是输入的意思，而在表单元素中`<input>`标签用于收集用户信息。

在`<input>`标签中，包含一个type属性，根据不同type属性值，输入字段拥有很多种形式(可以是文本自断、复选框、掩码后的文本控件、单选按钮、复选按钮等)

```html
<form action="" method="" name="">
    <input type="属性值">
</form>
```

- `<input />`标签是单标签

- type属性设置不同的属性值用来指定不同的控件类型 。

  **type属性的属性值及其描述如下：**

  | 属性值   | 描述                                                         |
  | -------- | ------------------------------------------------------------ |
  | button   | 定义可点击按钮(多说情况下，用于通过javascript启动脚本)       |
  | checkbox | 定义复选框                                                   |
  | file     | 定义输入字段和"浏览按钮"，供文件上传                         |
  | hidden   | 定义隐藏的输入字段                                           |
  | image    | 定义图像形式的提交按钮                                       |
  | password | 定义密码字段，该字段中的字符被掩码                           |
  | radio    | 定义单选按钮                                                 |
  | reset    | 定义重置按钮，重置按钮会清除表单中的所有数据                 |
  | submit   | 定义提交按钮，提交按钮会把表单数据发送到服务器               |
  | text     | 定义单行的输入字段，用户可在其中输入文本。默认宽度为20个字符 |

  **除type属性外，input标签还有其他很多属性，其常用属性如下：**

  | 属性      | 属性值       | 描述                                                         |
  | --------- | ------------ | ------------------------------------------------------------ |
  | name      | 由用户自定义 | 定义input元素的名称                                          |
  | value     | 由用户自定义 | 规定input元素的值                                            |
  | checked   | checked      | 规定此input元素首次加载时应当被选中，主要针对单选按钮或复选框 |
  | maxlength | 正整数       | 规定输入字段中的字符的最大长度                               |

  - name和value是每个表单元素都有属性值，主要给后台人员使用。
  - name表单元素的名字，要求**单选按钮和复选框要有相同的name值**。
  - checked属性主要针对单选按钮和复选框，主要作用已打开页面就要默认选中某个表单元素。
  - maxlength是用户可以在表单元素中输入的最大字符，一般较少使用。

##### 3.4.2`<label>`标签

`<label>`标签为input元素定义标注(标签)

`<label>`标签用于绑定一个表单元素，当点击`<label>`标签内的文本时，浏览器会自动将光标转到或选择对应的表单元素上，用来增加用户体验。

`<label>`标签语法：

```html
<label for="nan">男</label> <input type="radio" id="nan" name="sex">
```

**核心：`<label>`标签的for属性应当与相关元素的id属性相同**

##### 3.4.3select下拉表单元素

**使用场景：**在页面中，如果有多个选项让用户选择，并且想要节约页面空间，我们可以使用`<select>`标签控件定义下拉列表。

**select语法规范：**

```html
<select>
    <option>选项1</option>
    <option>选项2</option>
    <option>选项3</option>
</select>
```

- `<select>`中至少包含一对<option>。
- 在<option>中定义selected="selected"时，当前项即为默认选中项。

##### 3.4.4textarea文本域元素

**使用场景：**当用户输入内容较多的情况下，我们就不能使用文本框表单了，此时我们可以使用`<textarea>`标签。

在表单元素中，`<textarea>`标签用于定义多行文本输入的控件。

使用多行文本输入控件，可以输入更多的文字，该控件常见于留言板，评论。

**textarea语法**：

```html
<textarea cols="30" rows="10">文本内容</textarea>
```

- 通过`<textarea>`标签可以轻松地创建多行文本输入框
- cols='每行中的字符数'，rows="显示的行数"，**实际开发中我们使用css来改变大小。**

### 四.综合案例-注册页面

**实现效果图：**

![image-20220512170337488](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/image-20220512170337488.png)

代码实现：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>综合案例-注册</title>
</head>
<body>
    <form action="daemo.php" method="post" name="zhuce">
        <h4>青春不常在，抓紧谈恋爱</h4>
        <table width="500">
            <!-- 第一行 -->
            <tr>
                <td>性别</td>
                <td><label for="nan"><img src="images/man.jpg" >男 </label> <input type="radio" id="nan" name="sex">  
                    <label for="nv"><img src="images/women.jpg">女</label> <input type="radio" name="sex" id="nv"></td>
            </tr> 
            <!-- 第二行 -->
            <tr>
                <td>生日</td>
                <td>
                    <select >
                        <option selected>--请选择年--</option>
                        <option >1990</option>
                        <option >1991</option>
                        <option >1992</option>
                        <option >1993</option>
                        <option >1994</option>
                        <option >1995</option>
                    </select>
                    <select >
                        <option selected>--请选择月--</option>
                        <option >1</option>
                        <option >2</option>
                        <option >3</option>
                        <option >4</option>
                        <option >5</option>
                        <option >6</option>
                    </select>
                    <select >
                        <option selected>--请选择日--</option>
                        <option >1</option>
                        <option >2</option>
                        <option >3</option>
                        <option >4</option>
                        <option >5</option>
                        <option >6</option>
                    </select>
                </td>
            </tr> 
            <!-- 第三行 -->
            <tr>
                <td>所在地区</td>
                <td>
                    <select >
                        <option selected >北京</option>
                        <option >上海</option>
                        <option >广州</option>
                        <option >深圳</option>
                    </select>
                </td>
            </tr>
            <!-- 第四行 -->
            <tr>
                <td>婚姻状况</td>
                <td>
                    <label for="weihun">未婚</label> <input type="radio" id="weihun" name="hyzh" checked>
                    <label for="yihun">已婚</label> <input type="radio" id="yihun" name="hyzh">
                    <label for="liyi">离异</label> <input type="radio" id="liyi" name="hyzh">
                </td>
            </tr>
            <!-- 第五行 -->
            <tr>
                <td><label for="xueli">学历</label></td>
                <td><input type="text" id="xueli"></td>
            </tr>
            <!-- 第六行 -->
            <tr>
                <td>喜欢的类型</td>
                <td>
                    <label for="wumei">妩媚的<input type="checkbox" id="wumei" name="like_leixing"></label>
                    <label for="keai">可爱的<input type="checkbox" id="keai" name="like_leixing"></label>
                    <label for="xiaoxianrou">小鲜肉<input type="checkbox" id="xiaoxianrou" name="like_leixing" ></label>
                    <label for="laolarou">老腊肉<input type="checkbox" id="laolarou" name="like_leixing"></label>
                    <label for="douxihuan">都喜欢<input type="checkbox" id="douxihuan" name="like_leixing"></label>
                </td>
            </tr>
            <!-- 第七行 -->
            <tr>
                <td><label for="jieshao">自我介绍</label></td>
                <td><textarea  id="jieshao" cols="30" rows="10">请自我介绍</textarea></td>
            </tr>
            <!-- 第八行 -->
            <tr>
                <td></td>
                <td><input type="submit" value="免费注册"></td>
            </tr>
            <!-- 第九行 -->
            <tr>
                <td></td>
                <td><input type="checkbox" checked >我同意注册条款和会员加入标准</td>
            </tr>
            <!-- 第十行 -->
            <tr>
                <td></td>
                <td><a href="login.php">我是会员,立即登录</a></td>
            </tr>
            <!-- 第十一行 -->
            <tr>
                <td></td>
                <td>
                    <h2>我承诺</h2>
                    <ul>                        
                        <li>年满18岁、单身</li>
                        <li>抱着严肃的态度</li>
                        <li>真诚寻找另一半</li>
                    </ul>
                </td>
            </tr>
        </table>
    </form>
    
</body>
</html>
```

### 五.查阅文档

经常查阅文档是很好的习惯

推荐网站：

- W3C：https://www.w3school.com.cn/
- MDN：https://developer.mozilla.org/zh-CN/
