# css高级技巧

## 目标：

1. 能够使用精灵图
1. 能够使用字体图标
1. 能够写出css三角
1. 能够写出常见的css用户界面样式
1. 能够说出常见的布局技巧

## 目录：

1. 精灵图
2. 字体图标
3. css三角
4. css用户界面样式
4. vertical-align属性应用
4. 溢出的文字省略号显示
4. 常见布局技巧

## 一、精灵图

### 1.1为什么需要精灵图

![1571482435259](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571482435259.png)

一个网页中往往会应用很多小的背景图像作为修饰，当网页中的图像过多时，服务器就会频繁地接受和发送请求图片，造成服务器请求压力过大，这将大大降低页面的加载速度。

因此，为了有效的减少服务器接收和发送请求的次数，提高页面的加载速度，出现了css精灵技术（也称css sprites、css雪碧）

**核心原理：将网页中的一些小背景图像整合到一张大图中，这样服务器只需要一次请求就可以了。**

**精灵技术目的：为了有效的减少服务器接收和发送请求的次数，提高页面的加载速度。**

### 1.2精灵图的使用

**使用精灵图核心：**

1. 精灵技术主要针对背景图片使用。就是把多个小背景图片整合到一张大图片中。
2. 这个大图片也成为sprites精灵图 或者 雪碧图
3. 移动背景图片位置，此时可以使用background-position。
4. 移动的距离就是这个目标图片的x和y坐标。注意网页中的坐标有所不同
5. 因为一半情况下都是往上往左移动，所以数值是负值。
6. 使用精灵图的时候需要精确测量，每个小背景图片的大小和位置

**使用精灵图核心总结：**

1. 精灵图主要针对小的背景图片使用
2. 主要借助背景位置来实现——background-position。
3. 一般情况下精灵图都是负值。（千万主页网页中的坐标：x轴右边走是正值，左边走是负值，y轴同理。）

### 1.3精灵图代码实现

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>精灵图实现</title>
    <style>
        .box1 {
            width: 57px;
            height: 57px;
            /* background-color: pink; */
            margin: 50px auto;
            background: url(images/sprites.png) no-repeat -183px 0;
        }

        .box2 {
            width: 25px;
            height: 25px;
            margin: 50px auto;
            background: url(images/sprites.png) no-repeat -156px -106px;
        }
    </style>
</head>

<body>
    <div class="box1"></div>
    <div class="box2"></div>
</body>

</html>
```

### 1.4案例-使用精灵语拼出king

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拼出英文名字</title>
    <style>
        div {
            float: left;
            background: url(images/abcd.jpg) no-repeat;
        }

        .k {
            width: 106px;
            height: 112px;
            background-position:  -494px -142px;
        }

        .i {
            width: 62px;
            height: 108px;
            background-position: -326px -141px;
        }

        .n {
            width: 113px;
            height: 113px;
            background-position: -255px -274px;
        }

        .g {
            width: 105px;
            height: 110px;
            background-position: -97px -140px;
        }
    </style>
</head>

<body>
    <div class="k"></div>
    <div class="i"></div>
    <div class="n"></div>
    <div class="g"></div>
</body>

</html>
```



## 二、字体图标

### 2.1字体图标的产生

字体图标使用场景：主要用于显示网页中通用、常用的一些小图标。

精灵图是有诸多优点的，但是缺点很明显：

1. 图片文件还是比较大额
2. 图片本身放大和缩小会失真
3. 一旦图片制作完毕想要更换非常复杂

此时，有一种技术的出现很好的解决了以上问题，就是**字体图标iconfont**

**字体图标**可以为前端工程师提供一种方便高效的图标使用方式，**展示的是图标，本质属于字体。**

### 2.2字体图标的优点

- 轻量级：一个图标字体要比一系列的图像要小。一旦字体加载了，图标会马上渲染出来，减少了服务器请求
- 灵活性：本质其实是文字，可以很随意的改变颜色、产生阴影、透明效果、旋转等
- 兼容性：几乎支持所有的浏览器，请放心使用

注意：字体图标不能替代精灵技术，只是对工作中图标部分技术的提升和优化。

总结：

