---
title: Broombridge-量程化学架构
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: c2a7636d0b3f07419e3312e04da5d811229ad854
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185318"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge 量程化学架构 # 

强大的计算化学软件（如[NWChem](http://www.nwchem-sw.org/) ）允许对各种真实的化学问题进行建模。 为了使用 Microsoft 量程化学库访问 NWChem 分子模型，我们使用了一个[YAML](https://en.wikipedia.org/wiki/YAML)的架构，我们称之为**Broombridge**。 此名称被选作了引用，其中某些圆圈中的一个[路标](https://en.wikipedia.org/wiki/Broom_Bridge)Celebrated 为 Hamiltonians 的 birthplace。 

[NWChem](https://github.com/nwchemgit/nwchem)是一个开放源代码项目，根据许可教育社区许可证（ECL）2.0 许可证授权。 Broombridge 是[此处](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)指定的开放源架构，并附带[RFC 2119](https://tools.ietf.org/html/rfc2119)和在 MIT 许可证下许可的[验证程序脚本](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)的[定义](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)。 

Broombridge 是 YAML 的，它是一种用于表示电子结构问题的可人工读取的结构化、可人工阅读的方式。 具体而言，可以表示以下数据： 
- Fermionic Hamiltonians 可使用 electron 和双整型表示。 
- 使用创建序列可展示地面和兴奋状态。
- 可以指定能源水平的上限和下限。

可以轻松地从 NWChem 生成数据格式：可以使用各种方法，这些方法包括从完全安装的 NWChem 到运行化学标签，例如在[此处](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)提供的板，以及在运行时通过 Docker 输出 Broombridge。NWchem 的图像，还可用于从化学卡座生成 Broombridge。 最后，无需安装任何化学软件即可快速开始使用计算化学的可视化方法， [EMSL 箭头](https://arrows.emsl.pnnl.gov/api/qsharp_chem)接口会将其提供给 NWChem。 

从较高层次来看，NWChem 与 Microsoft Quantum Development Kit 之间的相互作用可以按如下所示进行可视化： ![化学堆栈](~/media/broombridge.png) 蓝色阴影框表示 Broombridge 架构，不同灰色阴影框表示其他内部选择用来表示和处理计算化学的量程算法的数据表示形式（基于实际化学问题）。 

[此处](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)提供了使用 Broombridge 架构定义的多个化学表示形式。

