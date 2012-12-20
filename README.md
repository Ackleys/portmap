
端口映射器

由于网络上下载的一个貌似delphi写的PortMap v1.6( http://www.onlinedown.net/soft/7023.htm )版本的工具频率崩溃, 于是花了一些时间重写了一个用于做端口映射的工具程序, 虽然简单, 但却实用, 本来想再添加一个支持sock5代理, web远程管理, 以及GUI和日志功能, 和各链接数据收发统计日志, 但是由于个人时间有限, 所以希望有兴趣的朋友能参与来完善等其它额外功能.
编译说明:
依赖boost, 编译器vc2003以上或gcc, 目前运行平台支持windows和linux.
在windows上直接使用vc2003以上版本打开portmap.sln即可编译.
在linux平台可使用boost的bjam进行编译.
编译参数:
定义LOGGER_OUTPUT_LOG宏表示打开日志输出功能.
定义LOGGER_DEBUG_VIEW表示打开debugview调试功能, 仅能在win32平台下使用.
定义LOGGER_THREAD_SAFE表示日志输出使用线程安全.
若使用bjam进行编译, 则需要设置环境变量
BOOST_ROOT=BOOST的ROOT目录
BOOST_BUILD_PATH=$(BOOST_ROOT)/tools/build/v2
然后执行
bjam
或
bjam define=LOGGER_OUTPUT_LOG
即可编译.
运行配置参数需要修改文件conf.cfg, 如:

server port=8080
remote host=127.0.0.1:80

注: 在release下有已经编译好的exe, 可以直接测试使用.

