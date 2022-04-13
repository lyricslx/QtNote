# QListWidget
QListWidget 用于方便表示列表控件中的数据
QListWidgetItem 表示列表中每一项的数据

## 增加子项
```c++
void QListWidget::addItem(QListWidgetItem *item);
```

## 设置子项的表现形式
```c++
//可对子项进行勾选
item->setFlags(item->flags() | Qt::ItemIsUserCheckable);
item->setCheckState(Qt::Unchecked);

//可对子项进行编辑
item->setFlags(item->flags() | Qt::ItemIsEditable);
```
