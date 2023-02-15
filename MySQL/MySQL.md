# MySQL
mysql安装
#### 1.官网下载MySQL
#### 2.配置初始化文件my.ini
#### 3.初始化MySQL
#### 4.安装mysql服务并启动+修改密码
#### 5.配置环境变量
#### 6.mysql 连接 Navicat



## 1. 官网下载MySQL

官网地址：https://dev.mysql.com/downloads/

选择"MySQL Community Server"下载

![image](https://user-images.githubusercontent.com/63994835/159439974-a7305c6a-f17c-4e68-9fd1-9aae8be26b71.png)

----------------------------

![image](https://user-images.githubusercontent.com/63994835/159440007-9c288ad6-3cf4-4ba5-92e1-9bf51b321068.png)

----------------------------

![image](https://user-images.githubusercontent.com/63994835/159440085-e8f0f665-5868-4b30-b474-02a8b2c4c379.png)

**下载完成后，将解压后的文件夹放到某一个文件夹，我放在D盘中（记住存放路径，后面需要用到！！）**


## 2. 配置初始化文件my.ini

在根目录下新建一个my.ini的文件，（新解压的文件没有my.ini文件，需自行创建）

![image](https://user-images.githubusercontent.com/63994835/159443554-4cc822e1-4b31-4ed6-8b4b-b59b8d974d52.png)

之后复制下面这个代码放在文件下，以下代码除安装目录和数据的存放目录（改成你刚才解压后的文件存放的位置）需修改，其余不用修改

```
[mysqld]
# 设置3306端口
port=3306
# 设置mysql的安装目录   ----------是你的文件路径-------------
basedir=D:\mysql\mysql-8.0.28-winx64
# 设置mysql数据库的数据的存放目录  ---------是你的文件路径data文件夹自行创建
datadir=D:\mysql\mysql-8.0.28-winx64\data
# 允许最大连接数
max_connections=200
# 允许连接失败的次数。
max_connect_errors=10
# 服务端使用的字符集默认为utf8mb4
character-set-server=utf8mb4
# 创建新表时将使用的默认存储引擎
default-storage-engine=INNODB
# 默认使用“mysql_native_password”插件认证
#mysql_native_password
default_authentication_plugin=mysql_native_password
[mysql]
# 设置mysql客户端默认字符集
default-character-set=utf8mb4
[client]
# 设置mysql客户端连接服务端时默认使用的端口
port=3306
default-character-set=utf8mb4
```

## 3.初始化MySQL

按住 win+r 键, 输入cmd, 进入终端界面

![image](https://user-images.githubusercontent.com/63994835/159444055-898677cd-542b-4767-9f87-53b3125e0848.png)

----------------------------

输入命令：cd D:\mysql\mysql-8.0.28-winx64\bin 进入bin目录，

![image](https://user-images.githubusercontent.com/63994835/159452830-530db3e8-4af0-4715-89cd-d01434b91bb9.png)

----------------------------

输入命令： mysqld --initialize --console

![image](https://user-images.githubusercontent.com/63994835/159453083-69402062-9d7d-44e5-acbd-7a03fdb4188f.png)

----------------------------

复制最后一行root@localhost后的密码，这个密码是进入数据库的初始密码（一定要保存好！）P!tk(6+;#Ol#

![image](https://user-images.githubusercontent.com/63994835/159453226-8d6fa9ad-794c-4866-94e1-88f47b2c1416.png)

## 4.安装mysql服务并启动+修改密码

安装mysql服务，输入命令：mysqld --install mysql

![image](https://user-images.githubusercontent.com/63994835/159453410-79c1ae5d-d595-437b-860b-4aa2a1ca1c02.png)

----------------------------

启动mysql服务，输入命令：net start mysql

![image](https://user-images.githubusercontent.com/63994835/159454058-0f4a4195-540c-45f0-a94c-2e93ab6e3678.png)

----------------------------

若启动mysql服务器失败，显示：'net’ 不是内部命令或外部命令，也不是可运行的程序或批处理文件，解决方案如下：

我的电脑-->属性-->高级-->环境变量 Path的变量值新加: %SystemRoot%\system32（以“；”隔开即可）

----------------------------

开始连接mysql, 输入命令：mysql -uroot -p

![image](https://user-images.githubusercontent.com/63994835/159454612-ceb1b030-a5f2-4aeb-a4d0-5f4f1b7cb07e.png)

----------------------------

输入刚才保存的密码，大家输入后直接点击回车即可

![image](https://user-images.githubusercontent.com/63994835/159456002-c2ee539e-50ce-4bda-b636-c2756c63394e.png)

----------------------------

由于初始密码过于复杂，很难记，下面更改下密码

输入命令：ALTER USER 'root'@'localhost' IDENTIFIED BY '新的密码'

![image](https://user-images.githubusercontent.com/63994835/159464763-40f4b8d4-4b14-48f5-9950-d2a6c4126473.png)

## 5.配置环境变量

为了避免每次都需要输入cd命令，再输入相关命令的麻烦， 我们配置下环境变量即可。

首先，打开系统环境变量界面

![image](https://user-images.githubusercontent.com/63994835/159465562-dc34a536-0b70-4fa8-90eb-028f59c4b247.png)

----------------------------

点击"环境变量"

![image](https://user-images.githubusercontent.com/63994835/159465655-14fd53bf-a61d-46b8-b4b7-59bdbbd771e9.png)

----------------------------

点击"新建"

![image](https://user-images.githubusercontent.com/63994835/159466018-98a44256-7865-4d40-8d71-72bc36c8e912.png)

----------------------------

再输入以下内容，变量值要根据自己的存放位置进行更改；最后，点击"确定"

![image](https://user-images.githubusercontent.com/63994835/159466192-a8b9ff20-3f28-42b5-8daf-58665d349d87.png)

----------------------------

然后，点击"系统变量"中的path

![image](https://user-images.githubusercontent.com/63994835/159465790-5f19d334-6080-491b-b01a-f55f5aacb3a3.png)

----------------------------

点击"新建"

![image](https://user-images.githubusercontent.com/63994835/159465818-7ffb6c2d-8921-4e82-9bb1-2473e60de03d.png)

----------------------------

加入以下两个内容即可，点击"确定"

![image](https://user-images.githubusercontent.com/63994835/159466559-d0d30e8c-cd16-46cc-b07d-eab18ca0783b.png)

----------------------------

此外，还需要在自己的环境变量中，加入bin的路径，如下

![image](https://user-images.githubusercontent.com/63994835/159467712-7d3f02dd-2bf0-4d5c-9ff8-31fda7ca9e5d.png)

----------------------------

![image](https://user-images.githubusercontent.com/63994835/159467736-70ef9ebb-c47e-4722-9627-d770bc3ff8da.png)

----------------------------

后面，大家需要进入mysql，只需要在命令行输入：mysql -uroot -p 

![image](https://user-images.githubusercontent.com/63994835/159467808-7b8755eb-31df-4196-a64b-c91799a21254.png)


## 6.mysql 连接 Navicat

打开Navicat, 点击"连接"

![image](https://user-images.githubusercontent.com/63994835/159467978-d49a81d9-f53e-445b-9975-f40786296004.png)

选择"mysql"

![image](https://user-images.githubusercontent.com/63994835/159468033-31e7c9ab-639d-4f6c-9304-4fa5f1ac2df9.png)

随便输入一个连接名，然后输入你的mysql密码就行，点击"确定"

![image](https://user-images.githubusercontent.com/63994835/159468188-9248c57e-ac3b-4d83-8967-e02b4508e96b.png)

