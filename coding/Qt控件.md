### QLabel

对齐方式：

* 获取对齐方式：Qt::Alignment alignment() const;
* 设置对齐方式：void setAlignment(Qt::Alignment align);

对齐的取值：

1.  Qt::AlignLeft: 左对齐
2.  Qt::AlignRight: 右对齐
3.  Qt::AlignHCenter: 水平居中
4.  Qt::AlignJustify: 水平方向，两端对齐
5.  Qt::AlignTop: 居上对齐
6.  Qt::AlignButton: 居下对齐
7.  Qt::AlignVCenter: 垂直方向，居中
8.  Qt::AlignCenter: 水平，垂直方向居中



### 按键捕获：

###### Qt中的回车键对应两个键值：Qt::Key_Enter、Qt::Key_Return。



### QListWidget
```
// 构造函数
QListWidget( Qwidget *parent)
// 添加条目
void QListWidget::addItem(QListWidgetItem *item)
void QListWidget::addItem(const QString & label)
void QListWidget::addItem(const QStringList & labels)
void QListWidget::addItem(int row, QListWidgetItem *item) // 插入条目到第row行
void QListWidget::addItem(int row, const QString & label)
void QListWidget::addItem(int row, const QStringList & labels)

// 获取控件里面条目计数
int QListWidget::count() const

// 删除条目
QListWidgetItem *QListWidget::takeItem(int row) // 根据行号移除一个条目，并返回该条目的指针，如果不合法则返回NULL指针

// 清空整个列表控件
void QListWidget::clear()

// 条目访问函数
QListWidgetItem *QListWdiget::item(int row) const // 根据行号获取条目对象的指针
int QListWidget::row(const QListWidgetItem * item) const // 已知列表控件内含条目对象指针，反查当前行号
```

> QListWidgetItem 是一个纯数据类，不是控件，没有基类，也没有信号和槽函数。