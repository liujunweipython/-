# HTML5和CSS3提高

## 目标：

1. 能够说出3~5个HTML5新增布局和表单标签
1. 能够说出CSS3的新增特性有哪些

## 目录：

1. HTML5的新特性
1. CSS3的新特性

## 一、H5新特性

HTML5的新增特性主要针对以前的不足，增加了一些新的标签、新的表单和新的表单属性等。

这些新特性都有兼容性问题，基本是IE9+以上版本的浏览器才支持，如果不考虑兼容性问题，可以大量使用这些新特性。

### 1.1HTML5新增的语义化标签

以前布局，我们基本用div来做。div对于搜索引擎来说，是没有语义的。

```html
<div class=“header”> </div>
<div class=“nav”> </div>
<div class=“content”> </div>
<div class=“footer”> </div>
```

发展到了HTML5后，新增了一些语义化标签，这样的话更加有利于浏览器的搜索引擎搜索，也方便了网站的seo（Search Engine Optimization，搜索引擎优化），下面就是新增的一些语义化标签

- `<header>` 头部标签
- `<nav>` 导航标签
- `<article>` 内容标签
- `<section>` 定义文档某个区域
- `<aside>` 侧边栏标签
- `<footer>` 尾部标签

![语义化标签](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/%E8%AF%AD%E4%B9%89%E5%8C%96%E6%A0%87%E7%AD%BE.png)

注意：

- 这种语义化标准只要是针对搜索引擎的
- 这些新标签页面中可以使用多次
- 在IE9中，需要把这些元素转换为块级元素
- 其实，我们移动端更喜欢使用这些标签

### 1.2HTML5新增的多媒体标签

新增的多媒体标签主要有两个：

1. 音频：`<audio>`
2. 视频：`<video>`

使用他们可以很方便的在页面嵌入音频和视频，而不再去使用flash和其他浏览器插件。

在不使用插件的情况下，也可以原生的支持视频格式文件的播放，当然支持的格式是有限的。

#### 1.21视频video

当前 **<video>** 元素支持三种视频格式： 尽量使用 **mp4格式**

**使用语法：**

```html
 <video src="视频文件地址" controls="controls"></video>
```

| 浏览器            | MP4                                                  | webm | ogg  |
| ----------------- | ---------------------------------------------------- | ---- | ---- |
| internet explorer | yes                                                  | no   | no   |
| chrome            | yes                                                  | yes  | yes  |
| fiefox            | yes（从firefox 21版本开始 Linux系统从firefox30开始） | yes  | yes  |
| safari            | yes                                                  | no   | no   |
| opera             | yes（从opera25版本开始）                             | yes  | yes  |

**兼容写法：**

由于各个浏览器的支持情况不同，所以我们会有一种兼容性的写法，这种写法了解一下即可

```html
<video  controls="controls"  width="300">
    <source src="move.ogg" type="video/ogg" >
    <source src="move.mp4" type="video/mp4" >
    您的浏览器暂不支持 <video> 标签播放视频
</ video >
```

**上面这种写法，浏览器会匹配video标签中的source，如果支持就播放，如果不支持往下匹配，直到没有匹配的格式，就提示文本**

video常见属性：

| 属性     | 值                                    | 描述                                                         |
| -------- | ------------------------------------- | ------------------------------------------------------------ |
| autoplay | autoplay                              | 视频就绪自动播放（谷歌浏览器需要添加muted来缓解自动播放问题） |
| controls | controls                              | 向用户显示播放控件                                           |
| width    | pixels（像素）                        | 设置播放器的宽度                                             |
| height   | pixels（像素）                        | 设置播放器的高度                                             |
| loop     | loop                                  | 播放完是否继续播放该视频，循环播放                           |
| preload  | auto(预先加载视频) none(不应加载视频) | 规定是否预加载视频(如果有了autoplay，就忽略该属性)           |
| src      | url地址                               | 视频文件地址                                                 |
| poster   | imgurl                                | 加载等待的画面图片                                           |
| muted    | muted                                 | 静音播放                                                     |

**属性很多，有一些属性需要大家重点掌握：**

