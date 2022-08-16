# css三大特性

## 目标：

1. 能够准确阐述盒子模型的4个组成部分
1. 能够利用边框复合写法给元素添加边框
4. 能够计算盒子的实际大小
4. 能够利用盒子模型布局模块案例
4. 能够给盒子设计圆角边框
4. 能够给盒子添加阴影
4. 能够给文字添加阴影

## 目录：

1. 盒子模型
2. ps基本操作
3. 综合案例
3. 圆角边框
3. 盒子阴影
3. 文字阴影

## 一、盒子模型

页面布局要学习三大核心，盒子模型、浮动和定位。学习好盒子模型能非常好的帮助我们布局页面

### 1.1看透网页布局的本质

网页布局过程：

- 先准备好相关的网页元素，网页元素基本都是盒子box
- 利用css设置好盒子样式，然后摆放到相应的位置
- 往盒子里装内容

### 1.2盒子模型组成

所谓盒子模型：就是html页面中的布局元素看作是一个矩形的盒子，也就是一个盛装内容的容器。

css盒子模型本质上是一个盒子，封装周围的html元素，它包括：边框、内边距、外边距和实际内容。 

![截屏2022-05-31 14.33.58](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/%E6%88%AA%E5%B1%8F2022-05-31%2014.33.58.png)

### 1.3border(边框)

border可以设置元素的边框。边框有三部分组成：边框宽度(粗细)、边框样式、边框颜色

语法：

```css
border: border-width |border-style|border-color
```



| 属性         | 作用                               |
| ------------ | ---------------------------------- |
| border-width | 定义边框的粗细，单位是px           |
| border-style | 定义边框的样式（实线、虚线、点线） |
| border-color | 定义边框的颜色                     |

css边框属性允许你指定一个元素边框的样式和颜色

边框简写：

```css
border: 1px solid red;   边框粗细、样式和颜色没有固定顺序。
```

边框分开写法：

```css
border-top: 1px solid red;  只设置上边框，其余同理
```

