# qml

QML是一个描述性语言，描述每个部件的外观和行为，
这些部件最后组合成一个完整的用户界面

部件与部件之间具有层级关系，子部件会继承父部件的相关属性

## qml语法
qml的语法很简单
```c++
// RectangleExample.qml

import QtQuick 2.5

Rectangle {
  // name this element root
  id: root
  
  // properties: <name> : <value>
  widht: 120; height: 240
  
  // color property
  color: "#4A4A4A"
  
  // Declare a nested element (child of root)
  Image {
    id: triangle
    
    x: (parent.width - width)/2; y: 40
    source: 'assets/triangle_rected.png'
  }
  
  // Another child of root
  Text {
    // un-named element
    
    // reference element by id
    y: triangle.y + triangle.height + 20
    width: root.width
    
    color: 'white'
    horizontalAlignment: Text.AlignHCenter
    text: 'Triangle'
  }
}
```

## qml可以非常方便的和c++交互,写法类似于css

每一个窗口都有一个实例化的C++的类

如Window -> QQuickWindow

```c++
//类似于c++的include
import QtQuick 2.12     //导入模块
```
## 不可见元素

```c++
Column {
}
```

控制元素
```c++
Column {  //不可视元素
  Button {  //可见元素
    id: btn
    text: 'btn'
  }
  Label { //可见元素
    text: btn.text
    color: 'red'
    font.pointSize: 20
  }
  
  Rectangle { //可见元素
    width:100
    height:100
    color: 'blue'
  }
}
```

## 信号
```c++
Window {
  width:640
  height:480
  visible: true
  title: "Hello, World"
  
  Button {
    text: 'click'
    
    //基本上属性都有一个属性变化信号
    onTextChanged: {
      console.log('new text', text)
    }
    
    onClicked: {
      console.log('btn click')
      text = 'hello'
    }
  }
}
```

## 自定义方法
```c++
Window {
  width:640
  height:480
  visible: true
  title: "Hello, World"
  
  Button {
    onClicked: {
      showAddResult(add(10, 20)
    }
  }
  
  function add(num1, num2) {
    return num1 + num2
  }
  
  function showAddResult(result) {
    consolo.log(result)
  }
}
```

## 导入js脚本

```c++
/*
这是一个js文件，他可以执行js代码，他支持的标准是es5
*/

function OperatorNumber(number) {
  this.number = number
  
  this.add = function(num) {
    return number + num;
  }
  
  this.sub = function(num) {
    return number - num;
  }
}

```

```c++
import 'file.js' as util
Window {
  width: 680
  height: 480
  title: 'hello,world'
  
  Button {
    text: 'clicked'
    
    onClicked: {
      let oper = new util.OperatorNumber(888)
      console.log('add', oper.add(70))
      console.log('sub', oper.sub(70))
    }
  }
}
```

## 布局定位
```c++
Window {
  width: 680
  height: 480
  title: 'hello world'
  
  
}
```
