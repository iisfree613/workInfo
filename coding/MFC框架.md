# 学习MFC前技术基础

## WIN32程序概念：

* message based: 文档基础
* event driven: 事件驱动
* multitasking: 多任务
* multithreading:多线程
* console programing:

## C++基础：

* 类和对象
* this指针和继承
* 静态成员
* 虚函数与多态
* 模板（template）类
* 异常处理（exception handling）

## MFC重点：

* CWinApp类：
* CFrameWnd类：
* CPaintDC类
* 消息映射机制

# MFC



## 基础：

* UINT类型是由unsigned int类型派生出来的

## afx_msg

是应用框架产生的消息映射函数。

afx_msg为消息标志，向系统声明：有消息映射到函数实现体；而在map宏定义中，就有具体消息和此函数的映射定义。

在类头中增加消息声明；在类实现文件中增加消息定义和执行函数。

![messages](../img/wm_messages.png)

## 文档/视图体系结构

依靠文档保存应用程序的数据，依靠视图对象控制视图中显示的数据。



## 视图：

* 用户视角，视图就是一个普通的窗口
* 程序员的视角，视图是一个个C++ 对象，派生自MFC中CView类
* 

## 消息映射

![](../img/message_map.png)

## 资源编辑器（.rc）



book：

基于visual C++ MFC编程



## MFC基础：

### 画图：CPaintDC类响应WM_PAINT消息，允许你在窗口客户区画图。

### 鼠标和键盘：

#### 客户区鼠标消息

![mouse_message](../img/mouse_message.png)

``` C++
afx_msg void OnMsgName (UINT nFlags, CPoint point)
    // point 指出光标的位置； nFlags指出消息产生时鼠标键以及shift键和Ctrl键的状态
```

<img src="../img/nflags.png" alt="nFlags" style="zoom:50%;" />

##### 从键盘获取输入

* 输入焦点的概念：
* 获取击键码：

#### 菜单

* 创建菜单：在资源描述文件（.rc）中添加

* 加载并显示菜单：

  * ``` c++
    CMainWindow::CMainWindow()
    {
    	Create(NULL, _T("The Hello Application"), WS_OVERLAPPEDWINDOW | WS_VSCROLL | WS_HSCROLL | WS_SYSMENU | WS_CAPTION,
    		CRect(400, 100, 1200, 1000), NULL, MAKEINTRESOURCE(IDR_MAINFRAME));
    }
    ```

  * MAKEINTRESOURCE(IDR_MAINFRAME)

## MFC集合类

* 数组
* 列表
* 映射表：设计映射表的目的是给定一个关键字，可以很快在表中找到响应的项目，通常只查找一次。
* 类型指针类



## 文件的I/O及序列化



## 控件

* 传统控件：6个预定义的WNDCLASS
* ![](../img/winclass.png)
* 