- `autoplay`  自动播放

  - 注意： 在google浏览器上面，默认禁止了自动播放，如果想要自动播放的效果，需要设置 muted属性

- `width`  宽度

- `height`  高度

- `loop`  循环播放

- `src`  播放源

- `muted` 静音播放

  **示例代码：**

  ```html
  <video src="media/mi.mp4" autoplay="autoplay" muted="muted"  loop="loop" poster="media/mi9.jpg"></video>
  ```


#### 1.22音频audio

当前audio元素支持三种音频格式：

| 浏览器            | MP3  | wav  | ogg  |
| ----------------- | ---- | ---- | ---- |
| internet explorer | yes  | no   | no   |
| chrome            | yes  | yes  | yes  |
| fiefox            | yes  | yes  | yes  |
| safari            | yes  | yes  | no   |
| opera             | yes  | yes  | yes  |

**使用语法：**

```css
<audio src="音频文件地址" controls="controls"></audio>
```

**兼容写法：**

由于各个浏览器的支持情况不同，所以我们会有一种兼容性的写法，这种写法了解一下即可

```html
<audio controls>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
  您的浏览器不支持 audio 元素。
</audio>
```

**上面这种写法，浏览器会匹配audio标签中的source，如果支持就播放，如果不支持往下匹配，直到没有匹配的格式，就提示文本**

audio常见属性：

| 属性值   | 值       | 描述                                                   |
| -------- | -------- | ------------------------------------------------------ |
| autoplay | autoplay | 如果出现该属性，则音频在就绪后马上播放                 |
| controls | controls | 如果出现该属性，则向用户显示控件，比如播放按钮         |
| loop     | loop     | 如果出现该属性，则当音频结束时重新开始播放（循环播放） |
| src      | url      | 要播放音频文件的url地址                                |

**示例代码：**

```html
<audio src="media/music.mp3" autoplay="autoplay" controls="controls"></audio>
```

#### 1.23多媒体标签总结

- 音频标签和视频标签使用方式基本一致
- 浏览器支持情况不同
- 谷歌浏览器把音频和视频自动播放禁止了
- 我们可以给视频标签添加 muted 属性来静音播放视频，音频不可以（可以通过JavaScript解决）
- 视频标签是重点，我们经常设置自动播放，不使用 controls 控件，循环和设置大小属性

### 1.3HTML5新增的input类型

在H5中，帮我们新增加了很多类型的表单，这样方便了程序员的开发

**课堂案例：在这个案例中，熟练了新增表单的用法**

![input案例](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/input%E6%A1%88%E4%BE%8B.png)

**案例代码：**

```html
<!-- 我们验证的时候必须添加form表单域 -->
<form action="">
    <ul>
        <li>邮箱: <input type="email" /></li>
        <li>网址: <input type="url" /></li>
        <li>日期: <input type="date" /></li>
        <li>时间: <input type="time" /></li>
        <li>数量: <input type="number" /></li>
        <li>手机号码: <input type="tel" /></li>
        <li>搜索: <input type="search" /></li>
        <li>颜色: <input type="color" /></li>
        <!-- 当我们点击提交按钮就可以验证表单了 -->
        <li> <input type="submit" value="提交"></li>
    </ul>
</form>
```

 **常见输入类型**

```
text password radio checkbox button file hidden submit reset image
```

**新的输入类型：**

| 属性值        | 说明                      |
| ------------- | ------------------------- |
| type="email"  | 限制用户必须输入email类型 |
| type="url"    | 限制用户必须输入url类型   |
| type="date"   | 限制用户必须输入日期类型  |
| type="time"   | 限制用户必须输入时间类型  |
| type="month"  | 限制用户必须输入月类型    |
| type="week"   | 限制用户必须输入周类型    |
| type="number" | 限制用户必须输入数字类型  |
| type="tel"    | 限制用户必须输入手机号    |
| type="search" | 搜索框                    |
| type="color"  | 生辰一个颜色选择表单      |

类型很多，我们现阶段**重点记忆三个**： **`number`   `tel`   `search`**



### 1.14HTML5新增的表单属性