1. 如果遇到一些结构和样式比较简单的小图标，就用字体图标。
2. 如果遇到一些结构和样式复杂一点的小图片，就用精灵图。

### 2.3字体图标的使用

字体图标是一些网页常见的小图标，我们直接往上下载即可。因此使用可以分为：

1. 字体图标的下载
2. 字体图标的引入（引入到我们的html页面中）
3. 字体图标的追加（以后添加新的小图标）

#### 2.31字体图标的下载

推荐下载网站：

- icomoon字库 https://icomoon.io

  成立于2011年，推出第一个自定义图标字体生成器，它允许用户选择所需要的图标，使它们成一字型。该字库内容种类繁多，非常全面，唯一遗憾的是服务器在国外，访问速度可能会慢。

- 阿里iconfont字库 https://www.iconfont.cn

  这个是阿里妈妈的一个字体图标字库，包含了淘宝图标库和阿里妈妈图标库。可以使用AI制作图标上传生成

#### 2.32字体图标的引入

下载好的字体文件不要删除，后面会使用。

1. 把下载的字体包解压，解压后里面有个fonts的文件夹，把fonts这个文件夹放到项目的根目录![1571520092646](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571520092646.png)

   不同浏览器所支持的字体格式是不一样的，字体图标之所以兼容，就是因为包含了主流浏览器支持的字体文件。

   1).TureType(  **.ttf**  )格式.ttf字体是Windows和Mac的最常见的字体，支持这种字体的浏览器有IE9+、Firefox3.5+、Chrome4+、Safari3+、Opera10+、iOS Mobile、Safari4.2+；

   2).Web Open Font Format( **.woff** )格式woff字体，支持这种字体的浏览器有IE9+、Firefox3.5+、Chrome6+、Safari3.6+、Opera11.1+；

   3).Embedded Open Type( **.eot** )格式.eot字体是IE专用字体，支持这种字体的浏览器有IE4+；

   4).SVG(  .**svg**  )格式.svg字体是基于SVG字体渲染的一种格式，支持这种字体的浏览器有Chrome4+、Safari3.1+、Opera10.0+、iOS Mobile Safari3.2+；

2. 在css样式中全局声明字体：简单理解把这些文字文件通过css引入到我们页面中。一定要注意字体文件路径的问题

   ```css
    @font-face {
      font-family: 'icomoon';
      src:  url('fonts/icomoon.eot?7kkyc2');
      src:  url('fonts/icomoon.eot?7kkyc2#iefix') format('embedded-opentype'),
        url('fonts/icomoon.ttf?7kkyc2') format('truetype'),
        url('fonts/icomoon.woff?7kkyc2') format('woff'),
        url('fonts/icomoon.svg?7kkyc2#icomoon') format('svg');
      font-weight: normal;
      font-style: normal;
    }
   ```

3. html标签中添加小图标

   ![1571520411345](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571520411345.png)

4. 给标签定义字体样式

   ```css
    span {
      font-family: "icomoon";
    }
   ```

     注意：务必保证 这个字体和上面@font-face里面的字体保持一致 

   ![1571520485350](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571520485350.png)

#### 2.33字体图标的追加

如果工作中，原来的字体图标不够用了，我们需要添加新的字体图标到原来的字体文件中。

把压缩包里面的 **selection.json** 从新上传，然后选中自己想要新的图标，从新下载压缩包，并替换原来的文件即可。

![1571520554317](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571520554317.png)

## 三、CSS三角

### 3.1介绍

网页中常见一些三角形，使用 CSS 直接画出来就可以，不必做成图片或者字体图标。

一张图， 你就知道 CSS 三角是怎么来的了, 做法如下：

![1571520965966](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571520965966.png)

```css
 div {
 	width: 0; 
    height: 0;
    border: 50px solid transparent;
	border-color: red green blue black;
	line-height:0;
    font-size: 0;
 }
```

### 3.2案例-京东三角

![1571521183026](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571521183026.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;

        }

        .jd {
            margin: 100px auto;
            position: relative;
            width: 190px;
            height: 500px;
            background-color: pink;
        }

        .jd>span {
            position: absolute;
            top: -40px;
            right: 20px;
            width: 0;
            height: 0;
            font-size: 0;
            line-height: 0;
            border: 20px solid transparent;
            border-bottom: 20px solid pink;
        }
    </style>
