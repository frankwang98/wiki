# STM32项目笔记

## 一、学习方法
STM32和51的学习方法类似。

首先，准备一块开发板，一个下载器，还有一些常用外设（如串口、CAN、ADC/DAC等）；然后，把例程都调通；最后，自己开发和修改程序。

不同的是，51是用寄存器编程，而STM32有寄存器、库函数、HAL库三种编程方式。寄存器版本要看一遍，库函数重点学习，HAL库可以当作备用。

大多数人已经习惯库函数编程，因此在这里也统一用**库函数**。

看现成的代码和手把手自己敲一遍，效果是完全不同的。**代码重在实践！**

另外大家都知道计算机的四个主干课程是**composition 计算机组成与原理、OS 操作系统、Network 网络和Algorithm 数据结构与算法**。

通过STM32这个单片微型计算机的学习，去了解计算机的组成、通信、操作系统的使用，以及软件算法的编写；如果是软件方向，可以从裸机到Linux开发板，从写驱动到写应用逻辑；如果想做硬件方向，可以先从认识元器件开始，学习数电、模电，尝试画一个最小系统板，并学会打板、焊接等手艺，是一个很酷的事情。

## 二、硬件介绍
STM32是ST公司基于ARM Cortex-M内核开发的32位微控制器。

STM32常用在嵌入式领域。其功能强大、性能优异，片上资源丰富、功耗低，是一款经典的MCU。

STM32精英板，买到板子后，先通电测试一下，默认出厂是烧录好综合测试程序的。

尤其要注意TFTLCD屏幕是否正常亮，这个容易出问题；另外，如果自己烧录程序出现白屏情况，很可能是lcd.c这个外设函数与你用的屏幕硬件不匹配了，自己解决不了的情况下，去联系商家要一个最新的程序库，亲测有效。

## 三、软件搭建

MDK

ST-Link

Flymcu

Cutecom

USB-CAN Tool

## 四、项目案例

| 入门案例                                        |  高级案例                                      |
| ----------------------------------------------- |  --------------------------------------------- |
| 新建工程                                        |  基于STM32 的自动刹车灯设计                    |
| [跑马灯](http://t.csdn.cn/VuasT)                |  基于STM32F407的openmv项目设计                 |
| 蜂鸣器                                          |   STM32 无线抢答器                              |
| 按键输入                                        |  基于 ARM-STM32的两轮自平衡小车                |
| 串口实验                                        |  基于STM32F4高速频谱分析仪                     |
| 外部中断                                        | 基于STM32F4的信号分析仪设计                   |
| 独立看门狗                                      |  基于STM32 的数字示波器设计                    |
| 窗口看门狗                                      |  基于ARM-CORTEX M3的STM32F103的移动电源设计    |
| 定时器中断                                      |  基于STM32的手机WIFI控制四轴飞行器设计         |
| PWM输出                                         | 基于RFID技术、以STM32为终端的智能小区管理系统 |
| 输入捕获                                        |                                               |
| 触摸按键                                        |                                               |
| OLED显示                                        |                                                |
| TFTLCD显示                                      |                                               |
| USMART调试                                      |                                                |
| RTC                                             |                                                |
| 待机唤醒                                        |                                                |
| ADC                                             |                                                |
| 内部温度传感器                                  |                                               |
| 光敏传感器                                      |                                                |
| DAC                                             |                                                |
| DMA                                             |                                                |
| IIC                                             |                                                |
| SPI                                             |                                               |
| 485                                             |                                                |
| CAN收发                                         |                                               |
| 触摸屏                                          |                                                |
| 红外遥控                                        |                                               |
| 18B20数字温度传感器实验                         |                                                |
| DHT11数字温湿度传感器实验                       |                                               |
| MPU6050六轴传感器实验                           |                                               |
| 无线通信                                        |                                                |
| FLASH模拟EEPROM                                 |                                                 |
| 摄像头                                          |                                                |
| 内存管理                                        |                                                |
| SD卡 SDIO                                       |                                                |
| FATFS                                           |                                               |
| 汉字显示                                        |                                                 |
| 图片显示                                        |                                                |
| 照相机                                          |                                                |
| 手写识别                                        |                                               |
| T9拼音输入法                                    |                                               |
| 串口IAP                                         |                                               |
| USB虚拟串口                                     |                                              |
| USB读卡器                                       |                                              |
| UCOSII实验-1-任务调度                           |                                             |
| UCOSII实验-2-任务创建删除挂起恢复               |                                             |
| UCOSII实验-3-信号量和邮箱                       |                                              |
| UCOSII实验-4-消息队列、信号量集和软件定时器      |                                            |
| 综合测试实验                                    |                                       |

## 五、参考资料
[opendev](http://www.openedv.com/docs/index.html)