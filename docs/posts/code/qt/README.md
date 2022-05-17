## 1. Qt 是什么？

### 1.1 为什么叫Qt?

不是英文缩写。
因为在某字体中'Q'比较漂亮，'t'是工具的意思，可以理解为 **漂亮的工具**。

### 1.2 Qt 历史

1991 年奇趣公司。
现在 **The qt Company**.

### 1.3 Qt 版本

有商业版和开源版。2020年6已经出了。

## 2. Qt安装

manjaro 安装

```bash
yay -S qtcreator
# 调试器
yay -S gdb
# manjaro 自带qmake，仍要安装 GNU make
yay -S make
```



## 3. 开发步骤及实例

### 3.1 基类的选择

- QApplicaiton 是完整的应用，有菜单栏等。
- QDialog 只是一个窗体。
- QWidget 是所有Qt GUI窗口的基类（按钮，窗体等），它接收鼠标，键盘和其他窗体事件，并在界面上绘制自己。

### 3.2 伙伴编辑模式

仅“QLabel" 控件有，设置buddy之后，在'text'属性中用"&+字母"
设置，其位置没有固定要求，不区分大小写。之后快捷键"Alt+字母"聚焦到绑定的buddy上。

### 3.3 信号和槽机制

> 任意两个Qt对象之间的通信机制。

#### 1) 用法

```cpp
connect(object1, SIGNAL(), object2, SLOT())
```


可以

- 一个信号 -》 另一个信号
- 多个信号 -》一个槽
- 一个信号 -》多个槽

#### 2) SIGNAL() & SLOT()

Qt定义的两个宏，返回其参数的C语言风格字符串（const char*)。下面两句一样：

```cpp
connect(button, SIGNAL(clicked()), this, SLOT(showArea()))
connect(button, "clicked()", this, "showArea()")
```

### 3.4 元对象系统

>  Qt5 元对象系统提供了对象间的通信机制（信号和槽）等，是标准C++的一个扩展。

⭐️**不支持C++模版**

基于的三个事实：

1. 基类QObject: 任何需要使用元对象系统的类都要继承自QObject
2. Q_Object宏：Q_Object 宏必须出现在类的 *私有声明区，用于启动元对象特性。*
3. 元对象编译器（moc）：为QObject子类实现元对象特性提供必要的代码实现。

