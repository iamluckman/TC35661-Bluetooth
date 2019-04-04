<a href="https://996.icu"><img src="https://img.shields.io/badge/link-996.icu-red.svg" alt="996.icu" /></a>


[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)


source project at 
https://github.com/yuht/TC35661-Keil




//---------------------------
2016.6.11
	1.BT不需要输入密码配对
	2.BLE 、BT通信方式

//---------------------------
2016.5.20
	1.android方式和ios方式不同。 android使用传统蓝牙方式， ios使用BLE方式。
	2.对代码进行了android和ios区分。
	3.android需要配对输入PIN，需要对方和自己的蓝牙地址。
	4.ios使用BLE，使用SERVICE概念。对SERVICE进行读写。
	4.1 该模块代码包含2个SERVICE，一个是device service，一个是功能service。


//---------------------------
2016.5.18增加
	1.该代码在android蓝牙可以使用。
	1.1注释掉的初始化代码为ios所使用的service。不影响android
	2.ios通信状态下，没有检测到通信指令和通信内容。没法做ios通信。

//---------------------------



1.下载 
1.1 InitModule\debugcommand.exe
1.2 InitModule\初始化命令.txt
1.3 模块说明.txt
1.4 请求配对指令.txt

2.运行
2.1 初始化模块
  
 
  2.1.1 启动debugcommand.exe指定COM口
  
  2.1.2 点打开串口和文件
  2.1.2.1 如果串口打开成功，选择文件“InitModule\初始化命令.txt”
  2.1.2.2 如果串口提示错误，请重新核对串口。
  
  2.1.3 都打开后，会提示“文件已经打开，等待发送。 串口xx已打开”


  2.1.4 对tc35661 模块的rst引脚先连接到gnd， 再接回vcc。

  2.1.5 如果模块复位，会显示“04 0E 04 04 00 00 00” 如果没有显示， 重复2.1.4

  2.1.6 然后点按钮"2.发送命令" 将初始化指令逐条发送。

2.2 蓝牙配对
  2.2.1 当软件内容不再滚动， 这时候，用手机就可以搜索到蓝牙模块"BA80072323" 
  2.2.2 手机点蓝牙模块，电脑软件窗体会提示配对指令“10 00 00 E1 55 09 00 4D 8D B2 BF 27 28 0C 02 5A”
  2.2.3 打开“请求配对指令.txt”。从最下开始向上看，因为最下面是最先受到的数据，上面是最后的数据。 里面有【注意点 x】,都是需要注意的地方
  2.2.4 根据“请求配对指令.txt”说描述的内容在电脑“发送单条指令左边输入”相应修改后的指令。
  2.2.5 完成配对，发送，接收数据真个过程。
