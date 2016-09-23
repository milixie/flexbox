# Flexbox

## flex-direction
`flex-direction:row(left to right, top to bottom) || row-reverse(right to left, bottom to top)|| column || column-reverse`
`row`,`row-reverse` 从左往右排或者从右往左排，横向排序
`column`,`column-reverse` 从上往下或者从下往上排，纵向排序
```
.flex-container {
    display: -webkit-flex;
    display: flex;
    -webkit-flex-direction: row-reverse;
    flex-direction: row-reverse;
    width: 400px;
    height: 250px;
    background-color: lightgrey;
}
```

## justify-content
`justify-content`表示横向对齐方式
`justify-content: flex-start || flex-end || center || space-around || space-between`
```
.flex-container {
    display: -webkit-flex;
    display: flex;
    -webkit-justify-content: flex-end;
    justify-content: flex-end;
    width: 400px;
    height: 250px;
    background-color: lightgrey;
}
```
## align-items
`align-items`表示纵向对齐方式
`align-items: stretch || flex-start || flex-end || center || baseline`
```
.flex-container {
    display: -webkit-flex;
    display: flex;
    -webkit-align-items: stretch;
    align-items: stretch;
    width: 400px;
    height: 250px;
    background-color: lightgrey;
}
```

## flex-wrap
`flex-wrap`表示是否可换行换行方式
`flex-wrap: nowrap || wrap || wrap-reverse`
```
.flex-container {
    display: -webkit-flex;
    display: flex;
    -webkit-flex-wrap: nowrap;
    flex-wrap: nowrap;
    width: 300px;
    height: 250px;
    background-color: lightgrey;
}
```

## align-content
`align-content`用于`flex-wrap`属性行为，它类似于`align-items`，但是它对于换行的元素内容对齐方式起作用
```
.flex-container {
    display: -webkit-flex;
    display: flex;
    -webkit-flex-wrap: wrap;
    flex-wrap: wrap;
    -webkit-align-content: center;
    align-content: center;
    width: 300px;
    height: 300px;
    background-color: lightgrey;
}
```

## order
`order = <number>`定义flex项目的顺序流
```language
.flex-item {
    background-color: cornflowerblue;
    width: 100px;
    height: 100px;
    margin: 10px;
}

.first {
    -webkit-order: -1;
    order: -1;
}
```

## margin
设置 `margin: auto`可以设置出完美居中，上下左右都是居中的，设置其中一个子元素`margin-right: auto;`可以让中间空出一部分，其他都按规则靠边
```language
.flex-item {
    background-color: cornflowerblue;
    width: 75px;
    height: 75px;
    margin: 10px;
}

.flex-item:first-child {
    margin-right: auto;
}
```

## align-self
`align-self`值的作用和`align-items`的作用一样，不过`align-items`是设置一堆子元素的纵向对齐方式，而`align-self`可以设置每个子元素自己的纵向对齐方式
```language
.flex-item {
    background-color: cornflowerblue;
    width: 60px;
    min-height: 100px;
    margin: 10px;
}

.item1 {
    -webkit-align-self: flex-start;
    align-self: flex-start;
}
.item2 {
    -webkit-align-self: flex-end;
    align-self: flex-end;
}

.item3 {
    -webkit-align-self: center;
    align-self: center;
}

.item4 {
    -webkit-align-self: baseline;
    align-self: baseline;
}

.item5 {
    -webkit-align-self: stretch;
    align-self: stretch;
}
```

## flex
`flex`属性表示每个子flex元素所占的比重，例如下面这个例子中，2+1+1 = 4，其中item1占据两列，item2和item3各占据1列

`flex`是`flex-grow`,`flex-shrink`,`flex-basis`三个属性的缩写，第二个和第三个参数是可选值，默认值是`0 1 auto`

```language
.flex-item {
    background-color: cornflowerblue;
    margin: 10px;
}

.item1 {
    -webkit-flex: 2;
    flex: 2;
}

.item2 {
    -webkit-flex: 1;
    flex: 1;
}

.item3 {
    -webkit-flex: 1;
    flex: 1;
}
```

## flex-flow
`flex-flow: flex-direction flex-wrap | initial | inherit;` 也就是说`flex-flow`是`flew-direction`和`flew-wrap`的综合
```language
div {
    display: -webkit-flex; /* Safari */
    -webkit-flex-flow: row-reverse wrap; /* Safari 6.1+ */
    display: flex;
    flex-flow: row-reverse wrap;
}
```

## flex-basis
`flex-basis`定义flex项目在分配flex容器剩余空间之前的一个默认尺寸
```language
div:nth-of-type(2) {
    -webkit-flex-basis: 80px; /* Safari 6.1+ */
    flex-basis: 80px;
}
```

## flex-grow
`flex-grow`定义一个flex项目的扩大比例
`flex-grow: <number>`number是正数
```language
/* Safari 6.1+ */
div:nth-of-type(1) {-webkit-flex-grow: 1;}
div:nth-of-type(2) {-webkit-flex-grow: 3;}
div:nth-of-type(3) {-webkit-flex-grow: 1;}

/* Standard syntax */
div:nth-of-type(1) {flex-grow: 1;}
div:nth-of-type(2) {flex-grow: 3;}
div:nth-of-type(3) {flex-grow: 1;}
```

## flex-shrink
`flex-shrink`property specifies how the item will shrink relative to the rest of the flexible items inside the same container.
```language
/* Safari 6.1+ */
div:nth-of-type(2) {
    -webkit-flex-shrink: 3; 
} 

/* Standard syntax */
div:nth-of-type(2) {
    flex-shrink: 3;
}
```