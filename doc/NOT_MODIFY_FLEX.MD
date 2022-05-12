## flex
> 设为 Flex 布局以后，子元素的float、clear和vertical-align属性将失效。
> [参考](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
> 容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）
> 主轴的开始位置（与边框的交叉点）叫做main start，结束位置叫做main end；
> 交叉轴的开始位置叫做cross start，结束位置叫做cross end。
> 项目默认沿主轴排列。单个项目占据的主轴空间叫做main size，占据的交叉轴空间叫做cross size

![Image text](flex/flex.png)

### 容器的属性
1. flex-direction： 属性决定主轴的方向row | row-reverse | column | column-reverse;
-  row：（默认值）主轴为水平方向，起点在左端。
-  row-reverse：主轴为水平方向，起点在右端。
-  column：主轴为垂直方向，起点在上沿。
-  column-reverse：主轴为垂直方向，起点在下沿。

2. flex-wrap 属性定义，如果一条轴线排不下，如何换行
-  row（默认值）：主轴为水平方向，起点在左端。
-  row-reverse：主轴为水平方向，起点在右端。
-  column：主轴为垂直方向，起点在上沿。
-  column-reverse：主轴为垂直方向，起点在下沿。

3. flex-flow 属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。
- flex-flow：<flex-direction> || <flex-wrap>;

4. justify-content 属性定义了项目在主轴上的对齐方式。（假设主轴为从左到右，即）
- flex-start（默认值）：左对齐
- flex-end：右对齐
- center： 居中
- space-between：两端对齐，项目之间的间隔都相等。
- space-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。

5. align-items 属性定义项目在交叉轴上如何对齐。
- flex-start：交叉轴的起点对齐。
- flex-end：交叉轴的终点对齐。
- center：交叉轴的中点对齐。
- baseline: 项目的第一行文字的基线对齐。
- stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。

6. align-content 属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。
- flex-start：与交叉轴的起点对齐。
- flex-end：与交叉轴的终点对齐。
- center：与交叉轴的中点对齐。
- space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
- space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
- stretch（默认值）：轴线占满整个交叉轴。

### 项目的属性
- order 属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。
- flex-grow 属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
- flex-shrink 属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
- flex-basis 属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。
- flex 属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。 none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
- align-self 属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。
             默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。
- align-self: auto | flex-start | flex-end | center | baseline | stretch;该属性可能取6个值，除了auto，其他都与align-items属性完全一致。
