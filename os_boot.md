启动

disk存放os
1. bios: baisc I/O 处理系统，初始化检查，将bootloader放入内存
2. bootloader(占据非常小的空间): 加载os, 将其放入内存，cpu控制权交给os


3种状态
1. 系统调用（来源于应用程序，异步或同步，等待和持续）：system call, 应用程序主动向操作系统发出服务请求
2. 异常（来源于不良的应用程序，同步，杀死或重新执行意想不到的指令）：exception, 非法指令或坏的处理状态（如内存出错）
3. 中断（来源于外设, 异步，持续，对用户应用程序是透明的）： interrupt, 来自不同的硬件设备的计时器和网络中断

为什么应用程序通过os间接访问外设？
1. 只有内核可以执行特权指令（不同于管理员模式，管理员模式是kernel再往上的,windows仅希望管理员处理的一个薄墙）
2. 内核是被信任的第三方，有些应用程序并不被信任
3. 方便应用程序，屏蔽底层的复杂性

