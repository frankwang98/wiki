# ARM那些事儿

## ARM公司过往
英国ARM公司是全球领先的半导体知识产权（IP）提供商。全世界超过95%的智能手机和平板电脑都采用ARM架构。ARM设计了大量高性价比、耗能低的RISC处理器、相关技术及软件。2014年基于ARM技术的全年全球出货量是120亿颗，从诞生到现在为止基于ARM技术的芯片有600亿颗 。技术具有性能高、成本低和能耗省的特点。在智能机、平板电脑、嵌入控制、多媒体数字等处理器领域拥有主导地位。
   
2016年7月18日，日本软银已经同意以234亿英镑（约合310亿美元）的价格收购英国芯片设计公司ARM。软银认为，凭借这笔收购，ARM将让软银成为下一个潜力巨大的科技市场（即物联网）的领导者。   

这笔交易将在周一早晨宣布。软银和ARM暂时都未对此发表评论。  
 
2022年2月9日讯，英伟达终止收购ARM(收购失败)。因此当前还是属于日本软银。  

1991 年，ARM 公司成立于英国剑桥，主要出售芯片设计技术的授权。采用ARM技术知识产权（IP核）的微处理器，即我们通常所说的ARM 微处理器，已遍及工业控制、消费类电子产品、通信系统、网络系统、无线系统等各类产品市场，基于ARM 技术的微处理器应用约占据了32 位RISC 微处理器75%以上的市场份额，ARM 技术正在逐步渗入到我们生活的各个方面。   

ARM 公司是专门从事基于RISC 技术芯片设计开发的公司，作为知识产权供应商，本身不直接从事芯片生产，靠转让设计许可由合作公司生产各具特色的芯片，世界各大半导体生产商从ARM公司购买其设计的ARM微处理器核，根据各自不同的应用领域，加入适当的外围电路，从而形成自己的ARM微处理器芯片进入市场。全世界有几十家大的半导体公司都使用ARM公司的授权，因此既使得ARM 技术获得更多的第三方工具、制造、软件的支持，又使整个系统成本降低，使产品更容易进入市场被消费者所接受，更具有竞争力。  
  
ARM是一个发展思路奇特的公司，通过IP知识产权来盈利。    

## ARM处理器
`ARM(开放设计) vs Intel(封闭设计)`

ARM处理器是英国Acorn有限公司设计的低功耗成本的第一款RISC微处理器。全称为Advanced RISC Machine。ARM处理器本身是32位设计，但也配备16位指令集，一般来讲比等价32位代码节省达35%，却能保留32位系统的所有优势。 


### 特点
ARM处理器的三大特点是：耗电少功能强、16位/32位双指令集和合作伙伴众多。  
1. 体积小、低功耗、低成本、高性能；  
2. 支持Thumb（16位）/ARM（32位）双指令集，能很好的兼容8位/16位器件；  
3. 大量使用寄存器，指令执行速度更快；  
4. 大多数数据操作都在寄存器中完成；  
5. 寻址方式灵活简单，执行效率高；  
6. 指令长度固定。  

系列产品有：ARM7系列　ARM9系列　ARM9E系列　ARM10E系列等 
 
最常见的还是**Cortex系列**，Cortex系列属于ARMv7架构，这是到2010年为止ARM公司最新的指令集架构。  

ARMv7架构定义了三大分工明确的系列：**“A”系列面向尖端的基于虚拟内存的操作系统和用户应用；“R”系列针对实时系统；“M”系列对微控制器。**  

由于应用领域不同，基于v7架构的Cortex处理器系列所采用的技术也不相同，基于v7A的称为Cortex-A系列，基于v7R的称为Cortex-R系列，基于v7M的称为Cortex-M系列。   

### Cortex系列

#### A系列
高端应用芯片，例如几乎所有的手机芯片都是A系列的，经常听到的有a53、a76，现在还用树莓派、Jetson系列等智能终端。

#### R系列
一般用在高实时性的工业场景，如医疗器械、网络交换机等。

#### M系列
用在一般工业场景，如3C数码、汽车控制器，最出名的是STM32单片机都是这个系列。  	
