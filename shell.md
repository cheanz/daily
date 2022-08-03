# ISSUE 1  
tty height not enough simply means terminal window is not high enough and you should drag it higher so that TUI can run.
# postinst
set -e 　若指令传回值不等于0，则立即退出shell
ln means link
`ln -s(symbolic link)f(force 强行删除已经存在的目标文件）`
*** 
Read overlay.py  
# python  
## lambda  
`(lambda parameter: expression)(argument)`
## os module  
All of these functions accept either only bytes or only string objects as their parameters. 
```
import os 
out = os.path.basename("/baz/foo")
print(out)//foo
out = os.path.dirname("/baz/foo")
print(out)//'/baz'
```
## subprocess
subprocess模块用来创建新的进程，连接到其stdin、stdout、stderr管道并获取它们的返回码。subprocess模块的出现是为了替代如下旧模块及函数：os.system、os.spawn*、os.popen*、popen2.*、commands.*。强烈建议POSIX用户（Linux、BSD等）安装并使用较新的subprocess32模块，而不是Python 2.7自带的subprocess。
Windows NT
POSIX：一种标准，仿照早期unix系统界面建立，与linux兼容
  完成同一功能，不同内核提供的系统调用（也就是一个函数）是不同的，例如创建进程，linux下是fork函数，windows下是creatprocess函数。好，我现在在linux下写一个程序，用到fork函数，那么这个程序该怎么往windows上移植？我需要把源代码里的fork通通改成creatprocess，然后重新编译...

  posix标准的出现就是为了解决这个问题。linux和windows都要实现基本的posix标准，linux把fork函数封装成posix_fork（随便说的），windows把creatprocess函数也封装成posix_fork，都声明在unistd.h里。这样，程序员编写普通应用时候，只用包含unistd.h，调用posix_fork函数，程序就在源代码级别可移植了
程序员只管API kernel只管系统调用


*注意：不要为stdout和stderr参数赋值为subprocess.PIPE*   

### call  
subprocess.call(args, *, stdin= None, stdout = None, stderr = None, shell = False)
运行由args参数提供的命令，等待命令执行结束并返回返回码。args参数由字符串形式提供且有多个命令参数时，需要提供shell=True参数
### check_call
subprocess.check_call(args, *, stdin = None, stdout = None, stderr = None, shell = False)
与call方法类似，不同在于如果命令行执行成功，check_call返回返回码0，否则抛出subprocess.CalledProcessError异常。
subprocess.CalledProcessError异常包括returncode、cmd、output等属性，其中returncode是子进程的退出码，cmd是子进程的执行命令，output为None。
### check_output

subprocess.check_output(args, *, stdin = None, stderr = None, shell = False, universal_newlines = False)
在子进程执行命令，以字符串形式返回执行结果的输出。如果子进程退出码不是0，抛出subprocess.CalledProcessError异常，异常的output字段包含错误输出：
```
import subprocess
try:
    res = subprocess.check_call(['ls', '('])
    print  'res:', res
except subprocess.CalledProcessError, exc:
    print 'returncode:', exc.returncode
    print 'cmd:', exc.cmd
    print 'output:', exc.output
    try:
    res = subprocess.check_output('ls xxx',
                    stderr = subprocess.STDOUT,
                    shell = True)
    print  'res:', res
except subprocess.CalledProcessError, exc:
    print 'returncode:', exc.returncode
    print 'cmd:', exc.cmd
    print 'output:', exc.output

```
## What's the difference？
res print出来不同
## __file__  

os.path.dirname(__file__)  
其实就是当前脚本运行的路径。

但是也会分不同的情况。

如果执行命令时使用绝对路径，__file__就是脚本的绝对路径。

如果使用的是相对路径，__file__就是脚本的相对路径。

注：

如果在交互式环境中，则会爆出异常。因为此时__file__并未生成。

```
#为 bytes() 方法指定字符集
b4 = bytes('C语言中文网8岁了', encoding='UTF-8')
print("b4: ", b4)
#通过 encode() 方法将字符串转换成 bytes
b5 = "C语言中文网8岁了".encode('UTF-8')
print("b5: ", b5)
```
# shift  
shift parameter poistion
```
$1,$2,
shift;shift;
```  
![Screenshot from 2022-07-22 10-00-13](https://user-images.githubusercontent.com/59786755/180346510-2762d795-0787-40d5-bb42-7685e815a3ea.png)  

but it cant shift $@

# variables
`myname=$1` is correct
while `myname = $1` is not.  
```
read myname
```  
## scope of variables

* export
* source  or  .
* curly bracket
#!/bin/sh
echo "What is your name?"
read USER_NAME
echo "Hello $USER_NAME"
echo "I will create you a file called ${USER_NAME}_file"
touch "${USER_NAME}_file"

# which, whereis and whatis  
which: show file-system location; report on your aliases;
whereis: shwo file-system location; manual pages location;
whatis: brief descriptions of command with man page index
```bash
man 3p shutdown
man 8 shutdown
```
`echo $PATH`  
Check your search path. (personal bin or current positions shouldnt be in the first place of $PATH)
# bash -c!  

![image](https://user-images.githubusercontent.com/59786755/182543158-09bc9b39-a36d-49f8-b7d4-c673149eefb2.png)


-c means command
$0 is always the filename.sh itself. $@ or $* represents from $1,$2......
```
bash -c "echo '$0 is $0, $1 is $1, $2 is $2'" foo bar bi
bash -c 'echo "$0 is $0, $1 is $1, $2 is $2"' foo bar biz
```
```
echo $PATH
echo $shell
```
