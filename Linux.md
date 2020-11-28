# LInux (CentOS 8)

## 命令行

### 目录

#### 当前目录

##### 	cd：切换目录

​		**cd /home/sh-yj/example**		TAB键可自动补全

​		**cd ~/example**		其中~特指用户的主目录

​		**cd**		回到用户主目录的位置

##### 	pwd：显示当前工作目录

##### 	ls：列出文件和目录

​		**ls** 

​		**ls ~/example**

​		**ls -l ~example**		-l 参数表示详细模式

##### 	绝对与相对路径

​		绝对路径	**/home/sh-yj/example**

​		相对路径：

​			**.	当前目录**

​			**..	上级目录**

​			**../hello	上级目录下的hello子目录**

#### 目录操作

##### mkdir：创建目录

​		**mkdir abc**

​		**mkdir -p abc/123/test**	-p参数可以将路径的层次目录全部创建

##### 	rmdir：删除空目录

​		**rmdir abc**	如果目录非空，则删除失败

##### 	rm：删除文件或目录

​		**rm -rf abc**	删除abc目录，和子项一并删除

​		**r 表示 recursive(递归), f 表示 force(强制)**

##### 	cp：复制文件或目录

​		**cp -rf example example2**

##### 	mv：移动文件或目录(重命名)

​		**mv hello helloworld**

#### 归档压缩(tar)

##### 	归档

​	创建档案包

​		**tar -cvf example.tar example** 

​		**c：表示创建档案**

​		**v：表示显示详情**

​		**f：表示file**

​		**也可以多个目录打包 tar -cvf xxx.tar file1 file2 file3**

##### 	压缩

​	还原档案包

​		**tar -xvf example.tar**

​		**tar  -xvf example.tar -C outdir**

​		**-C参数指定目标目录，默认解压到当前目录下**

##### 	归档并压缩

​		并档压缩

​		**tar -czvf example.tar.gz example**

​		解压缩

​		**tar -xzvf example.tar.gz**

​		**tar -xzvf example.tar.ge -C outdir**

#### 软链接(ln)

同‘windows’的快捷方式

​	**ln -s example example2**

​	**-s 表示soft 软链接（默认为硬）**

### 用户和组

#### 用户管理

##### su：切换用户

​	**su username**	默认切换到root，输入密码不外显

​	当前会话终端变为 root ,并非整个登录

##### useradd：添加用户

​	**useradd test1**

​	默认创建一个用户会同时创建一个同名的组，组里只有一个用户

##### passwd：修改用户密码

​	**passwd test1**

##### userdel：删除用户

​	**userdel test1**

#### 组的管理

**groupadd boys**	创建boys组

**groupdel boys**	删除boys组

**useradd -g boys test1**

​	**-g 表示添加用户，同时将用户加到boys组**

**usermod -g boys sh-yj**	添加现有用户到当前组

​	**usermod 表示用户信息**

**cat /etc/group**	查看用户和组

​	每一行表示一个group的信息，名称+ID

**cat /etc/passwd**	查看用户列表

### 文件

