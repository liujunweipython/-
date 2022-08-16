# 浮动

## 目标：

- 能够说出为什么需要浮动
- 能够说出浮动的排列特性
- 能够说出3钟最常见的布局方式
- 能够说出为什么需要清除浮动
- 能够写出至少3种清除浮动的方法
- 能够利用photoshop实现基本的切图
- 能够利用photoshop插件实现切图
- 能够完成学成在线的页面布局

## 目录：

- 浮动
- 常见网页布局
- 清除浮动
- ps切图
- 学成在线案例

## 一、浮动

### 1.1传统网页布局的三种方式

网页布局的本质—用css来摆放盒子。把盒子摆放到相应的位置

css提供了三种传统布局方式(简单说，就是盒子如何进行排列顺序)：

- 普通流(标准流) 
- 浮动
- 定位

### 1.2标准流

所谓标准流：就是标签按照规定好默认方式排列

- 块元素会独占一行，从上向下顺序排列。常用元素有：div、hr、p、h1~h6、ul、ol、dl、form、table
- 行内块元素会按照顺序，从左到右顺序排列，碰到父元素边缘则自动换行。常用元素：span、a、i、em

以上就是标准流布局，前面学习的就是标准流，标准流是最基本的布局方式。

这三种布局方式就是用来摆放盒子的，盒子摆放到合适的位置，布局自然就完成了。

==注意：实际开发中，一个页面基本都包含了这三种布局方式。（后面移动端会用到新的布局方式）==

### 1.3为什么需要浮动

**提问：**我们用标准流能很方便的实现如下效果吗？

- 如何让多个块级盒子(div)水平排列成一行？

  ![image-20220608112802724](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/image-20220608112802724.png)

  比较难，虽然转换方式为行内块元素可以实现一行显示，但是他们之间会有部分空白缝隙，很难控制。

- 如何实现两个盒子的左右对齐？

  ![image-20220608113028571](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/image-20220608113028571.png)

  

**总结：**因为很多布局效果，标准流没有办法完成，此时就可以利用浮动完成布局。因为浮动可以改变元素标签默认的排列方式。

浮动最典型的应用：可以让多个块级元素一行内排列显示。

==网页布局第一准则：多个块元素纵向排列找标准流，多个块级元素横向排列找浮动。==

### 1.4什么是浮动

float属性用于创建浮动框，将其移动到一边，直到左边缘或右边缘触及包含块或另一个浮动框的边缘

语法：

```css
选择器 {float: 属性值;}
```

| 属性值 | 描述                 |
| ------ | -------------------- |
| none   | 元素不浮动（默认值） |
| left   | 元素向左浮动         |
| right  | 元素向右浮动         |

### 1.5浮动特性(重难点)

加了浮动之后的元素，会具有很多特性，需要掌握。

- 浮动元素会脱离标准流(脱标)

  - 脱离标准普通流的控制(浮)移动到指定位置(动)，俗称脱标

  - 浮动的盒子不再保留原先的位置，设置了浮动的元素，漂浮在普通流的上面，不占位置，脱标，正常流标准显示

    ![1571544664994](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571544664994.png)

- 如果多个盒子都设置了浮动，则他们会按照属性值一行内显示并且元素顶端对齐排列。

  - 浮动的元素是相互贴靠在一起的(不会有缝隙)，如果父级宽 度装不下这些浮动的盒子，多出的盒子会另起一行对齐。

- 浮动的元素会具有行内块元素的特性

  - 任何元素都可以浮动，不管原先是什么模式的元素，==添加浮动之后具有行内块元素相似的特性==。
  - 如果块级盒子没有设置宽度，默认宽度和父级一样宽，但是添加浮动后，它的大小根据内容来决定
  - 浮动的盒子中间没有缝隙，是紧挨着一起的
  - 行内元素同理

### 1.6浮动元素经常和标准流父级搭配使用

为了约束浮动元素位置，网页布局一般采取的策略是：

==**先用标准流的父元素排列上下位置，之后内部子元素采取浮动排列左右位置，符合网页布局第一准则。**==

==**先设置盒子大小，之后设置盒子的位置是网页布局额第二准则**==

