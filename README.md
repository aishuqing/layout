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
 
代码：
<LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">
        <Button
            android:layout_width="wrap_content"
            android:text="One,One"
            android:layout_height="wrap_content"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            android:textColor="#ffffff"
            tools:text="1,1" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="One,two"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            android:textColor="#ffffff"
            tools:text="1,2" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="One,three"
            android:textColor="#ffffff"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            tools:text="1,3" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="One,four"
            android:textColor="#ffffff"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            tools:text="1,4" />
    </LinearLayout>
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="two,One"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            android:textColor="#ffffff"
            tools:text="1,1" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="two,two"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            android:textColor="#ffffff"
            tools:text="1,2" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="two,three"
            android:textColor="#ffffff"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            tools:text="1,3" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="two,four"
            android:textColor="#ffffff"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            tools:text="1,4" />
    </LinearLayout>
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="three,one"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            android:textColor="#ffffff"
            tools:text="1,1" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="three,two"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            android:textColor="#ffffff"
            tools:text="1,2" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="three,three"
            android:textColor="#ffffff"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            tools:text="1,3" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="three,four"
            android:textColor="#ffffff"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            tools:text="1,4" />
    </LinearLayout>
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="four,one"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            android:textColor="#ffffff"
            tools:text="1,1" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="four,two"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            android:textColor="#ffffff"
            tools:text="1,2" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="four,three"
            android:textColor="#ffffff"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            tools:text="1,3" />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="four,four"
            android:textColor="#ffffff"
            android:layout_marginTop="3dip"
            android:layout_marginLeft="3dip"
            tools:text="1,4" />
    </LinearLayout>
 
截图：![](https://github.com/aishuqing/layout/blob/master/屏幕快照%202019-03-18%20下午10.21.30.png)
### 三：约束布局
 
代码

截图: ![](https://github.com/aishuqing/layout/blob/master/屏幕快照%202019-03-18%20下午10.20.46.png)
#### 四：表格布局

代码

截图： ![](https://github.com/aishuqing/layout/blob/master/屏幕快照%202019-03-18%20下午10.21.05.png)

