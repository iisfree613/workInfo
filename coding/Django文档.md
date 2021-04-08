# Django

#### 显示Django版本

``` py
python -m django version
```

```
$ python manage.py runserver 0:8000
```

**0** 是 **0.0.0.0** 的简写



## 数据库配置

[`ENGINE`](https://docs.djangoproject.com/zh-hans/3.1/ref/settings/#std:setting-DATABASE-ENGINE) -- 可选值有

`django.db.backends.sqlite3`，`django.db.backends.postgresql`，

`django.db.backends.mysql`，或 

`django.db.backends.oracle`

### django 自带应用

- [`django.contrib.admin`](https://docs.djangoproject.com/zh-hans/3.1/ref/contrib/admin/#module-django.contrib.admin) -- 管理员站点， 你很快就会使用它。
- [`django.contrib.auth`](https://docs.djangoproject.com/zh-hans/3.1/topics/auth/#module-django.contrib.auth) -- 认证授权系统。
- [`django.contrib.contenttypes`](https://docs.djangoproject.com/zh-hans/3.1/ref/contrib/contenttypes/#module-django.contrib.contenttypes) -- 内容类型框架。
- [`django.contrib.sessions`](https://docs.djangoproject.com/zh-hans/3.1/topics/http/sessions/#module-django.contrib.sessions) -- 会话框架。
- [`django.contrib.messages`](https://docs.djangoproject.com/zh-hans/3.1/ref/contrib/messages/#module-django.contrib.messages) -- 消息框架。
- [`django.contrib.staticfiles`](https://docs.djangoproject.com/zh-hans/3.1/ref/contrib/staticfiles/#module-django.contrib.staticfiles) -- 管理静态文件的框架。

### 查看迁移命令会执行哪些SQL语句

`python manage sqlmigrate appName  appName/migrations/xxx.initial.py`

=>

``` sql

```

### Django 快捷函数 	`django.shortcuts`

##### django中具有的快捷函数：

* render: 渲染
* get_object_or_404: 获取一个对象，如果不存在就抛出404



## 通用视图



# Django相关

## URL与视图

* 项目结构
* 配置文件
* URL与视图的映射
* URL中添加参数
* path函数
* re_path函数
* url中指定默认的参数
* include函数
* URL反转
* 自定义URL转换器

## 模板

DTL模板

模板变量

if判断

for循环

with和URL等常用标签

add和date等常用过滤器

自定义过滤器

模板继承和block

加载静态文件



## 高级视图

View类视图

TemplateView类视图

WSGIRequest对象

HttpResponse对象

页面跳转和重定向

限制请求的method装饰器

## 模板和数据库

配置MySQL

ORM模型介绍

模型Field详解

Field参数详解

模型中的Meta配置

数据增删改查

表关系一对多

表关系一对一

表关系多对多

模型关联操作

复杂查询

F对象

Q对象

聚合函数

## others

表单验证

内置admin的配置和自定义

中间件和子框架

cookie和session详解

CSRF攻击

django缓存框架

## Memcached缓存

安装与启动

Telnet操作memcached

python操作memcached

## Redis

redis字符串操作

redis列表操作

redis集合操作

Redis哈希操作

Redis事务操作

Redis发布和订阅

rdb和aof持久化

redis密码设置

Python操作Redis



## 项目部署

supervisor： Supervisor是一款运行在类Unix系统（如Linux、MacOS系统）上的进程管理软件，基于Python开发。 ... 有了它，我们再也不用担心由于uwsgi进程莫名被"死掉"而引起的Django网站打不开的情况了

supervisorctl详解

[一份相关配置指南](https://zhuanlan.zhihu.com/p/65040410)