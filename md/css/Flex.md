
# Flex布局

## 弹性盒子模型
- 采用Flex布局的元素，称为Flex容器（flex container），简称"容器"。
- 它的所有子元素自动成为容器成员，称为Flex项目（flex item），简称"项目"。

> 容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。
> 主轴的开始位置（与边框的交叉点）叫做main start，结束位置叫做main end；
> 交叉轴的开始位置叫做cross start，结束位置叫做cross end。
> 项目默认沿主轴排列。单个项目占据的主轴空间叫做main size，占据的交叉轴空间叫做cross size。

## 使用flex水平垂直居中
- 给父容器设置如下属性

```
  display: flex;
  flex-flow:row wrap;/*flex-direction和flex-wrap的复合写法*/
  justify-content: center;
  align-items:center;

```
-----------------------------------------------------------------------
## 容器的属性

```
flex-direction:属性决定主轴的方向（即项目的排列方向）
值：row | row-reverse | column | column-reverse;

flex-wrap:如果一条轴线排不下，如何换行
值：nowrap | wrap | wrap-reverse;

flex-flow：属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap
值：<flex-direction> || <flex-wrap>;

justify-content：属性定义了项目在主轴上的对齐方式。
值：flex-start | flex-end | center | space-between | space-around;

align-items：属性定义项目在交叉轴上如何对齐。
值： flex-start | flex-end | center | baseline | stretch;

align-content：属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。
值： flex-start | flex-end | center | space-between | space-around | stretch;
```
----------------------------------------------------------------------------------------
## 项目的属性

```
order:属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。

flex-grow:属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。

flex-shrink:属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。

flex-basis:属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。
浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。

flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。
该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。

align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。
值：auto | flex-start | flex-end | center | baseline | stretch;

```
--------------------------------------------------------------------------------------------------

### 实现三栏布局


####  给父容器添加属性

```
   .wrap{
            display: flex;
            flex-wrap: wrap;
        }
        .wrap >*{
            flex:1 100%;
            height: 100px;
        }
```

####  子容器要给高度
```
        @media all and (min-width: 600px) {
            .aside{
              flex:1  auto;
              height: 200px;
            }
        }
        @media all and (min-width: 800px) {
            .main{
              flex:2  auto;
            }
            .aside-1{
                order: -1;
            }
            .header{
                order: -2;
            }
        }
```

