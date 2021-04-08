# django model

###  ForeignKey ( othermodel, on_delete, **options )

第一个参数：关联的表格（主表）

第二个参数：on_delete的参数

* models.CASCADE: 当主表的字段被删除时，和他有关的子表字段也会被删除。
* models.PROTECT：返回错误提示，阻止删除。
* models.SET_NULL：设置null来代替
* models.SET_DEFAULT：用默认值替换
* models.SET：设定自定义值

可选参数：

**to_field**: 设置关联到主表的字段

**related_name**: 自定义一个名称，用于反向查询

> 当一张子表里，多个foreignkey指向同一个主表，related_name必须设置。

### 区别于Django中这两个字段的区别：

* models.DateTimeField： 记录日期和时间，年月日+时间
* models.DateField：只记录日期，年月日

> 这两种不同类型的标签在HTML模板中对应的格式化输出字符是不同的

``` html
models.DateTimeField  ==> {{ datetime|date:"Y/m/d H:i:s" }}
models.DateField ==> {{ date|date:"Y/m/d" }} 
// 否则会爆出如下的错误
Django Version:	3.1.7
Exception Type:	TypeError
Exception Value:	
The format for date objects may not contain time-related format specifiers (found 'H').
```



## manage.py help

``` python
Available subcommands:

[auth]
    changepassword # 更改管理员账号密码
    createsuperuser # 创建超级管理员账号

[captcha]
    captcha_clean
    captcha_create_pool

[contenttypes]
    remove_stale_contenttypes

[django]
    check
    compilemessages
    createcachetable
    dbshell
    diffsettings
    dumpdata
    flush
    inspectdb
    loaddata
    makemessages
    makemigrations  # 
    migrate     # 
    sendtestemail
    shell
    showmigrations
    sqlflush
    sqlmigrate
    sqlsequencereset
    squashmigrations
    startapp  # 为项目添加APP应用
    startproject  # 创建新项目
    test
    testserver

[sessions]
    clearsessions

[staticfiles]
    collectstatic  # 克隆静态资源到项目的静态目录
    findstatic
    runserver # 启动服务，默认localhost:8000，可指定端口
```