课堂练习：请给出一个200*200的盒子，设置上边框为红色，其余边框为蓝色(注意边框的层叠性)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>案例</title>
    <style>
        div {
            width: 180px;
            height: 180px;
            border: 10px solid blue;
            border-top: 10px solid red;
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

### 1.4表格的细线边框

border-collapse属性控制浏览器绘制表格边框的方式。它控制相邻两个单元格的边框。

语法：

```css
border-collapse: collapse;
```

- collapse 单词是合并的意思
- border-collapse: collapse; 表示相邻边框合并在一起（如果不合并的话，边框的粗细为5px，相邻的两个边框的线会变成10px，会变粗）

### 1.5边框会影响盒子的实际大小

边框会额外增加盒子的实际大小。因此我们有两种解决方案：

- 测量盒子大小的时候不测量边框
- 如果测量的时候包含了边框，则需要width/height减去边框的宽度

### 1.6内边距(padding)

padding属性用于设置内边距，即边框与内容之间的距离。

| 属性           | 作用     |
| -------------- | -------- |
| padding-left   | 左内边距 |
| padding-right  | 右内边距 |
| padding-top    | 上内边距 |
| padding-bottom | 下内边距 |

padding属性的简写，可以有1到4个值。

| 值的个数                     | 表达的意思                                                   |
| ---------------------------- | ------------------------------------------------------------ |
| padding: 5px;                | 1个值，代表上下左右都有5像素的内边距                         |
| padding: 5px 10px;           | 两个值，代表上下内边距是5像素，左右内边距是10像素            |
| padding: 5px 10px 20px;      | 三个值，代表上内边距5像素，左右内边距10像素，下内边距20px    |
| padding: 5px 10px 20px 30px; | 四个值，代表上内边距5像素，右内边距10像素，下内边距20像素，左内边距30像素。顺时针 |

当我们给盒子指定padding值后，发生了两件事：

- 内容和边框有了距离，添加了内边距
- padding也会影响盒子的实际大小。

也就是说，如果盒子已经有了宽度和高度，此时在指定内边距，就会撑大盒子。

**解决方案：**

如果保证盒子跟效果图大小保持一致，则让width/height减去多出来的内边距大小即可。

**不撑开盒子的方法：**

如果盒子本身没有指定width/height属性，则此时padding不会撑开盒子大小。

### 1.7案例-新浪导航栏- padding影响盒子好处

padding内边距可以撑开盒子，我们可以巧妙运用此方法。

因为每个导航栏里面的文字个数是不固定的，我们可以不设置盒子的宽度，直接给padding最合适。

相关取值：

- 上边框为3px，颜色为#ff8500

- 下边框为1px，颜色为#edeef0

- 盒子高度为41px，背景色为#fcfcfc

- 文字颜色为#4c4c4c

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .nav {
            height: 37px;
            border-top: 3px solid #ff8500;
            border-bottom: 1px solid #edeef0;
            background-color: #fcfcfc;
            line-height: 37px;
        }

        .nav a {
            display: inline-block;
            text-decoration: none;
            font-size: 12px;
            color: #4c4c4c;
            padding: 0 20px;
        }

        .nav a:hover {
            background-color: #eee;
            color: #ff8500;
        }
    </style>
</head>

<body>
    <div class="nav">
        <a href="">设为首页</a>
        <a href="">手机新浪网</a>
        <a href="">移动客户端</a>
        <a href="">博客</a>
        <a href="">微博</a>
        <a href="">关注我</a>
    </div>
</body>

</html>
```

- 小米导航栏案例修改-padding影响盒子大小计算

  padding内边距可以撑开盒子，有时候也会让我们去修改宽度

  所以小米侧边栏这个案例，文字距离左侧的距离不应该用text-indent这样不精确

  实际开发的做法是给padding值，这样更加精确

### 1.8外边距（margin）

margin属性用于设置外边距，即控制盒子与盒子之间的距离

| 属性          | 作用     |
| ------------- | -------- |
| margin-left   | 左外边距 |
| margin-right  | 右外边距 |
| margin-top    | 上外边距 |
| margin-bottom | 下外边距 |

margin简写方式跟padding完全一致。

**外边距的典型应用：**

外边距可以让块级盒子水平居中，但是必须满足两个条件：

- 盒子必须指定了宽度(width)。
- 盒子的左右外边距都设置为auto。

```css
.header {width:960px margin:0 auto;}
```

常见的写法有以下三种：

- margin-left: atuo;  margin-right: auto;
- margin: auto;
- margin: 0 auto;(常用此写法)

注意：以上方法是让块级元素水平居中，行内元素或者行内块元素水平居中给其父元素添加text-align: center即可。

### 1.9外边距合并

使用margin定义块元素的垂直外边距时，可能会出现外边距的合并。

主要有两种情况：

- 相邻块元素垂直外边距的合并
- 嵌套块元素垂直外边距的塌陷

#### 1.9.1相邻块元素垂直外边距的合并

当上下相邻的两个块元素相遇时，如果上面的元素有下外边距(margin-bottom)，下面的元素有上外边距(margin-top)，则他们之间的垂直间距不是matgin-bottom与margin-top之和。**而是取两个值中较大者(margin-top为200px，margin-bottom为100px，此时两个块元素之间的距离是200px)，这种现象被称为垂直外边距的合并。**

![截屏2022-06-01 12.04.52](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/%E6%88%AA%E5%B1%8F2022-06-01%2012.04.52.png)

**解决方案：尽量只给一个盒子添加margin值**

#### 1.9.2嵌套块元素垂直边距塌陷

对于两个嵌套关系(父子级关系)的块元素，父元素有上外边距，同时子元素也有上外边距，此时父元素会塌陷较大的外边距值(父级元素的上外边距是30px，子元素的上外边距是50px，此时父元素的上外边距也就变成50px)

![截屏2022-06-01 12.28.52](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/img/%E6%88%AA%E5%B1%8F2022-06-01%2012.28.52.png)

**解决方案：**（三选一，实际开发使用overflow: hidden较多）

- 可以为父元素定义上边框。
- 可以为父元素定义上内边距。
- 可以为父元素添加overflow: hidden。

还有其他方法，比如浮动、固定、绝对定位的盒子不会有塌陷问题，后面遇到在总结。

### 2.0清除内外边距

网页元素很多都带有默认的内外边距，而且不同浏览器默认的也不一致，因此我们在布局前，先要清除下网页元素的内外边距。

```css
* {
    margin: 0;  #清除内边距
    padding: 0;  #清除外边距
}
```

注意：行内元素为了照顾兼容性，尽量是设置左右内外边距，不要设置上下内边距。但是转换为块级和行内块级元素就可以了。

##   二、ps基本操作

因为网页美工大部分效果图都是利用ps来做的，所有以后我们大部分切图工作都在ps里面完成。

### 2.1基本操作

- 文件—>打开：可以打开我们要测量的图片
- ctrl+R：可以打开标尺，或者视图—>标尺
- 右击标尺，把里面的单位改为像素
- ctrl+加号可以放大视图，ctrl+减号可以缩小视图
- 按住空格键，鼠标可以变成小手，拖动ps视图
- 用选区拖动，可以测量大小
- ctrl+D可以取消选区，或者在旁边空白处点击一下也可以取消选区

## 三、圆角边框

在css3中，新增了圆角边框样式，这样我们的盒子就可以变成圆角了。

### 3.1语法

border-radius属性用于设置元素的外边框圆角

```css
border-radius: length;
```

- 参数值可以为数值或百分比的形式
- **如果是正方形，想要设置一个圆，把数值修改为高度或者宽度的一半即可，或者直接写50%**
- **如果是一个矩形，设置为高度的一半就可以做圆矩形**
- 该属性是一个简写属性，可以跟四个值，border-radius: 10px 20px 30px 40px;分别代表左上角10px，右上角20px，右下角30px，左下角40px
- 分开写：border-top-left-radius、border-top-right-radius、border-bottom-right-radius、border-bottom-left-radius

## 四、盒子阴影(重要)

css3中新增了盒子阴影，我们可以使用box-shadow属性为盒子添加阴影

### 4.1语法

```css
box-shadow: h-shadow v-shadow blur spread color inset;
```

| 值       | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| h-shadow | 必需，水平阴影的位置，允许负值                               |
| v-shadow | 必需，垂直阴影的位置，允许为负值                             |
| blur     | 可选，模糊距离（影子虚实，数值越大，影子越虚）               |
| spread   | 可选，阴影的尺寸（阴影的大小，数值越大，影子越大）           |
| color    | 可选，阴影的颜色。参与css颜色值                              |
| inset    | 可选，将外部阴影(outset)改为内部阴影（默认outset外阴影不用写，如果写上导致阴影没效果） |

**注意：**

- 默认的是外阴影(outset)，但是不可以写这个单词，否则导致阴影无效

- 盒子阴影不会占用空间，不会影响其盒子的排列

## 五、文字阴影(了解)

在css3中，我们可以使用text-shadow属性将阴影应用于文本

### 5.1语法

```css
text-shadow: h-shadow v-shadow blur  color ;
```

| 值       | 描述                                           |
| -------- | ---------------------------------------------- |
| h-shadow | 必需，水平阴影的位置，允许负值                 |
| v-shadow | 必需，垂直阴影的位置，允许为负值               |
| blur     | 可选，模糊距离（影子虚实，数值越大，影子越虚） |
| color    | 可选，阴影的颜色。参与css颜色值                |

