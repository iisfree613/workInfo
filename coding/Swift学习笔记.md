# Swift 学习笔记

* 

* 创建OS X playground  引入 `Cocoa`

* 创建iOS playground 引入`UIKit`

* swift中字母采用Unicode编码

* 和声明有关的关键字：

  * class
  * deinit
  * enum
  * extension
  * func
  * import
  * init
  * internal
  * let
  * operator
  * private
  * protocol
  * public
  * static
  * struct
  * subscript
  * typealias
  * var

* 和语句有关的关键字：

  * break
  * case
  * continue
  * default
  * do
  * else
  * fallthrough
  * for
  * if
  * in 
  * return
  * switch
  * where
  * while

* 表达式和类型关键字：

  * as
  * dynamicType
  * false
  * is
  * nil
  * self
  * Self
  * super
  * true
  * __ COLUMN __
  * __ FILE __
  * __ FUNCTION __
  * __ LINE __

* 在特定上下文使用的关键字：

  * associativity
  * convenience
  * dynamic
  * didSet
  * final
  * get
  * infix
  * inout
  * lazy
  * left
  * mutating
  * none
  * nonmutating
  * optional
  * override
  * postfix
  * precedence
  * prefix
  * Protocol
  * required
  * right
  * set
  * Type
  * unowned
  * weak
  * willSet

* 语法上对空格有一定的要求

* 打印输出： `print("Hello World!")`

  * ``` swift
    for x in 0...10 {
        print("\(x)", terminator: " ")
    }
    ```

* 获取用户输入：`let theInput = readLine()`

* 内置数据类型：

  * Int:
  * UInt: 尽量不要使用UInt， 无符号类型 UInt
  * Float、Double: 浮点数
  * Bool : 布尔值
  * String : 字符串类型
  * Character : 字符, 不能创建空的字符类型变量或常量

* 类型别名：typealias

  * `typealias newName type`

* 变量输出，在字符串中可以用括号和反斜线来插入变量

  * ``` swift
    var name = "bobby"
    var age = 26
    print("My name is \(name), and my age is \(age)")
    ```

* 创建数组：`  var newArray = [SomeType](repeatin: InitivalValue, count: NumberOfElements)`

* 创建字典： ` var someDict = [KeyType : ValueType]()`



#  IOS 开发

playground是xcode文件的一种类型，可以和代码交互，能看到即时的输出结果。



# Objective-C 

Obj-C由C语言扩展而来。

OC源文件名的后缀是`.m`

`#import`引入头文件

* 能够保证头文件只被引用一次

`Foundation/Foundation.h`是Foundation框架的头文件，只要引入它，就可以使用Foundation框架的所有功能了。它是OC语言的基础框架，提供了OC专有的基本数据类型（如字符串、数组、时间日期等），提供了多线程，网络连接，文件操作，本地输出存储等常用功能。一般都需要引入。

`NSLog()`是OC中的格式化输出函数，不仅可以用来输出C语言中的数据，还可以输出OC中的数据。

`@`符号没有实际含义，只是用来作为OC字符串的特有标志。在OC中，字符串前面都要加@，如果不加就变成了C语言中的字符串，就要使用字符指针或字符数组来定义。

NSString 是OC中的字符串类型，需要使用格式控制符`%@`来输出。

OC中的类和对象：

* 通过`@interface`关键字来声明类
* 声明类的属性要`@property`关键字
* 使用`@end`关键字结束类的声明
* 通过`@implementation`关键字来实现类中的函数
* 使用`@end`关键字结束类中函数的实现







---

### 先声明，再实现，后使用

头文件-》声明

源文件-》实现

入口（main）文件-》调用



## 间接

* 变量名的间接
* 文件名的间接

间接是面向对象的核心



