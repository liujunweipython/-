# css定位

## 目标：

1. 能够说出为什么需要定位
1. 能够说出定位的4种分类
1. 能够说出4种定位各自特点
1. 能够说出为什么常用子绝父相布局
1. 能够写出淘宝轮播图布局
1. 能够说出显示隐藏的2种方式以及区别

## 目录：

1. 定位
2. 综合案例
3. 网页布局总结
4. 元素的显示与隐藏

## 一、定位

### 1.1为什么需要定位

提问：以下情况使用标准流或者浮动能实现吗？

- 某个元素可以自由的在一个盒子内移动位置，并且压住其他盒子。

  ![01_定位示例1](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/01_%E5%AE%9A%E4%BD%8D%E7%A4%BA%E4%BE%8B1.gif)

- 当滚动窗口的时候，盒子是固定在屏幕的某个位子的。

  ![ding](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/ding.png)

以上效果，标准流或浮动都无法快速实现，此时**需要定位来实现**

所以：

- 浮动可以让多个块级盒子一行没有缝隙排列显示，经常用于横向排列盒子。
- 定位则是可以让盒子自由额在某个盒子内移动位置或者固定屏幕中某个位置，并且可以压住其他盒子。

### 1.2定位组成

定位：将盒子定在某一个位置，所以定位也是在摆放盒子，按照定位的方式移动盒子。

**定位=定位模式+边偏移**

**定位模式**用于指定一个元素在文档中的定位方式。**边偏移**则决定了该元素的最终位置

#### 1.21定位模式

定位模式决定元素的定位方式，他通过css的position属性来设置，其值可以分为4个：

| 值       | 语义     |
| -------- | -------- |
| static   | 静态定位 |
| relative | 相对定位 |
| absolute | 绝对定位 |
| fixed    | 固定定位 |

#### 1.22边偏移

边偏移就是定位的盒子移动到最终位置。右top、bottom、left、right 4个属性。

| 边偏移属性 | 示例        | 描述                                         |
| ---------- | ----------- | -------------------------------------------- |
| top        | top:80px    | 顶端偏移量，定义元素相对于父元素上边线的距离 |
| bottom     | bottom:80px | 底部偏移量，定义元素相对于父元素下边线的距离 |
| left       | left:80px   | 左侧偏移量，定义元素相对于父元素左边线的距离 |
| right      | right:80px  | 右侧偏移量，定义元素相对于父元素右边线的距离 |

### 1.3静态定位static(了解)

静态定位是元素的默认定位方式，无定位的意思

语法：

```css
选择器 {position:static;}
```

- 静态定位按照标准流特性摆放位置，它没有边偏移
- 静态定位在布局时很少用到

### 1.4相对定位relative(重要)

相对定位是元素在移动位置的时候，是相对它自己的位置来说的(自恋型)。

语法：

```css
选择器 {position:relative;}
```

相对定位特点：（务必记住）

- 它是相对原来的位置来移动的（移动位置的时候参照点是自己原来的位置）
- 原来在标准流的位置继续占有，后面的盒子仍然以标准流的方式对待他（不脱标，继续保留原来位置）

因此，相对定位并没有脱标。它最典型的应用是给绝对定位当爹的。。

### 1.5绝对定位absolute(重要)

绝对定位是元素在移动位置的时候，是相对它祖先元素来说的(拼爹型)。

语法：

```css
选择器 {position:absolute;}
```

绝对定位的特点：(务必记住)

- 如果没有祖先元素或者祖先元素没有定位，则以浏览器为准定位。
- 如果祖先元素有定位(相对、绝对、固定定位)，则以最近一级的有定位祖先元素为参考点移动位置
- 绝对定位不在占有原先的位置

### 1.6思考

绝对定位和相对定位到底有什么使用场景呢?

为什么说相对定位给绝对定位当爹的呢？

### 1.7子绝父相的由来

弄清楚这个口诀，就明白了绝对定位和相对定位的使用场景。

这个“子绝父相”太重要了，是我们学习定位的口诀，是定位中最常用的一种方式，这句话的意思是：子绝是绝对定位的话，父级要用相对定位。

- 子级绝对定位，不会占有位置，可以放到父盒子里面的任何一个地方，不会影响其他的兄弟盒子。
- 父盒子需要加定位限制子盒子在父盒子内显示
- 父盒子布局时，需要占有位置，因此父亲只能是相对定位

这就是子绝父相的由来，所以**相对定位经常用来作为绝对定位的父级**。

总结：因为父级需要占有位置，因此是相对定位，子盒子不需要占有位置，则是绝对定位

### 1.8定位案例：学成咋先-hot new模块添加

