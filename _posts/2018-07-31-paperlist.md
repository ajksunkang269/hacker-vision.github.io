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

