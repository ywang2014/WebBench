## 遇到的问题
1.Codeblocks 编译不成功，minGW的库可能不是标准gcc库，缺少头文件<sys/socket.h>

    socket.h在gcc-5.3.0的base/sys中有，gcc-1.09.1/socket/sys和sys/中有，gcc-2.0.1 gcc-2.23版本中都有
	
2.cygwin编译不成功，缺少头文件<rpc/types.h>，改用头文件<sys/types>编译成功，但是可执行文件无法执行成功，缺少cygwin1.dll，在system32中添加该dll，注册不成功。

3.cygwin中直接根据makefile使用make安装，仍然失败，可能是windows和linux系统环境不同造成的

    <builtin>: recipe for target 'webbench.o' failed
    make: *** [webbench.o] Error 1