![1571544991989](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571544991989.png)

### 1.7案例

#### 1.71小米布局案例1

![image-20220608143559427](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/image-20220608143559427.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>浮动布局练习1</title>
    <style>
        .box {
            width: 1226px;
            height: 460px;
            background-color: pink;
            margin: 0 auto;
        }

        .left {
            width: 235px;
            height: 460px;
            background-color: purple;
            float: left;

        }

        .right {
            width: 991px;
            height: 460px;
            background-color: skyblue;
            float: left;
        }
    </style>
</head>

<body>
    <div class="box">
        <div class="left"></div>
        <div class="right"></div>
    </div>

</body>

</html>
```

#### 1.72小米布局案例2

![image-20220608145000464](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/image-20220608145000464.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>浮动布局练习2</title>
    <style>
        * {
            margin: 0;
            padding: 0;

        }

        li {
            list-style: none;
        }

        .box {
            width: 1226px;
            height: 285px;
            background-color: pink;
            margin: 0 auto;
        }

        .box li {
            width: 296px;
            height: 285px;
            background-color: purple;
            float: left;
            margin-right: 14px;
        }
        /* 这里必须写.box .last 要注意权重的问题 */
        .box .last {
            margin-right: 0;
        }
    </style>
</head>

<body>
    <ul class="box">
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li class="last">4</li>
    </ul>
</body>

</html>
```

#### 1.73小米布局案例3

![1654674246(1)](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1654674246(1).png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>浮动布局练习3</title>
    <style>
        .box {
            width: 1226px;
            height: 615px;
            background-color: pink;
            margin: 0 auto;
        }

        .box .left {
            width: 234px;
            height: 615px;
            background-color: gray;
            float: left;
        }

        .box .right {
            width: 992px;
            height: 615px;
            background-color: purple;
            float: left;

        }
        .box .right>div{
            width: 234px;
            height: 300px;
            background-color: pink;
            float: left;
            margin-left: 14px;
            margin-bottom: 15px;

        }
    </style>
</head>

<body>
    <div class="box">
        <div class="left"></div>
        <div class="right">
            <div>1</div>
            <div>2</div>
            <div>3</div>
            <div>4</div>
            <div>5</div>
            <div>6</div>
            <div>7</div>
            <div>8</div>
        </div>

    </div>

</body>

</html>
```

## 二、常见网页布局

### 2.1常见网页布局

![image-20220608162330017](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/image-20220608162330017.png)

![image-20220608162501169](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/image-20220608162501169.png)





### 2.2浮动布局注意点

- 浮动和标准流的父盒子搭配
  - 先用标准流的父元素排列上下位置，之后内部子元素采取浮动排列左右位置。
- 一个元素浮动了，理论上其余兄弟元素也要浮动
  - 一个盒子里面有多个子盒子，如果其中一个盒子浮动了，那么其他兄弟也应该浮动，以防止引起问题。
  - 浮动的盒子自会影响浮动盒子后面的标准流，不会影响前面的标准流。

## 三、清除浮动

### 3.1为什么需要清除浮动

由于父盒子在很多情况下不方便设置高度，但是子盒子浮动又不占有位置，最后父级盒子高度为0时，就会影响下面的标准流盒子

![1571555883628](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571555883628.png)

- 由于浮动元素不在占用原文档流的位置，所以他会对后面的元素排版产生影响

### 3.2清除浮动本质

- 清除浮动元素的本质就是清除浮动元素造成的影响
- 如果父盒子本身有高度，则不需要清除浮动
- 清除浮动之后，父级就会根据浮动的子盒子自动检测高度。父级有了高度，就不会影响下面的标准流了

### 3.3清除浮动

语法：

```css
选择器 {
      clear: 属性值;
}
```

| 属性值 | 描述                                       |
| ------ | ------------------------------------------ |
| left   | 不允许左侧有浮动元素（清除左侧浮动的影响） |
| right  | 不允许右侧有浮动元素（清除右侧浮动的影响） |
| both   | 同时清除左右两侧浮动的影响                 |

实际工作中，几乎只用clear: both;

清除浮动的策略是：闭合浮动

### 3.4清除浮动方法

#### 3.41额外标签发

额外标签法也称为隔墙法，是w3c推荐的做法

额外标签法会在浮动元素末尾添加一个空标签。例如`<div style="clear: both"><div>`，或者其他标签（如`</br>`）等。

- 优点：通俗易懂，书写方便
- 缺点：添加许多无意义的标签，结构化比较差

**注意：**要求这个新的空标签必须是块级元素。

总结：

- 清除浮动本质是：清除浮动元素脱离标准流造成的影响
- 清除浮动策略是：闭合浮动，只让浮动在父盒子内部印象，不影响父盒子外面的其他盒子
- 额外标签法：也称隔墙法，就是在最后一个浮动的子元素后面添加一个额外标签，添加清除浮动样式

#### 3.42父级添加overflow属性（重点）

可以给父级添加overflow属性，将其属性值设置为hidden、auto或scroll。

```css
父级元素的属性中添加
overflow: hidden;
```

优点：代码简洁

缺点：无法显示溢出部分

#### 3.43父级添加after伪元素（重点）

:after方式是额外标签法的升级版。也是给父元素添加

```css
.clearfix:after {
    content: "";
    display: block;
    height: 0;
    clear: both;
    visibility: hidden;
}

.clearfix {
    /* IE6、7 专有 */
    *zoom: 1;
}
```

- 优点：没有增加标签，结构简单
- 缺点：照顾低版本浏览器

#### 3.44父级添加双伪元素（重点）

也是给父元素添加

```css
.clearfix:before,
.clearfix:after {
    content: "";
    display: table;
}

.clearfix:after {
    clear: both;
}

.clearfix {
    *zoom: 1;
}
```

- 优点：代码更简洁
- 缺点：照顾低版本浏览器

#### 3.45清除浮动总结

为什么需要清除浮动？

- 父级没有高度
- 子盒子浮动了
- 影响下面布局了，我们就应该清除浮动了。


浮动的四种方法：

- | 清除浮动的方法         | 优点               | 缺点                              |
  | ---------------------- | ------------------ | --------------------------------- |
  | 额外标签法（隔墙法）   | 通俗易懂，书写方便 | 添加许多无意义的标签，结构化较差  |
  | 父级overflow：hidden； | 书写简单           | 溢出隐藏                          |
  | 父级after伪元素        | 结构语义化正确     | 由于IE6-7不支持:after，兼容性问题 |
  | 父级双伪元素           | 结构语义化正确     | 由于IE6-7不支持:after，兼容性问题 |

## 四、ps切图

### 4.1常见的图片格式

1. jpg图像格式：JPEG（JPG）对色彩的信息保留较好 ，高清，颜色较多，我们==产品类的图片经常用jpg格==
    ==式的==
2. git图像格式：GIF格式最多只能储存256色，所以通常用来显示简单图形及字体，但是可以保存透明背景
    和动画效果，==实际经常用于一些图片小动画效果==
3. png图像格式是一种新兴的网络图形格式，结合了GIF和JPEG的优点，具有存储形式丰富的特点，能够保
    持透明背景.==如果想要切成背景透明的图片,请选择png格式.==
4. PSD图像格式PSD格式是Photoshop的专用格式，里面可以存放图层、通道、遮罩等多种设计稿.==对我们==
    ==前端人员来说,最大的优点,我们可以直接从上面复制文字,获得图片,还可以测量大小和距离==

### 4.2图层切图

最简单的切图方式：右击图层—>快速导出为PNG。

但是很多情况下，我们需要合并图层在导出：

- 选中需要的图层：图层菜单—>合并图层（ctrl+e）
- 右击—>快速导出为PNG

### 4.3切片切图

- 利用切片选中图片：利用切片工具手动划出

- 导出选中的图片：文件菜单—>导出—>存储为web设备所用格式—>选择我们要的图片格式—>存储

### 4.4ps插件切图

cutterman是一款运行在photoshop中的插件，能够自动将你需要的图层进行输出，以替代传统的手工“导出web所用格式”以及使用切片工具进行挨个切图的繁琐流程。

官网：www.cutterman.cn/zh/cutterman

注意：插件要求ps必须是完整版的，不可以是绿色版本。

## 五、学成在线 案例

### 5.1准备素材和工具

- 学成在线psd源文件
- 开发工具=ps/cutterman插件+vscode+chrome

### 5.2案例准备工作

本次采取结构与样式相分离思想：

- 创建学成在线文件夹用于存放相关内容
- 用vscode打开这个文件夹
- 在目录里面新建img文件夹，用于存放图片
- 新建首页文件index.html（以后网站首页文件统一命名为index.html）
- 新建style.css样式文件。本次采用外链样式表。
- 将样式引入到html页面中。
- 样式表写入清除内外边距的样式，来检测样式表是否引入成功

### 5.3css属性书写顺序(重点)

建议遵循以下顺序：

- 布局定位属性：display/position/float/clear/visibility/overflow（建议display第一个写，毕竟关系到模式）
- 自身属性：width/height/margin/padding/border/background
- 文本属性:color/font/text-decoration/text-algin/vertical-align/white-space/break-word
- 其他属性(css3):content/cursor/border-radius/box-shadow/text-shadow/background:linear-gradient...

### 5.4页面布局整体思路

为了提高制作的效率，布局时通常有以下的整体思路：

- 必须确定页面的版心(可视区)，我们测量可得知。
- 分析页面中的行模块，以及每个行模块中的列模块。页面布局第一准则。
- 一行中的列模块经常浮动布局，先确定每个列的大小，之后确定列的位置。页面布局第二准则。
- 制作html结构。我们还是遵循，现有结构，后有样式的原则。结构永远最重要。
- 所以，先理清楚布局结构，再写代码尤为重要。

### 5.5确定版心

这个页面的版心是1200像素，每个版心都要水平居中对齐，可以定义版心为共公共类：

```css
.w {
    width: 1200px;
    margin: 0 auto;
}
```

### 5.6头部制作

![1](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1.png)

- 1号是版心盒子header1200*42的盒子水平居中对齐，上下给一个margin值就可以了
- 版心盒子里面包含2号盒子logo
- 版心盒子里面包含3号盒子nav导航栏
- 版心盒子里面包含4号盒子search搜索栏
- 版心盒子里面包含5号盒子user个人信息
- 注意：要求里面的4个盒子必须都是浮动的

**导航栏注意点：**

**实际开发中，我们不会直接用链接a ，而是用li 包含链接(li+a)的做法。**

- li+a语义更清晰，一看这就是有条理的列表型内容。
- 如果直接用a，搜索引擎容易辨别为堆砌关键字嫌疑（故意堆砌关键字容易被搜索引擎有降权的风险），从而影响网站排名。

**注意：**

- 让导航栏一行显示，给li加浮动，因为li是块级元素，需要一行显示。

**search搜索框：**

一个search大盒子里面包含2个表单

![1571307430101](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571307430101.png)

### 5.7banner制作

![1571314623135](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571314623135.png)

- 1号盒子是通栏的大盒子banner，不给宽度，给高度，给一个蓝色背景
- 2号盒子是版心，要水平居中对齐
- 3号盒子在安心内，左对齐subnav侧导航栏
- 4号盒子在版心内，右对齐course课程

### 5.8精品推荐小模块

![3](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/3.png)

- 大盒子水平居中goods精品，注意此处有个盒子阴影
- 1号盒子是标题h3左侧浮动
- 2号盒子里面方链接左侧浮动，goods-item距离可以控制链接的左右外边距(注意行内元素只给左右内外边距)
- 3号盒子右浮动mod修改

### 5.9精品推荐大模块

![4](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/4.png)

- 1号盒子为最大的盒子，box版心水平居中对齐
- 2号盒子为上面部分，bx-hd 里面左侧标题h3左浮动，右侧链接a 有浮动
- 三号盒子为低下部分，bo-bd 里面是无序列表，右10个小li组成
- 小li外边距的问题，这里有个小技巧：给box-hd宽度1215就可以一行装开5个li

### 5.10底部模块

![5](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/5.png)

- 1号盒子是通栏大盒子，底部footer给高度，底色是白色
- 2号盒子版心水平剧中
- 3号盒子版权copyright左对齐
- 4号盒子连接组links右对齐
