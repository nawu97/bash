# nohup的使用
## 简介：
```
使用该命令运行程序可以忽略挂断信号。一般最后配合&，使程序在后台执行，并且在终端退出后不打断程序执行。
```
## 用法：
```
nohup <command> &
```
例如：
```
nohup python multi-Hesienberg.py &
[1] 238154
(base) [nawu@login01 initial]$ nohup: ignoring input and appending output to ‘nohup.out’
^C
[1]+  Exit 1                  nohup python multi-Hesienberg.py

```
nohup运行时返回程序运行的进程号，命令默认输出到当前目录下的nohup.out文件。
### 指定输入输出
```
nohup python multi-Hesienberg.py >temp.log 2>&1 &
[1] 239614

```
指定输出到temp.log文件。

2 - stderr指标准错误输出，1 - stdout指标准输出，&1表示1输出通道，2>&1表示将2重定向到1，即将标准错误输出传递给标准输出。

常用：
ps -def|grep " command"查看输出

<img width="657" alt="微信截图_20211125174826" src="https://user-images.githubusercontent.com/76439954/143418567-f6d07a30-a670-4fee-b7b6-40904afb2707.png">




UID     //用户ID、但输出的是用户名
PID     //进程的ID
PPID    //父进程ID
C       //进程占用CPU的百分比
STIME   //进程启动到现在的时间
TTY     //该进程在那个终端上运行，若与终端无关，则显示? 若为pts/0等，则表示由网络连接主机进程。
CMD     //命令的名称和参数