| 属性         | 值        | 说明                                                         |
| ------------ | --------- | ------------------------------------------------------------ |
| required     | requited  | 表单拥有该属性表示其内容不能为空，必填                       |
| placeholder  | 提示文本  | 表单的提示信息，存在默认值将不显示                           |
| autofocus    | autofocus | 自动聚焦属性，页面加载完自动聚焦到指定表单                   |
| autocomplete | off/on    | 当用户在字段开始键入时，浏览器基于之前键入过的值，应该显示出在字段中填写的选项。<br />默认已经打开，如autocomplete="on",关闭autocomplete="off"需要放在表单内，同时加上name属性，同时成功提交 |
| multiple     | multiple  | 可以多选文件提交                                             |

可以通过以下设置方式修改placeholder里面的字体颜色：

```css
input::placeholder{
    color: pink;
}
```

## 二、CSS3新特性

### 2.1css3的现状

- 新增的CSS3特性有兼容性问题，ie9+才支持
- 移动端支持优于 PC 端 
- 不断改进中 
- 应用相对广泛
- 现阶段主要学习：新增选择器和盒子模型以及其他特性

### 2.2CSS3 给我们新增选择器

- 属性选择器
- 结构伪类选择器
- 伪元素选择器

####  2.21属性选择器

属性选择器可以根据元素特定属性来选择元素。这样就可以不用借助于类或者id选择器。

| 选择器        | 简介                                  |
| ------------- | ------------------------------------- |
| E[att]        | 选择具有att属性的E元素                |
| E[att="val"]  | 选择具有att属性且属性值等于val的E元素 |
| E[att^="val"] | 匹配具有att属性且值以val开头的E元素   |
| E[att$="val"] | 匹配具有att属性且值以val结尾的E元素   |
| E[att*="val"] | 匹配具有att属性且值中含有val的E元素   |

**示例代码：**

```css
/* 只选择具有value属性的input */
input[value]{
    color: pink;
}
/* 只选择 type =text 文本框的input 选取出来 */
input[type=text] {
    color: pink;
}
/* 选择首先是div 然后 具有class属性 并且属性值 必须是 icon开头的这些元素 */
div[class^=icon] {
    color: red;
}
/* 选择首先是section 然后 具有class属性 并且属性值 必须是 data结尾的这些元素 */
section[class$=data] {
    color: blue;
}

/* 选择首先是section 然后 具有class属性 并且属性值中 必须包含3的这些元素 */
section[class*='3'] {
    color:blue;
}

[]中括号中的属性选择器的权重是10，括号外的标签选择器是1，所以section[class$=data]权重是11
```

- 属性选择器，按照字面意思，都是根据标签中的属性来选择元素
- 属性选择器可以根据元素特定属性的来选择元素。 这样就可以不用借助于类或者id选择器
- 属性选择器也可以选择出来自定义的属性
- **注意：类选择器、属性选择器、伪类选择器，权重为 10。**

#### 2.22结构伪类选择器

结构伪类选择器主要根据**文档结构**来选择，常用于根据父级选择器里面的子元素。

| 选择符           | 简介                          |
| ---------------- | ----------------------------- |
| E:first-child    | 匹配父元素中的第一个子元素E   |
| E:last-child     | 匹配父元素中的最后一个子元素E |
| E:nth-child(n)   | 匹配父元素中的第n个子元素E    |
| E:first-of-type  | 指定类型E的第一个             |
| E:last-of-type   | 指定类型E的最后一个           |
| E:nth-of-type(n) | 指定类型E的第n个              |

**示例：**

```css
/* 1. 选择ul里面的第一个孩子 小li */
ul li:first-child {
    background-color: pink;
}

/* 2. 选择ul里面的最后一个孩子 小li */
ul li:last-child {
    background-color: pink;
}

/* 3. 选择ul里面的第2个孩子 小li */
    ul li:nth-child(2) {
    background-color: skyblue;
}
ul li:nth-child(6) {
    background-color: skyblue;
}
```

**nth-child(n) 选择某个父级元素的一个或者多个特定的子元素**

- n可以是数字，关键字，或者公式

- n如果是数字，就是选择第n个元素，里面从1开始

- n可以是关键字：even偶数，odd奇数

