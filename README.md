# QT6-MySQL-
用QT6连接MySQL，设计小型数据库，实现不同用户级别对于数据库的增删改查。
数据库建表及索引、触发器等语句已上传
租户客户端和房东客户端集合在一起了（因为懒得弄两个一样的客户端）
整体都是用自动生成的槽和信号连接的（除了回车信号和admin界面的退出是自己写的），因此不要轻易改动对象名称，
管理员客户端（adminwindow）懒得重写函数，直接switch判断当前页面全程c+v了，可读性很差，除了能跑的起来一无是处
整体代码突出一个懒，看看思路就OK
已知BUG：admin界面新增row时还可以更改其他row的数据，想实现锁定其他row但是国内网上实现太复杂，果断放弃

QT6的MySQL驱动配置看这：https://blog.csdn.net/DreamerZC/article/details/128040436


QT6打包后实现连接数据库看这：
首先在你的main.cpp里添上     a.addLibraryPath("./plugins"); 这么一句，设置你的库路径为当前目录下的plugins文件夹
打包后将
Q\6.4.1（你的版本号）\msvc2019_64（你用的编译器）\bin中的libmysq.dll添加到打包后文件exe的同级目录
QT\6.4.1\msvc2019_64\bin中的plugins文件夹整个拖到打包后文件exe的同级目录
这时候就能成功连接MySQL了