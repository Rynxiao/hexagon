# 关于正六边形(hexagon)的绘制

## 思路一：canvas绘制实现

1. 准备一个120x120的正方形canvas

2. 一张120x120的背景图片(正好使图片能够作为canvas背景)

3. 使用canvas绘制一个正六边形(需要计算), 算出之后即可以通过scale来放大缩小, 同时布置等大背景图片就好

4. 使用图片作为填充样式, 调用fill, 默认会从canvas (0,0) 的位置开始绘制

## 思路二：div+css实现

1. 准备三个div(记做div1,div2,div3), 长度为120,通过坐标可以算出宽度(注意三个div的层次关系, 由于div2,div3要相对div1定位,
    因此div1作为最上面一层容器, 同时定位为`position:relative`, div2、div3设置`position:absolute`, 相对于div1定位, 同时设置`z-index`在
    div1之下)

2. 设置div1背景居中显示

3. 设置div2、div3的`background : inherit`, 将div2与div3分别旋转正方向60度与反方向60度, 同时设置`overflow:hidden`属性,为伪类隐藏做准备

4. 分别定义div2与div3的伪类, 设置`width`和`height`为最大容器的宽度和高度(这样图片才能完好填充整个容器), 同时背景采用继承方式, 注意`z-index`设置高于其父容器, 之后即可以通过旋转到正的位置来补充正六边形的上边与下边残缺的图案
