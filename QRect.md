# QRect
这个类可以用来访问到矩形的多个特征坐标，以及对这些坐标的操作函数
甚至还可以执行一些坐标的平移转换操作

## 构造函数
没有指定初始值的Rect的各个点的坐标为:
rect left: 0, rect right: -1;
rect top: 0, rect bottom: -1;
```c++
// constructure two identical rectangles
// 注意: buttom() 和 right() 函数返回的值和正常值相比是有-1的偏差的
QRect r1(100, 200, 11, 16);
QRect r2(QPoint(100, 200), QSize(11, 16));

// 这个构造函数尽量少用，避免引起歧义（bottom 和 right）
QRect r3(QPoint(100, 200), QPoint(110, 215);
```

## 坐标
```c++
//by the history reason, buttom() and right() deviate the 
//true buttom-right corner of the rect.
/*
 *  top() + height() - 1
 */
int QRect::bottom() const;

/*
 * left() + width() - 1
 */
int QRect::right() const;

/*
 * Returns the y-coordinate of the rectangle's top edge.
 * Equivalent to top()
 */
int QRect::y() const;
int QRect::top() const;

/*
 * Returns the x-coordinate of the rectangle's left edge.
 * Equivalent to left()
 */
int QRect::x() const;
int Qrect::left() const;
```

## 转换
```c++
void setLeft(int x);

void moveLeft(int x);
```

## 限制
QRect 的坐标都是用int类型来存储的，如果存储值超过了int的表示范围，
其行为是未定义的
