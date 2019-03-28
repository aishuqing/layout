# 一．基本理论
Android六大基本布局分别是：线性布局LinearLayout、表格布局TableLayout、相对布局RelativeLayout、
层布局FrameLayout、绝对布局AbsoluteLayout、网格布局GridLayout。
## 二：线性布局
线性布局在开发中使用最多，具有垂直方向与水平方向的布局方式，通过设置属性“android:orientation”控制方向，属性值垂直（vertical）和水平(horizontal)，默认水平方向。
android:gravity：内部控件对齐方式，常用属性值有center、center_vertical、center_horizontal、top、bottom、left、right等。
这个属性在布局组件RelativeLayout、TableLayout中也有使用，FrameLayout、AbsoluteLayout则没有这个属性。
center：居中显示，这里并不是表示显示在LinearLayout的中心，当LinearLayout线性方向为垂直方向时，center表示水平居中，但是并不能垂直居中，此时等同于center_horizontal的作用；同样当线性方向为水平方向时，center表示垂直居中，等同于center_vertical。

top、bottom、left、right顾名思义为内部控件居顶、低、左、右布局。
这里要与android:layout_gravity区分开，layout_gravity是用来设置自身相对于父元素的布局。

android:layout_weight：权重，用来分配当前控件在剩余空间的大小。
使用权重一般要把分配该权重方向的长度设置为零，比如在水平方向分配权重，就把width设置为零。

截图：![](https://github.com/aishuqing/layout/blob/master/屏幕快照%202019-03-18%20下午10.21.30.png)
### 三：约束布局
 列举几点来表明ConstraintLayout是如何能解决这个矛盾，它的强大之处。 
Constraint Layout可以在不嵌套view group的情况下实现非常庞大、复杂的布局。实现扁平化。 
Constraint Layout同时具有Relative Layout和Linear Layout的优点、特性。功能强大。 
使用Constraint Layout来布局时性能要比其他布局方式高。性能比较具体参考官方文档 ：ConstraintLayout性能优势解析-官文 
截图: ![](https://github.com/aishuqing/layout/blob/master/屏幕快照%202019-03-18%20下午10.20.46.png)
#### 四：表格布局
表格布局，适用于多行多列的布局格式，每个TableLayout是由多个TableRow组成，一个TableRow就表示TableLayout中的每一行，这一行可以由多个子元素组成。实际上TableLayout和TableRow都是LineLayout线性布局的子类。但是TableRow的参数android:orientation属性值固定为horizontal，且android:layout_width=MATCH_PARENT，android:layout_height=WRAP_CONTENT。所以TableRow实际是一个横向的线性布局，且所以子元素宽度和高度一致。
注意：在TableLayout中，单元格可以为空，但是不能跨列，意思是只能不能有相邻的单元格为空。
TableLayout常用属性：
android:shrinkColumns：设置可收缩的列，内容过多就收缩显示到第二行
android:stretchColumns：设置可伸展的列，将空白区域填充满整个列
android:collapseColumns：设置要隐藏的列
列的索引从0开始，shrinkColumns和stretchColumns可以同时设置。
子控件常用属性：
android:layout_column：第几列
android:layout_span：占据列数

截图： ![](https://github.com/aishuqing/layout/blob/master/屏幕快照%202019-03-18%20下午10.21.05.png)

