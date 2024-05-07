### ADC模块<!-- {docsify-ignore} -->

> 芯片具有 1 个 12 位的 SARADC（successive approximation analog-to-digital converter）。该模块共有 12 个要被测量的通道，包括 10 个外部通道和 2 个内部通道。
>
> 各通道的转换模式可以设定为单次、连续、扫描、不连续模式。转换结果存储在左对齐或者右对齐的 16 位 数据寄存器中。
>
> 模拟 watchdog 允许应用检测是否输入电压超出了用户定义的高或者低阈值。
>
> ADC 实现了在低频率下运行，可获得很低的功耗。



**ADC 主要特性**

* 高性能 

  * 12bit、10bit、8bit 和 6bit 分辨率可配置 

  * ADC 转换时间：1us@12bit（1MHz）

  * 自校准 

  * 可编程的采样时间 

  * 可编程的数据对齐模式 

  * 支持  DMA

* 低功耗 

  * 为低功耗操作，降低 PCLK 频率，而仍然维持合适的 ADC 性能 

  * 等待模式：防止以低频 PCLK 运行产生溢出

* 模拟输入通道 

  * 10 个外部模拟输入通道：PA[7:0]和 PB[1:0] 

  * 1 个内部 temperature sensor 通道 

  * 1 个内部参考电压通道（VREFINT） 

* 转换操作启动可以通过

  * 软件启动 

  * 可配置极性的硬件启动（TIM1、TIM3 或者 GPIO） 

* 转换模式 

  * 单次模式(single mode)：可以转换 1 个单通道或者可以扫描一系列通道 

  * 连续模式(continuous mode)：连续转换被选择的通道 

  * 不连续模式(discontinuous mode)：每次触发，转换被选择的通道 1 次 

* 中断产生 

  * 在采样结束 

  * 在转换结束 

  * 在连续转换结束 

  * 模拟看门狗事件 

  * 溢出事件 

* 模拟看门狗



**配置ADC**

> 软件必须在 ADC 禁止(ADEN 必须为 0) 的情况下改写 ADC_CR 寄存器中的 ADCAL 和 ADEN 位。软件必 须在 ADC 开启且没有关闭请求挂起(ADEN=1)的情况下改写 ADC_CR 寄存器中的 ADSTART。
>
> 对于以下这些 ADC_IER、ADC_CFGRi、ADC_SMPR、ADC_TR、ADC_CHSELR 和 ADC_CCR 寄存器， 软件必须在 ADC 开启 (ADEN = 1) 且无转换期间 (ADSTART = 0) 的情况下才能进行改写。
>
> 软件必须在 ADC 开启且无挂起请求 (ADSTART = 1) 的情况下改写 ADC_CR 寄存器中的 ADSTP 位。



1. #### ADC初始化

![image-20230426135947096](ADC模块.assets/image-20230426135947096.png) 



2. #### ADC读值

![image-20230426140113487](ADC模块.assets/image-20230426140113487.png) 


