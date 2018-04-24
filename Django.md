# virtualenv 虚拟环境创建
1. 安装virtualenv

```
pip install virtualenv
```

2. 创建虚拟环境

指定安装虚拟环境中的python版本的安装方式
>在Windows的cmd.exe下如果安装路径有空格可以用""转义空格
```
virtualenv --no-site-package -p C:\"Program Files"\Python36\python.exe env
```

3. 进入和退出env

进入

```
cd env/Scripts
activate
```
退出

```
deactivate
```


# Django 的使用

## 创建一个Django项目
1. 首先先创建一个运行Django项目的虚拟环境(virtualenv)

虚拟环境中有python, Django, pymysql等需要的库

大致安装下面的库

```
pip install Django==1.11
pip install PyMySQL
```

2. 创建一个Django项目
创建一个名为helloworld的项目

```
django-admin startproject helloworld
```

项目下有
- helloworld: 项目的容器
- **manage.py:** 是Django用于管理本项目的管理集工具,是一个实用的命令行工具, 可以让你以各种方式与该Django项目进行交互
- helloworld\\\_\_init__.py: 一个空文件, 告诉Python 该目录是一个Python 包
- helloworld\\settings.py: 是Django项目的配置/设置
- helloworld\\urls.py: 该Django项目的URL声明, 一份有django驱动的网站"目录"
- helloworld\\wsgi.py: 一个WSGI兼容的Web服务器端口, 以便运行你的项目


3. 启动项目

```
python manage.py runserver IP:端口
```

4. 创建app

```
python manage.py startapp app_name
```
5.配置settings.py文件
settings文件中INSTALLED_APPS中写入创建的app的name
也可以导入apps.py文件中的APPCONFIG下的name属性

6. 模型
在models.py文件中定义class模型名称Student
继承models.Model
db_tables: 定义数据库中的表的名称

7. 数据库迁移

```
python manage.py makemigrations
```

```
python manage.py migrate
```

8. 保持数据 
stu = Student()
stu.name = 'xxx'
stu.save()

9. 创建超级管理员的账号和密码

```
python manage.py createsuperuser
```
10. ORM 对象关系映射

11. 模型字段

- CharField: 字符串
    - max_length:长度
- BooleanField：布尔类型
  - ```1, 0```

- DateField: 年月日，日期
  - auto_now_add： 第一次创建的时候赋值
  - auto_now：每次修改的时候赋值
- DateTimeField：年月日 时分秒
  - auto_now_add
  - auto_now

- AutoField：自动增长

- DecimalField： 
  - models.DecimalField(max_digits=3, decimal_places=1)
  - max_digits：总位数
  - decimal_places：小数后多少位

- TextField：存文本信息
- IntegerField：整数
- FloatField：浮点

- FileField：文件上传字段
- ImageField：上传图片
  - upload_to="" 指定上传图片的路径


12. 模型参数
- default: 默认
- null ：设置是否为空，针对数据库中该字段是否可以为空
- blank ：设置是否为空，针对表单提交该字段是否可以为空

- primary_key：创建主键
- unique：唯一