</head>

<body>
    <div class="jd">
        <span></span>
    </div>
</body>

</html>
```

### 3.2案例-小米案例

![image-20220623161755455](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/image-20220623161755455.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .xiaomi{
            position: relative;
            margin: 50px auto;
            width: 135px;
            height: 200px;
            background-color: pink;
        }
        .sanjiao{
            position: absolute;
            top: 10px;
            right: -20px;
            width: 0;
            height: 0;
            line-height: 0;
            font-size: 0;
            border: 10px solid transparent;
            border-left-color: pink;
        }
    </style>
</head>
<body>
    <div class="xiaomi">
        <div class="sanjiao"></div>
    </div>
</body>
</html>
```

## 四、CSS用户界面样式

### 4.1什么是界面样式

所谓的界面样式，就是更改一些用户操作样式，以便提高更好的用户体验。

- 更改用户的鼠标样式
- 表单轮廓
- 防止表单域拖拽

### 4.2鼠标样式cursor

语法：

```css
li {cursor: pointer;}
```

设置或检索在对象上移动的鼠标指针采用何种系统预定义的光标形状。

| 属性值      | 描述      |
| ----------- | --------- |
| default     | 小白 默认 |
| pointer     | 小手      |
| move        | 移动      |
| text        | 文本      |
| not-allowed | 禁止      |

### 4.3表单轮廓线outline

给表单添加outline: 0; 或者 outline: none; 样式之后，就可以去掉默认的蓝色边框。

```css
input {outline: none;}
```

### 4.4防止做拽文本域resize

 实际开发中，我们文本域右下角是不可以拖拽的。

```css
 textarea{ 
 	resize: none;
 }
```

## 五、vertical-alien属性应用

css的vertical-align属性使用场景：经常用于设置图片或者表单（行内块元素）和文字垂直对齐。

官方解释：用于设置一个元素的垂直对齐方式，但是它只针对于行内元素或者行内块元素有效。

### 5.1图片、表单和文字对齐

语法：

```css
标签名 {vertical-align : baseline |top |middle |bottom }
```

| 值       | 描述                                   |
| -------- | -------------------------------------- |
| baseline | 默认。元素防止在父元素的基线上         |
| top      | 把元素的顶端与行中最高元素的顶端对齐   |
| middle   | 把此元素放置在父元素的中部             |
| bottom   | 把元素的顶端与行中最低的元素的底端对齐 |

![1571522040645](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571522040645.png)

图片、表单都属于行内块元素，默认的vertical-align是基线对齐。

![1571522093729](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571522093729.png)

此时可以给图片、表单这些行内块元素vertical-align属性设置为middle 就可以让文字和图片垂直居中对齐了。

```css
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>利用vertical-align实现图片文字垂直居中对齐</title>
    <style>
        img {
            /* vertical-align: bottom; */
            /* 让图片和文字垂直居中 */
            vertical-align: middle;
            /* vertical-align: top; */
        }
        textarea {
            vertical-align: middle;
        }
    </style>
</head>
<body>
    <img src="images/ldh.jpg" alt="">  pink老师是刘德华

    <br>
    <textarea name="" id="" cols="30" rows="10"></textarea> 请您留言
</body>
</html>
```

### 5.3解决图片底部默认空白缝隙问题

bug:图片底侧会有一个空白缝隙，原因是行内块元素和文字的基线对齐。

主要解决方式有两种：

1. **给图片**添加 **vertical-align:middle | top| bottom** 等。 （提倡使用的）
2. 把图片转换为块级元素  **display: block**; 

## 六、溢出的文字省略号显示

### 6.1单行文本溢出显示省略号

![1571522253642](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571522253642.png)

单行文本溢出溢出显示省略号—必须满足三个条件：

```css
  /*1. 先强制一行内显示文本*/
   white-space: nowrap;  （ 默认 normal 自动换行）

  /*2. 超出的部分隐藏*/
   overflow: hidden;

  /*3. 文字用省略号替代超出的部分*/
   text-overflow: ellipsis;
```



