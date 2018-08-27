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
[2016.The Renewed Case for the Reduced Instruction Set Computer](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- RISCV的Macro-fusion技术：RVC + fusion。RISCV在cmp-branch指令上具有明显优势，但在index-load/store比不过x86甚至是ARM.

[2018.ISCA-45.3AP4.A Case for Richer Cross-layer Abstractions Bridging the Semantic Gap to Enhance Memory Optimization](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 2018一篇ISCA,设计XMem系统(atom模型+Interface接口)实现跨层抽象，弥补应用程序和体系结构/系统之间的语义Gap,在存储优化上得到很大性能提升.

[1996.The Mips R10000 superscalar microprocessor](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 高体课的第1篇论文,MIPS R10000和Aplpha 21264堪称经典,后续RISC系列处理器都以此为原型.

[1992.Alternative implementations of two-level adaptive branch prediction](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 高体课的第2篇论文,两级自适应转移预测器{G,P}A{g,p/s},与当前主流的Gshare作比较.

[1995.Optimal 2-bit branch predictors](https://github.com/Hacker-vision/Tutorials/tree/master/1-paper)
- 高体课的第3篇论文,最优(0,2)转移预测器,5248种自动机方案的推导.

