---
layout: post
title: 体系结构论文清单[已读]
date: 2018-07-31
categories:
- tool
tags: [转换器, 云跟帖，disqus]
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  views: '2'
author:
  login: slayer
  email: dongyado@gmail.com
  display_name: slayer
---

体系结构四大顶会：ISCA、HPCA、MICRO、ASPLOS

计算机安全四大顶会：NDSS、SP、Sec、CCS

[Back to the Future Leveraging Belady’s Algorithm for Improved Cache Replacement](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)

&#160; &#160; &#160; &#160;OPT算法是现实不可实现的，Back to the future这篇文章利用cache历史访问信息模拟最优LLC替换算法——OPT+Bypass，如果历史的行为是未来行为的很好的预测器的话，那么我们的算法就能够逼近OPT。

[2017.SGXBOUNDS Memory Safety for Shielded Execution](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)

&#160; &#160; &#160; &#160;SgxBound是为Intel SGX设计的一种BoundChecking策略，其设计思想是tag pointer + compact memory layout（类似于low-fat pointer），指针p的高32位存的是UpperBound，指针p指向的内存部分区域存的是LowerBound.

&#160; &#160; &#160; &#160;SgxBound源码地址[https://github.com/tudinfse/sgxbounds](https://github.com/tudinfse/sgxbounds)


[2009.soft bound Highly Compatibleand Complete Spatial Memory Safety for C](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
  
&#160; &#160; &#160; &#160;SoftBound是一种朴素的BoundChecking实现技术，只在编译过程中的中间表示中插入代码，而不修改源程序.插入的代码包括1.每个指针创建base和bound 2.每次使用指针进行访存操作之前做越界检查的语句，运行时刻的开销主要体现在访问查找表获取base和bound时间上。优点：能对所有的安全漏洞作全面检查，而且不改变源代码，兼容性好；缺点是：开发过程的压力都给了编译，运行时刻的开销也很大。

[2016.CC.Heap Bounds Protection with Low Fat Pointers](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)

&#160; &#160; &#160; &#160;Low-fat pointer的思想解决heap的boundchecking问题。内存结构包括：全局变量0区+M个堆区+1个栈区。编码方式：给定指针p对应的内存地址值，p的高32位决定所在哪个堆区，每个堆区只能动态分配固定大小的size，base同时也要求对齐.

[2018.ISCA-45.3AP3.SEESAW Using Superpages to Improve VIPT Caches](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 多核课第二周的paper2.改进VIPT的Index受限的问题，在4KB的base page引入2MB的超级页（大页），修改了TLB的Memory Hierarchy,TFT作为超级页映射表.

[2018.HPCA-24.2BP2.SIPT Speculatively Indexed, Physically Tagged Caches](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 多核课第二周的paper1.改进VIPT的Index受限的问题，提出增加额外1-3bit index与tag一起做地址翻译，采用感知器做方向预测，类似于BTB的结构做值预测.

[2018.ISCA-45.7BP2.Practical Memory Safety with REST](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- REST(Random Embedded Secret Token)通过软硬件协同的机制在缓冲区的上下插入了随机Token（令牌）.
- Cache Line增加了1 bit的Token标识位，在I1-D与Memory之间增加了一个Token比较器；ISA中通过修改X86指令增加了arm和disarm两条store指令.

[2002.CCured Type-Safe Retrofitting of Legacy Code](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- CCured表示对C语言的治愈，把所有指针分成Safe、Sequence、Dynamic三类，在静态编译和运行时刻对指针所覆盖的内存区域做类型检查.

[1998.StackGuard: Automatic Adaptive Detection and Prevention of Buffer-Overflow Attacks](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- Buffer Overflow Attack(缓冲区溢出攻击)：对栈帧中的返回地址return address作写覆盖，使得返回的地址指向插入的攻击代码attack code.
- StackGuard:1.插入Canary Word(金丝雀)在return时做检查2.MemGuard-对虚拟存储页写保护,禁止对返回地址写；前者是更高效，后者是更安全.

[CHERI(1).2014.ISCA-41.S7BP1.The CHERI capability model Revisiting RISC in an age of risk](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 剑桥大学的一套基于MIPS ISA+fat pointer存储安全系统，增加指令形成CHERI ISA，编译器使用LLVM，OS使用FreeBSD，处理器采用FPGA.
- CHERI ISA和指令级模拟器QEMU-CHERI已在2016年发布.

[CHERI(2).2015.SP.CHERI A Hybrid Capability-System Architecture for Compartmentalization](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 剑桥大学的一套基于MIPS ISA+fat pointer存储安全系统，增加指令形成CHERI ISA，编译器使用LLVM，OS使用FreeBSD，处理器采用FPGA.
- CHERI ISA和指令级模拟器QEMU-CHERI已在2016年发布.

[2012.Baggy Bounds Checking An Efficient and Backwards-Compatible Defense](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 一种高效的越界检查方法——baggy bound checking技术。通过buddy allocator给每个指针分配一个2的整数次幂的大小空间，使得只有1个字节就可以通过指针p索引到bound table并计算出base和size，大大降低了存储指针信息的overhead.

[2016.The Renewed Case for the Reduced Instruction Set Computer](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- RISCV的Macro-fusion技术：RVC + fusion。RISCV在cmp-branch指令上具有明显优势，但在index-load/store比不过x86甚至是ARM.
- 《Tue1130celio-fusion-finalV2》是这篇文章的slice.

[2018.ISCA-45.3AP4.A Case for Richer Cross-layer Abstractions Bridging the Semantic Gap to Enhance Memory Optimization](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 2018一篇ISCA,设计XMem系统(atom模型+Interface接口)实现跨层抽象，弥补应用程序和体系结构/系统之间的语义Gap,在存储优化上得到很大性能提升.

[1996.The Mips R10000 superscalar microprocessor](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 高体课的第1篇论文,MIPS R10000和Aplpha 21264堪称经典,后续RISC系列处理器都以此为原型.

[1992.Alternative implementations of two-level adaptive branch prediction](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 高体课的第2篇论文,两级自适应转移预测器{G,P}A{g,p/s},与当前主流的Gshare作比较.

[1995.Optimal 2-bit branch predictors](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 高体课的第3篇论文,最优(0,2)转移预测器,5248种自动机方案的推导.