### 6.2多行文本溢出显示省略号

![1571522289409](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571522289409.png)

多行文本溢出显示省略号，要设置好盒子高度 。同时**有较大兼容性问题**，适合于webKit浏览器或移动端（移动端大部分是webkit内核）

```css
/*1. 超出的部分隐藏 */
overflow: hidden;

/*2. 文字用省略号替代超出的部分 */
text-overflow: ellipsis;

/* 3. 弹性伸缩盒子模型显示 */
display: -webkit-box;

/* 4. 限制在一个块元素显示的文本的行数 */
-webkit-line-clamp: 2;

/* 5. 设置或检索伸缩盒对象的子元素的排列方式 */
-webkit-box-orient: vertical;
```

**更推荐让后台人员来做这个效果，因为后台人员可以设置显示多少个字，操作更简单。**

## 七、常见布局技巧

巧妙利用一个技术更快更好的布局

### 7.1margin负值的运用

![1571522666082](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571522666082.png)

![1571522683897](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571522683897.png)

1. 让每个盒子margin-left 往左侧移动 -1px 正好压住相邻盒子边框

2. 鼠标经过某个盒子的时候，提高当前盒子的层级即可（如果没有定位，则加相对定位(保留位置)，如果有定位，则加z-index）。

   ```css
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta http-equiv="X-UA-Compatible" content="IE=edge">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           li{
               
               float: left;
               margin-left: -1px;
               list-style: none;
               width: 245px;
               height: 260px;
               /* background-color: pink; */
               border: 1px solid black;
           }
           li:hover{
             /* 如果盒子没有定位，则鼠标经过添加加相对定位即可 */
               position: relative;
               border: 1px solid pink;
           }
       </style>
   </head>
   <body>
       <ul>
           <li></li>
           <li></li>
           <li></li>
           <li></li>
           <li></li>
       </ul>
   </body>
   </html>
   ```

   ```css
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta http-equiv="X-UA-Compatible" content="IE=edge">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           li{
               position: relative;
               float: left;
               margin-left: -1px;
               list-style: none;
               width: 245px;
               height: 260px;
               border: 1px solid black;
           }
           li:hover{
              /* 如果li都有定位，则利用z-index提高鼠标经过的层级 */
               z-index: 1;
               border: 1px solid pink;
           }
       </style>
   </head>
   <body>
       <ul>
           <li></li>
           <li></li>
           <li></li>
           <li></li>
           <li></li>
       </ul>
   </body>
   </html>
   ```

### 7.2文字围绕浮动元素

![1571522777745](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571522777745.png)

这种布局可以巧妙运用浮动元素不会压住文字的特性

```css
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>文字围绕浮动元素的妙用</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .box{
            width: 300px;
            height: 70px;
            background-color: pink;
            padding: 5px;
        }
        .pic{
            float: left;
            width: 120px;
            height: 60px;
            margin-right: 10px;
            
        }
        .pic img{
            width: 100%;
            height: 100%;
        }
    
    </style>

</head>

<body>
    <div class="box">
        <div class="pic">
            <img src="images/img.png" alt="">
        </div>
        <p >【集锦】热身赛-巴西0-1秘鲁 内马尔替补两人血染赛场</p>
    </div>
</body>

</html>
```

### 7.3行内块的巧妙运用

