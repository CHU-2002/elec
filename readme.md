#### 1、数据手册

随本文件上传

#### 2、名词解释

##### 、使能

使能是芯片的一个输入引脚，只有当该引脚激活（如置于高电平），整个模块才能正常运行

##### 反馈

使运算器的输出返回其输入端并以某种方式改变输入，正反馈使输出起到与输入相似的过程，使系统偏差不断增大，使系统震荡；负反馈使系统与目标误差减小，系统趋于稳定

##### 肖基特二极管

![img](https://bkimg.cdn.bcebos.com/pic/09fa513d269759eee10202c7b2fb43166d22df68?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U4MA==,g_7,xp_5,yp_5/format,f_auto)

肖特基二极管是贵金属（金、银、铝、铂等）A为正极，以[N型半导体]B为负极，利用二者接触面上形成的势垒具有整流特性而制成的金属-半导体器件。因为N型半导体中存在着大量的电子，贵金属中仅有极少量的自由电子，所以电子便从浓度高的B中向浓度低的A中扩散。显然，金属A中没有空穴，也就不存在空穴自A向B的扩散运动。随着电子不断从B扩散到A，B表面电子浓度逐渐降低，表面电中性被破坏，于是就形成势垒，其电场方向为B→A。但在该电场作用之下，A中的电子也会产生从A→B的漂移运动，从而消弱了由于扩散运动而形成的电场。当建立起一定宽度的[空间电荷区]后，电场引起的电子漂移运动和浓度不同引起的电子扩散运动达到相对的平衡，便形成了[肖特基势垒]

典型的肖特基整流管的内部电路结构是以[N型半导体]为基片，在上面形成用砷作掺杂剂的N-外延层。阳极使用钼或铝等材料制成阻档层。用[二氧化硅]（SiO2）来消除边缘区域的电场，提高管子的耐压值。N型基片具有很小的通态电阻，其掺杂浓度较H-层要高100%倍。在基片下边形成N+[阴极]层，其作用是减小阴极的接触电阻。通过调整结构参数，N型基片和阳极金属之间便形成[肖特基势垒]，如图1所示。当在肖特基势垒两端加上正向偏压（阳极金属接电源正极，N型基片接电源负极）时，肖特基势垒层变窄，其内阻变小；反之，若在肖特基势垒两端加上反向偏压时，肖特基势垒层则变宽，其内阻变大。

采用硅[平面工艺]制造的铝硅肖特基二极管也已问世，这不仅可节省贵金属，大幅度降低成本，还改善了参数的一致性。

##### PN结二极管

*在本征半导体的两个不同区域掺入三价和五价杂质元素*，便形成了P型区和N型区。

**其区别主要在于一个是贵金属与N型半导体形成垒势，另一个是P、N两型半导体形成垒势**

##### PWM

脉宽调制（PWM，Pulse Width Modulation）是利用微处理器的数字输出来对模拟电路进行控制的一种非常有效的技术，广泛应用在从测量、通信到功率控制与变换的许多领域中。

理想的电能变换控制希望变换器的实际输出波形与参考波形完全一致。但在中大功率的应用中，连续的参考波形无法直接转化为输出波形。

脉宽调制（Pulse-width Modulation, PWM）技术通过伏秒平衡，可以实现脉冲波形对连续参考波形进行等效，见《电力电子变换器的先进脉宽调制技术》。

因而随着20世纪中后期电力电子器件的诞生与应用，PWM技术逐渐完善，并成为了电力电子变换中的核心技术。

从功能上而言，变换器可以看做是功率版的**数-模转换**（Digital-Analog, DA）模块，将控制算法计算出的参考波形（数字量）转化为实际的输出电压（模拟量），其功能的实现完全依赖于IGBT等开关器件是否接受了正确的PWM序列。

##### PWM原理

面积等效原理：冲量相等而形状不同的窄脉冲施加在惯性环节上时，其效果基本相同。

通过控制逆变器开关的开通与关断，可以输出窄矩形脉冲；再利用面积等效原理，当 ![[公式]](https://www.zhihu.com/equation?tex=T_s) 较小时，窄矩形脉冲可以逼近正弦波。

为了得到想要的参考正弦波波形，设计矩形脉冲的宽度，利用傅里叶分析与低通滤波器实验正弦波形的输出

#### 引脚功能介绍

1 BST 启动程式 是内部MOSFET启动器的内部浮动高侧电源 通过一个旁路电容与SW引脚连接

2 GND 接地 应该尽可能接近输出电容，避免大电流的开关路径

3 FB 反馈 是误差放大器的输入 一个外部分压电阻连接在输出和GND之间和内部的+0.8V参考来设定调节电压

4 EN 使能输入 参考使能介绍

5 VIN 输入供应 为内部所有控制电路提供电源 接地耦合电容应该接近这个引脚以减少开关峰值

6 SW 开关节点 是高侧开关的输出 低侧VF肖基特二极管接地需要接近该引脚去减少开关峰值

