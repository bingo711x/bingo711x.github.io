#make工具
> - [参考1](http://blog.csdn.net/ruglcc/article/details/7814546/)
> - [参考2](http://www.cnblogs.com/mfryf/p/3305778.html)
> - [编译和链接]{参考gcc笔记}

##简介
> make是一个通常应用于Unix平台的自动化编译工具，卸载makefile或Makefile文件中

###make编译规则
1. 如果这个工程没有编译过，那么我们的所有C文件都要编译并被链接。
2. 如果这个工程的某几个C文件被修改，那么我们只编译被修改的C文件，并链接目标程序。
3. 如果这个工程的头文件被改变了，那么我们需要编译引用了这几个头文件的C文件，并链接目标程序。

###格式
target...: prerequisites...

[tab] command
 
* target 目标文件可以是.o，可以使执行文件，也可以是标签
* prerequisites 就是目标生成的依赖，可以使.o,.c,.h
* command 可以使shell支持的任意命令

> - 反斜杠是换行
> - 命令那一行一定要以tab键开头
> - 无参数的情况下，默认执行第一条
> - 比如name.o的依赖，就不用再把name.c加上了，只需要写上其他的依赖
> - 在标签前边加上.PHONY : clean
> - 命令的前一条加上-表示即使出错，也忽略

###变量

如果需要多次写几个依赖，可以在开始定义成变量
> cc = gcc
>objects = main.o kbd.o command.o \

## 写法
### 引入其他的file
> 相当于把要引入的file放到当前的位置，如果在当前路径
中找不到，那么它会在以下两个路径中继续寻找

* make执行的时候加上参数“-I”或者“--include-dir”
* 如果/include(一般是/usr/local/bin或者/usr/include)存在

**MAKEFILES变量:**相当于是include，内容用空格分离，执行这个其他的所有makefile都会受影响
不建议使用
###通配符
* ~ 表示当前用户的根目录，～username便是username这个用户的根目录
* \* 表示任意的字符或字符串
* ? 表示

###文件搜寻路径
* VPATH :如果这个变量被定义，当前make文件就在指定的路径下搜寻目标文件和依赖文件
其写法按照如下方式,使用冒号分割

> VPATH = src:../headers

* vpath：是make工具的关键字，提供更灵活的搜索路径配置

> vpath < pattern> < directories> 为符合模式< pattern>的文件指
定搜索目录<directories>。

> -vpath <pattern> : 清除模式pattern匹配的路径

> vpath ：清除所有

>**%**为匹配符号，比如 vpath %.c foo:bar:src/
###伪目标