![1571522898744](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571522898744.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>页码案例-利用行内块做</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        input {
            outline: none;
        }

        .box {
            text-align: center;
        }

        .box a {
            display: inline-block;
            width: 40px;
            height: 40px;
            background-color: #f7f7f7;
            border: 1px solid #ccc;
            text-decoration: none;
            text-align: center;
            line-height: 40px;
            color: #333;
            font-size: 14px;
        }

        .box .prev,
        .box .next {
            width: 85px;
            height: 40px;
        }

        .box .current,
        .box .elp {
            border: none;
            background-color: #fff;
        }

        .box input {
            width: 40px;
            height: 40px;
            background-color: #f7f7f7;
            border: 1px solid #ccc;
        }

        .box button {
            width: 56px;
            height: 40px;
            background-color: #f7f7f7;
            border: 1px solid #ccc;
        }
    </style>
</head>

<body>
    <div class="box">
        <a href="#" class="prev">&lt;&lt;上一页</a>
        <a href="#">1</a>
        <a href="#" class="current">2</a>
        <a href="#">3</a>
        <a href="#">4</a>
        <a href="#">5</a>
        <a href="#">6</a>
        <a href="#">7</a>
        <a href="#" class="elp">...</a>
        <a href="#" class="next">&gt;&gt;下一页</a>
        到第<input type="text">页<button>确定</button>
    </div>
</body>

</html>
```

### 7.4css三角强化

![1571522998580](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571522998580.png)

原理：

![1571523024087](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571523024087.png)

![1571550898114](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571550898114.png)

代码：

```css
right: 0;
width: 0;
height: 0;
line-height: 0;
font-size: 0;
  /* 直角三角形上边100px 右边50px 下和左边都是0 */
border-width: 100px 50px 0 0;
/* 直角三角形的样式都是实线 */
border-style: solid;
/* 直角三角形除了右边其他的三个边都是透明色 */
border-color: transparent red transparent transparent;
```

实现：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .price {
            position: relative;
            width: 180px;
            height: 30px;
            border: 1px solid red;
            margin: 100px auto;
            line-height: 30px;
        }

        .miaosha {
            position: relative;
            float: left;
            width: 100px;
            height: 30px;
            background-color: red;
            text-align: center;
            color: #fff;
            font-weight: 700;
            margin-right: 8px;


        }

        .miaosha i {
            position: absolute;
            right: 0;
            top: 0;
            width: 0;
            height: 0;
            line-height: 0;
            font-size: 0;
            border-width: 30px 10px 0 0;
            border-style: solid;
            border-color: transparent #fff transparent transparent;
        }

        .origin {
            font-size: 14px;
            color: gray;
            text-decoration: line-through;
        }
    </style>
</head>

<body>
    <div class="price">
        <span class="miaosha">
            ￥1650
            <i></i></span>
        <span class="origin">￥5088</span>
    </div>
</body>

</html>
```

## 八、CSS初始化

### 8.1css初始化

不同浏览器对有些标签的默认值是不同的，为了消除不同浏览器对HTML文本呈现的差异，照顾浏览器的兼容，我们需要对CSS 初始化

简单理解： CSS初始化是指重设浏览器的样式。 (也称为CSS reset）

每个网页都必须首先进行 CSS初始化。

这里我们以 京东CSS初始化代码为例。

**Unicode编码字体：**

把中文字体的名称用相应的Unicode编码来代替，这样就可以有效的避免浏览器解释CSS代码时候出现乱码的问题。

比如：

黑体 \9ED1\4F53
宋体 \5B8B\4F53
微软雅黑 \5FAE\8F6F\96C5\9ED1

**京东css初始化代码：**

```css
/* 把我们所有标签的内外边距清零 */
* {
    margin: 0;
    padding: 0
}
/* em 和 i 斜体的文字不倾斜 */
em,
i {
    font-style: normal
}
/* 去掉li 的小圆点 */
li {
    list-style: none
}

img {
    /* border 0 照顾低版本浏览器 如果 图片外面包含了链接会有边框的问题 */
    border: 0;
    /* 取消图片底侧有空白缝隙的问题 */
    vertical-align: middle
}

button {
    /* 当我们鼠标经过button 按钮的时候，鼠标变成小手 */
    cursor: pointer
}

a {
    color: #666;
    text-decoration: none
}

a:hover {
    color: #c81623
}

button,
input {
    /* "\5B8B\4F53" 就是宋体的意思 这样浏览器兼容性比较好 */
    font-family: Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB, "\5B8B\4F53", sans-serif
}

body {
    /* CSS3 抗锯齿形 让文字显示的更加清晰 */
    -webkit-font-smoothing: antialiased;
    background-color: #fff;
    font: 12px/1.5 Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB, "\5B8B\4F53", sans-serif;
    color: #666
}

.hide,
.none {
    display: none
}
/* 清除浮动 */
.clearfix:after {
    visibility: hidden;
    clear: both;
    display: block;
    content: ".";
    height: 0
}

.clearfix {
    *zoom: 1
}
```

