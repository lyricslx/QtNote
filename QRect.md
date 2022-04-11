```c++
// constructure two identical rectangles
QRect r1(100, 200, 11, 16);
QRect r2(QPoint(100, 200), QSize(11, 16));

//by the history reason, buttom() and right() deviate the 
//true buttom-right corner of the rect.
/*
 *  top() + height() - 1
 */
int QRect::bottom() const;

/*
 *
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