- n可以是公式：常规的公式如下(如果n是公式，则从0开始计算，但是第0个元素或者超出了元素的个数会被忽略)

  | 公式 | 取值                           |
  | ---- | ------------------------------ |
  | 2n   | 偶数                           |
  | 2n+1 | 奇数                           |
  | 5n   | 5、10、15...                   |
  | n+5  | 从第五个开始(包含第五个)到最后 |
  | -n+5 | 前五个(包含第五个)             |

**E:nth-child 和 E:nth-of-type 的区别：**

这里只讲明  **E:nth-child(n)**  和 **E:nth-of-type(n)**  的区别  剩下的 **E:first-of-type**     **E:last-of-type**  **E:nth-last-of-type(n)**   同理做推导即可

```css
<style>
    ul li:nth-child(2){
      /* 字体变成红色 */
        color: red;
    }

    ul li:nth-of-type(2){
      /* 背景变成绿色 */
      background-color: green;
    }
  </style>


  <ul>
    <li>列表项一</li>
    <p>乱来的p标签</p>
    <li>列表项二</li>
    <li>列表项三</li>
    <li>列表项四</li>
  </ul>
```

![nth-child与nth-of-type区别](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/nth-child%E4%B8%8Enth-of-type%E5%8C%BA%E5%88%AB.png)

也就是说：

- `E:nth-child(n)`     匹配父元素的第n个子元素E，也就是说，nth-child 对父元素里面所有孩子排序选择（序号是固定的）  先找到第n个孩子，然后看看是否和E匹配
- `E:nth-of-type(n)` 匹配同类型中的第n个同级兄弟元素E，也就是说，对父元素里面指定子元素进行排序选择。 先去匹配E ，然后再根据E 找第n个孩子

小结：

- 结构伪类选择器一般用于选择父级里面的第几个孩子
- nth-child对父元素里面所有的孩子排序选择(序号是固定的) 先找到第n个孩子，然后在看是否和E匹配
-  nth-of-type 对父元素里面指定子元素进行排序。先去匹配E，然后在根据E找第n个孩子。
- 关于 nth-child(n) 我们要知道n都是从0开始计算的，要记住常用的公式
- 如果是无序列表，我们肯定用nth-child更多。
- 类选择器、属性选择器、伪类选择器，权重都为10.

#### 2.23伪元素选择器(重点)

伪元素选择器可以帮助我们利用css创建新标签元素，而不需要html标签，从而简化html结构。

| 选择符   | 简介                     |
| -------- | ------------------------ |
| ::before | 在元素内部的前面插入内容 |
| ::after  | 在元素内部的后面插入内容 |

注意：

- ==before== 和 ==after==创建一个元素，但是属于行内元素
- 新创建的这个元素在文档树中是找不到的，所以我们称为==伪元素==
- ==语法：element::before{}==
- bifore 和 after ==必须有content属性==
- before在父元素内容的前面创建元素，after在父元素内容的后面插入元素
- ==伪元素选择器和标签选择器一样，权重为1==

#### 2.24伪元素选择器使用场景1:配合字体图标

伪元素字体图标

![image-20220705170730870](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/image-20220705170730870.png)

代码：

```css
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>伪元素字体</title>
    <style>
        @font-face {
  font-family: 'icomoon';
  src:  url('fonts/icomoon.eot?1lv3na');
  src:  url('fonts/icomoon.eot?1lv3na#iefix') format('embedded-opentype'),
    url('fonts/icomoon.ttf?1lv3na') format('truetype'),
    url('fonts/icomoon.woff?1lv3na') format('woff'),
    url('fonts/icomoon.svg?1lv3na#icomoon') format('svg');
  font-weight: normal;
  font-style: normal;
  font-display: block;
}
        div{
            position: relative;
            height: 35px;
            width: 200px;
            border: 1px solid red;

        }
        div::after{
            position: absolute;
            line-height: 35px;
            right: 10px;
            font-family: 'icomoon';
            content: "\e91e";
            line-height: 35px;
            color: red;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <div></div>
</body>
</html>
```

