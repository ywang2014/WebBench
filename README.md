# WebBench

Webbench是一个在linux下使用的非常简单的网站压测工具。它使用fork()模拟多个客户端同时访问我们设定的URL，测试网站在压力下工作的性能，最多可以模拟3万个并发连接去测试网站的负载能力。

##使用：

	sudo make && make install
  
##命令行选项：




| 短参        | 长参数           | 作用   |
| ------------- |:-------------:| -----:|
|-f     |--force                |不需要等待服务器响应               | 
|-r     |--reload               |发送重新加载请求                   |
|-t     |--time <sec>           |运行多长时间，单位：秒"            |
    |-p     |--proxy <server:port>  |使用代理服务器来发送请求	    |
|-c     |--clients <n>          |创建多少个客户端，默认1个"         |
     |-9     |--http09               |使用 HTTP/0.9                      |
|-1     |--http10               |使用 HTTP/1.0 协议                 |
     |-2     |--http11               |使用 HTTP/1.1 协议                 |
|       |--get                  |使用 GET请求方法                   |
|       |--head                 |使用 HEAD请求方                    |
|       |--options              |使用 OPTIONS请求方法               |
|       |--trace                |使用 TRACE请求方法                 |
|-?/-h  |--help                 |打印帮助信息                       |
|-V     |--version              |显示版本号                         |

#### 遇到问题

1.Codeblocks 编译不成功，minGW的库不是标准gcc库，缺少头文件<sys/socket.h>

2.cygwin编译不成功，缺少头文件<rpc/types.h>，改用头文件<sys/types>编译成功，但是可执行文件无法执行成功，报错缺少cygwin1.dll，在system32中添加该dll，报错注册不成功。

3.cygwin中，makefile 直接安装，仍然错误。

	<builtin>: recipe for target 'webbench.o' failed
 	make: *** [webbench.o] Error 1