![1571385771180](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/1571385771180.png)

### 1.9固定定位fixed(重要)

固定定位是元素固定于浏览器可视区的位置。主要使用场景：可以在浏览器页面滚动时元素的位置不会改变。

语法：

```css
选择器 {position:fixed;}
```

固定定位的特点：(务必记住)

- 以浏览器的可视窗口为参照点移动元素。
- 跟父元素没有任何关系
- 不随滚动条滚动
- 固定定位不在占有原来的位置
- 固定定位也是脱离标准流的，其实固定定位也可以看作是一种特殊的绝对定位。

#### 1.91固定定位小技巧

**固定在版心右侧位置**

小算法：

- 让固定定位的盒子left:50%; 走到浏览器可视区(也可以看作版心)的一半位置。
- 让固定定位的盒子margin-left:版心宽度的一半距离。多走版心宽度的一半位置

**就可以让固定定位的盒子贴着版心右侧对齐了。**

### 2.0粘性定位sticky(了解)

粘性定位可以被认为是相对定位和固定定位的混合。sticky粘性的

语法：

```css
选择器 {position:sticky; top: 10px;}
```

粘性定位的特点：

- 以浏览器的可视窗口为参照点移动元素(固定定位的特点)
- 粘性定位占有原先的位置(相对定位的 特点)
- 必须添加top、left、right、bottom其中一个才生效

跟页面滚动搭配使用。兼容性较差，IE不支持

### 2.1定位总结

| 定位模式         | 是否脱标             | 移动位置           | 是否常用   |
| ---------------- | -------------------- | ------------------ | ---------- |
| static静态定位   | 否                   | 不能使用边偏移     | 很少       |
| relative相对定位 | 否（占有原来位置）   | 相对于自身位置移动 | 常用       |
| absolute绝对定位 | 是（不占有原来位置） | 带有定位的父级     | 常用       |
| fixed固定定位    | 是（不占有原来位置） | 浏览器可视区       | 常用       |
| sticky粘性定位   | 否（占有原来位置）   | 浏览器可视区       | 当前阶段少 |

一定记住 相对定位、绝对定位、固定定位  两个大的特点：①是否占有位置（脱标）②以谁为基准点进行位置移动

学习定位重点学会子绝父相

### 2.1定位叠放次序 z-index

在使用定位布局时，可能会出现盒子重叠的情况。此时，可以使用z-index来控制盒子的前后次序（z轴）

语法：

```css
选择器 {z-index: 1;}		
```

- 数值可以是正整数、负整数或者0，默认是auto，数值越大，盒子越靠上
- 如果属性值相同，则按照书写顺序，后来者居上。
- 数字后面不能加单位
- 只有定位的盒子才有z-index属性

### 2.2定位的拓展

#### 2.21绝对定位的盒子居中

加了绝对定位额盒子不能通过margin:0 auto水平居中，但是可以通过以下计算方法实现水平和垂直居中：

① left:50%; 让盒子的左侧移动到父级元素的水平中心位置。

② margin-left: -100px; 让盒子向左移动自身宽度的一半

#### 2.22定位特殊特性

绝对定位和固定定位也和浮动类似

①行内元素添加绝对或者固定定位，可以直接设置高度和宽度

②块级元素添加绝对或者固定定位，如果不给宽度或者高度，默认大小是内容本身的大小。

#### 2.23脱标的盒子不会触发外边距塌陷

浮动元素、绝对定位、固定定位元素 都不会触发外边距合并的问题

#### 2.24绝对定位(固定定位)会完全压住盒子

浮动元素不同，只会压住它下面标准流的盒子，但是不会压住下面标准盒子里的文字或图片

但是绝对定位（固定定位）会压住下面标准流的所有内容。

浮动之所以不会压住文字，因为浮动产生的目的最初是为了做文字环绕效果的。文字会围绕浮动元素

![文字环绕图片](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/%E6%96%87%E5%AD%97%E7%8E%AF%E7%BB%95%E5%9B%BE%E7%89%87.png)

## 二、综合案例

### 案例1-淘宝焦点图布局

![淘宝焦点图](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/%E6%B7%98%E5%AE%9D%E7%84%A6%E7%82%B9%E5%9B%BE.png)

