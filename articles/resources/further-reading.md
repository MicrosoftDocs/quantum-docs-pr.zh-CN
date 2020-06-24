---
title: 量程计算学习资源 |Microsoft Docs
description: 如果想要详细了解量程计算机编程，请参阅深入了解量程计算主题的参考列表。
author: QuantumWriter
uid: microsoft.quantum.more-information
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: bcc26f66a4ba3e861800ceca122b38b8d3ef6ad5
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274369"
---
# <a name="more-quantum-computing-learning-resources"></a>更多量程计算学习资源

尽管 "[量程计算概念](xref:microsoft.quantum.concepts.intro)" 一节中所述的工具是任何量程软件开发人员的基础，但它们并不是跨越有关量子计算机编程和算法设计的深度或广度。  由于量程计算是一个快速的开发字段，因此没有任何一个资源包含了解如何最好地使用这些工具来解决问题所需的所有信息。  出于此原因，我们已编译一个引用列表，该列表可能会对读者感兴趣的读者了解有关量子计算机编程的详细信息。
本部分包含对量程计算主题深入介绍的选定参考内容。

## <a name="basic-quantum-computing"></a>基本量程计算 ##

+ Nielsen， & 语，I. L。 （2010 年）。 量程计算和量程信息。 量程计算和量程信息，英国：剑桥大学，2010。
+ Kitaev，Shen，A.，& Vyalyi，M. N。 （2002）。 传统计算和量程计算（47）。 提供：美国数学社会。
+ Kaye，Laflamme，Mosca &，M. （2007）。 量程计算简介。 Oxford 大学，按。
+ Rieffel、& Polak、W.x.y.z。 (2011). 量程计算：一种非常简单的介绍。 MIT Press。

## <a name="elementary-techniques-for-building-controlled-gates"></a>用于构建受控入口的基本技术 ##

+ Barenco、A、Bennett、Cleve、DiVincenzo、Margolus、选定、Weinfurter、、P ... &、H. （1995，）.）。 用于量程计算的基本入口。 物理审核 A、52（5）、3457。
+ . （2013）。 容错 Toffoli 入口的低开销构造。 物理审核 A、87（2）、022328

## <a name="techniques-for-preparing-quantum-states"></a>准备量程状态的方法 ##

+ Shende、、Markov、Bullock、&、S。 （2004）。 最小通用双 qubit 控制-不基于的线路。 物理评审 A、69（6）、062321。
+ Ozols，M.，Roetteler，M.，& Roland，J. （2013）。 量程拒绝采样。 计算理论上的未处理事务（TOCT）、5（3）、11。
+ Grover、& Rudolph、T. （2002）。 创建对应于有效 integrable 概率分布的 superpositions。 arXiv preprint quant/0208112。
+ Farhi、Goldstone、Gutmann、、& Sipser、（2000）。 Adiabatic 进化的量程计算。 arXiv preprint quant/0001106。

## <a name="approaches-for-synthesizing-circuits-out-of-h-t-and-cnot-gates"></a>从 H、T 和 CNOT-CONTAINS 入口综合线路的方法 ##

+ Kliuchnikov、Maslov、Mosca &，M. （2013）。 使用固定数量的辅助 qubit，通过 Clifford 和 T 线路 Asymptotically 最佳近似值。 物理审核字母，110（19），190502。
+ Ross，n. & Selinger，P. （2014）。 最佳 ancilla-免费 Clifford + T，z 旋转。 arXiv preprint arXiv:1403.2975.
+ Kliuchnikov，V. （2013）。 将 unitaries 与 Clifford + T 线路合成一起。 arXiv preprint arXiv:1306.3200.
+ Aspuru、Whitfield、McMahon、Yung、Van、米、、Guzik、Yamamoto &、、、、、、、、（2012）。 容错的量程计算机上的量程化学模拟更快。 新日记，物理学，14（11），115023。

## <a name="approaches-for-quantum-arithmetic"></a>量程算法的方法 ##

+ Takahashi、& Kunihiro、N. （2005）。 线性大小的量程线路，无辅助 qubits。 量程信息 & 计算，5（6），440-448。
+ Draper，T. G。 （2000）。 在量程计算机上添加。 arXiv preprint quant/0008033。
+ Soeken，Micheli，Wiebe，，& De，G. （2017，三月）。 设计对量程计算机的自动化和设计空间探索。 在2017设计中，欧洲大会 & 展览（日期） & 测试自动化470-475 （）。 IEEE.

## <a name="methods-for-fast-quantum-sampling-amplitude-amplification-and-probability-estimation"></a>用于快速量程采样的方法（振幅放大）和概率估计 ##

+ Brassard，G.，Hoyer，P.，Mosca，M.，& Tapp，A. （2002）。 量程幅度放大和估算。 现代型数学、305、53-74。
+ Grover、L. K。 （2005）。 定点量程搜索。 物理审阅信函，95（15），150501。
+ Berry、Childs、& Kothari、R. （2015，10月）。 Hamiltonian 模拟，对所有参数的依赖几乎是最佳的。 在计算机科学（FOCS）的基础上，2015 IEEE 56th 年研讨会792-809 （）。 IEEE.

## <a name="algorithms-for-quantum-simulation"></a>量程模拟算法 ##

+ Lloyd，S. （1996）。 通用量程模拟器。 [科学（纽约，纽约州），273（5278），1073](http://doi.org/10.1126/science.273.5278.1073)。
+ Berry、Childs、Cleve、R.、Kothari、R.、& Somma、R. D。 (2015)。 使用截断的 Taylor 系列模拟 Hamiltonian dynamics。 [物理审核字母、114（9）、090502](http://doi.org/10.1103/PhysRevLett.114.090502)。
+ Low、G. & 语，I. L。 (2017)）。 [通过量程信号处理优化 Hamiltonian](https://arxiv.org/abs/1606.02685)。 [物理审阅信函，118（1），010501](http://doi.org/10.1103/PhysRevLett.118.010501)。
+ Low、G. & 语，I. L。 （2016）。 Hamiltonian 通过 qubitization 模拟。 [arXiv preprint： 1610.06546](https://arxiv.org/abs/1610.06546)。
+ Reiher，Wecker，Svore，K.，，d.，& Troyer，，2017）。 量程计算机上的 Elucidating 反应机制。 [美国国家标准学院的诉讼，201619152](http://doi.org/10.1073/pnas.1619152114)。
+ Wiebe、N.、Berry、Sanders、Høyer、P. &，b。 (2011). 模拟量程计算机上的量程。 [物理学 A：数学和理论，44（44），445308](http://doi.org/10.1088/1751-8113/44/44/445308)。
+ Peruzzo，A.，McClean，J.，Shadbolt，P.，Yung，，Zhou，Obrien，，&，J.）。 （2014）。 Photonic 量程处理器上的 variational eigenvalue 求解器。 [性质通信，5](http://doi.org/10.1038/ncomms5213)。

## <a name="procedures-for-quantum-optimization"></a>量程优化过程 ##

+ Durr，c. & Høyer，P. （1996）。 用于查找最小值的量程算法。 arXiv preprint quantph/9607014.
+ Farhi，Goldstone，J & Gutmann，S. （2014）。 量程大致优化算法。 arXiv preprint arXiv:1411.4028.
+ Brandao，Svore，K. M。 (2017)）。 用于 Semidefinite 编程的量程速度。 年度研讨会（FOCS 2017）。
