#gem 相当于 Python pip
#docker  
Docker 是一个开源的应用容器引擎，基于 Go 语言 并遵从 Apache2.0 协议开源。

Docker 可以让开发者打包他们的应用以及依赖包到一个轻量级、可移植的容器中，然后发布到任何流行的 Linux 机器上，也可以实现虚拟化。

容器是完全使用沙箱机制，相互之间不会有任何接口（类似 iPhone 的 app）,更重要的是容器性能开销极低。
***
<img width="462" alt="image" src="https://user-images.githubusercontent.com/107660838/175251719-5214580c-a0a9-4a8a-8127-f3bd63d287b8.png">
comment: 将$UID修改为USERNAME

<img width="291" alt="image" src="https://user-images.githubusercontent.com/107660838/175290080-df9c4c97-26f7-40eb-9272-342e61798d9b.png">
直接删除一个文件夹 简单粗暴

<img width="248" alt="image" src="https://user-images.githubusercontent.com/107660838/175290410-543cdc1e-4363-48f5-b74b-37627778099f.png">
隐藏文件夹

<img width="552" alt="image" src="https://user-images.githubusercontent.com/107660838/175291432-0e805aed-de48-4969-a8c3-61dbd7818f5e.png">
绿色的是 executable file exe文件啊！！！

<img width="266" alt="image" src="https://user-images.githubusercontent.com/107660838/175292665-deccf4da-69cb-42a3-b01e-25660db216a3.png">
very useful

<img width="671" alt="image" src="https://user-images.githubusercontent.com/107660838/175293369-25bb89a5-c4b1-4a23-a4fc-9474b4f1dbca.png">
？？明日再议
warning是正常现象因为在docker里面生成镜像
bootstrap卡住可以ctrl+c 激活一下

# make.log
`$make 2>&1|tee xxx.log`，“0”表示标准输入，“1”表示标准输出，“2”表示标准出错信息输出。2>&1表示把2设备的信息重定向到1设 备；“|”是管道符号，把标准输出的信息直接传递给后面的命令；tee是创建文件并保存信息的工具；xxx.log是文件名
<img width="515" alt="image" src="https://user-images.githubusercontent.com/59786755/175455396-082a954c-e5dd-475d-a6b9-51fb30bfa974.png">