- 大盒子我们类名为：tb-promo  淘宝广告
- 里面先放一张图片
- 左右两个按钮用链接就好了。左箭头prev  右箭头 next
- 底侧小圆点ul继续做。类名promo-nav

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>淘宝轮播</title>
    <style>
        * {
            margin: 0;
            padding: 0;

        }

        li {
            list-style: none;
        }

        .tb-promo {
            position: relative;
            width: 520px;
            height: 280px;
            background-color: pink;
            margin: 200px auto;
        }

        .tb-promo img {
            width: 520px;
            height: 280px;

        }

        .prev,
        .next {
            position: absolute;
            top: 50%;
            margin-top: -15px;
            width: 20px;
            height: 30px;
            background-color: rgba(0, 0, 0, 0.3);
            text-align: center;
            line-height: 30px;
            color: #ffffff;
            text-decoration: none;

        }

        .prev {
            left: 0;
            border-top-right-radius: 15px;
            border-bottom-right-radius: 15px;

        }

        .next {
            right: 0;
            border-top-left-radius: 15px;
            border-bottom-left-radius: 15px;

        }
        .promo-nav{
            position: absolute;
            left: 50%;
            margin-left: -35px;
            bottom: 15px;
            width: 70px;
            height: 13px;
            background-color: rgba(255,255,255,0.2);
            border-radius: 7px ;
        }
        .promo-nav li {
            float: left;
            width: 8px;
            height: 8px;
            border-radius: 4px;
            background-color: #fff;
            border-radius: 50%;
            margin: 3px;
        }
        .promo-nav .selected{
            background-color: #ff5500;
        }
    </style>
</head>

<body>
    <div class="tb-promo">
        <img src="images/tb.jpg" alt="">
        <!-- 左侧按钮 -->
        <a href="#" class="prev">&lt;</a>
        <a href="#" class="next">&gt;</a>
        <!-- 小圆点 -->
        <ul class="promo-nav">
            <li class="selected"></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
        </ul>

    </div>
</body>

</html>
```

## 三、网页布局总结

通过盒子模型，清楚知道大部分html标签是一个盒子。

通过css浮动、定位可以让每个盒子排列成为网页。

一个完整的网页，是标准流、浮动、定位一起完成布局的，每个都有自己的专门用法。

1. 标准流：可以让盒子上下排列或者左右排列，垂直的块级盒子显示就用标准流布局
2. 浮动：可以让多个块级元素一行显示或者左右对齐盒子，多个块级盒子水平显示就用浮动布局。
3. 定位：定位最大的特点就是有层叠的概念，就是可以让多个盒子前后叠压来显示。如果元素自由在某个盒子内移动就用定位布局。

## 四、元素的显示与隐藏

### 4.1display属性

display属性用于设置一个元素应如何显示。

- display:none;隐藏对象
- display:block；除了转换为块级元素之外，同时还有显示元素的意思

display隐藏元素后，不在占有原来的位置。

后面应用搭配js做网页特效。

### 4.2visibility可见性

visibility属性用于指定一个元素可见还是隐藏。

- visibility:visible；元素可视
- visibility:hidden；元素隐藏

visibility隐藏元素后，继续占有原来的位置。

如果隐藏元素想要原来位置，就用visibility:hidden

如果隐藏元素不想要原来位置，就用display:none （用处更多，重点）

### 4.3overflow溢出

overflow属性指定了如果内容溢出一个元素的框（超过其指定高度及宽度）时，会发生什么。

| 属性值  | 描述                                       |
| ------- | ------------------------------------------ |
| visible | 不剪切内容也不添加滚动条                   |
| hidden  | 不显示超过对象尺寸的内容，超出的部分隐藏掉 |
| scroll  | 不管是否超出内容，都显示滚动条             |
| auto    | 超出自动显示滚动条，不超出不显示滚动条     |

一般情况下，我们都不想让溢出的内容显示出来，因为溢出的部分会影响布局。

但是如果有定位的盒子，请慎用overflow：hidden 因为他会隐藏多余的部分。

### 4.4案例-土豆网鼠标经过显示遮罩

![土豆网案例](https://raw.githubusercontent.com/liujunweipython/tuchuang/main/%E5%9C%9F%E8%B1%86%E7%BD%91%E6%A1%88%E4%BE%8B.png)

1. 练习元素的显示与隐藏
2. 练习元素的定位
3. 核心原理：原先半透明的黑色遮罩看不见，鼠标经过 大盒子，就显示出来。
4. 遮罩的盒子不占有位置，就需要用绝对定位和display配合使用。

```css
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .tudou {
            position: relative;
            width: 444px;
            height: 320px;
            /* background-color: pink; */
            margin: 0 auto;

        }
        .tudou img{
            
            width: 100%;
            height: 100%;

        }
        .msk{
            position: absolute;
            display: none;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0,0.5) url(images/arr.png) no-repeat center;

        }
        .tudou:hover .msk{
            display: block;
        }
    </style>
</head>

<body>
    <div class="tudou">
        <div class="msk"></div>
        <img src="images/tudou.jpg" alt="" >
    </div>
</body>

</html>
```