#### 2.25伪元素选择器使用场景2:仿土豆

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>伪元素选择器使用场景2-仿土豆网显示隐藏遮罩案例</title>
    <style>
        .tudou {
            position: relative;
            width: 444px;
            height: 320px;
            background-color: pink;
            margin: 30px auto;
        }

        .tudou img {
            width: 100%;
            height: 100%;
        }

        .tudou::after {
            content: '';
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, .4) url(images/arr.png) no-repeat center;
        }
        /* 当我们鼠标经过 土豆这个盒子，就让里面before遮罩层显示出来 */
        .tudou:hover::after{
            display: block;
        }
    </style>
</head>

<body>
    <div class="tudou">
        <img src="images/tudou.jpg" alt="">
    </div>
    <div class="tudou">
        <img src="images/tudou.jpg" alt="">
    </div>
    <div class="tudou">
        <img src="images/tudou.jpg" alt="">
    </div>
    <div class="tudou">
        <img src="images/tudou.jpg" alt="">
    </div>
</body>

</html>
```

#### 2.26伪元素选择器使用场景3:伪元素清除浮动

1. 额外标签法也称隔墙法，是w3c推荐的做法
2. 父级添加overflow属性
3. 父级添加after伪元素
4. 父级添加双伪i元素

后面两种伪元素清除浮动算是第一种额外标签法的一个升级和优化

![单伪元素](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/%E5%8D%95%E4%BC%AA%E5%85%83%E7%B4%A0.png)

![双伪元素](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/%E5%8F%8C%E4%BC%AA%E5%85%83%E7%B4%A0.png)

### 2.3CSS3盒子模型

css3中可以通过box-sizing来指定盒模型，有2个值：即可以指定为content-box、border-box，这样我们计算盒子大小的方式就发生了改变。

可以分成两种情况：

1. box-sizing:content-box盒子大小为width+padding+border（以前默认的计算方式）
2. box-sizing:border-box盒子大小为width
3. 如果盒子模型我们更改为box-sizing:border-box，那padding和border就不会撑大盒子了（前提padding和border不会超过width宽度）

```css
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
```

### 2.4CSS3其他特性(了解)

图片变模糊

计算盒子宽度width:calc 函数

#### 2.41图片变模糊-滤镜filter

filter CSS属性将模糊或颜色偏移等图形效果应用于元素。

```css
filter:函数();     例如：filter:blur(5px);  blur模糊处理，数值越大越模糊
```

![filter](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/filter.png)

#### 2.42calc函数

calc() 此函数让你在声明css属性值时执行一些计算

```css
width:calc(100% - 30px);    /* 注意注意 一定要在加减左右加空格 */
```

括号里面可以使用+ - * / 来进行计算。

### 2.5css3过度(重点)

过渡是css3中具有颠覆性的特征之一，我们可以在不使用flash动画或者js的情况下，当元素从一种样式变换为另一种样式时为元素添加效果。

过渡动画：是一从一个状态渐渐的过渡到另外一个状态

可以让我们页面更好看，更动感十足，虽然 低版本浏览器不支持（ie9一下版本），但是不会影响页面布局。

**我们经常和:hover一起搭配使用。**

**过渡的使用口诀：谁做过渡给谁加**

```css
transition: 要过渡的属性 花费时间 运动曲线 何时开始;
```

1. 属性：想要变化的css属性，宽度高度 背景颜色 内外边距都可以。如果想要所有的属性都变化过渡，写一个all就可以。
2. 花费时间：单位是 秒（必须些单位） 比如0.5s
3. 运动曲线：默认是ease（可以省略）
4. 合适开始：但是是秒 （必须写单位） 可以设置延迟触发时间， 默认是0s（可以省略）

![运动曲线](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/%E8%BF%90%E5%8A%A8%E6%9B%B2%E7%BA%BF.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>过渡</title>
    <style>
        div {
            width: 200px;
            height: 100px;
            background-color: pink;
            /* 如果想要写多个属性，利用逗号进行分割 */
           /* transition: width 1s ease 3s, height 1s ease 3s;*/
            /* 要多个属性都变化也可以写all */
            transition: all 0.5s;
        }

        div:hover {
            width: 400px;
            height: 200px;
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

### 2.6进度条案例

![进度条](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/%E8%BF%9B%E5%BA%A6%E6%9D%A1.png)

1. 进度条如何布局
2. 过渡的使用
