---
title: Broombridge-量程化学架构
description: Broombridge 量程化学架构概述，用于建模 Microsoft Quantum Development Kit 的实际化学问题。
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: a746b63055bb1b2c1168b89993a7459ca9597f86
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907811"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge 量程化学架构 # 

强大的计算化学软件（如[NWChem](http://www.nwchem-sw.org/) ）允许对各种真实的化学问题进行建模。 为了使用 Microsoft 量程化学库访问 NWChem 分子模型，我们使用了一个[YAML](https://en.wikipedia.org/wiki/YAML)的架构，我们称之为**Broombridge**。 此名称被选作了引用，其中某些圆圈中的一个[路标](https://en.wikipedia.org/wiki/Broom_Bridge)Celebrated 为 Hamiltonians 的 birthplace。 

[NWChem](https://github.com/nwchemgit/nwchem)是一个开放源代码项目，根据许可教育社区许可证（ECL）2.0 许可证授权。 Broombridge 是[此处](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)指定的开放源架构，并附带[RFC 2119](https://tools.ietf.org/html/rfc2119)和在 MIT 许可证下许可的[验证程序脚本](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)的[定义](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)。 

Broombridge 是 YAML 的，它是一种用于表示电子结构问题的可人工读取的结构化、可人工阅读的方式。 具体而言，可以表示以下数据： 
- Fermionic Hamiltonians 可使用 electron 和双整型表示。 
- 使用创建序列可展示地面和兴奋状态。
- 可以指定能源水平的上限和下限。

可以轻松地从 NWChem 生成数据格式：可以使用各种方法，这些方法包括完全安装的 NWChem （例如在[此处](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)提供的），并在运行时将 Broombridge 作为运行的一部分输出，通过 NWChem 的 docker 映像，还可用于从化学标签生成 Broombridge。 最后，无需安装任何化学软件即可快速开始使用计算化学的可视化方法， [EMSL 箭头](https://arrows.emsl.pnnl.gov/api/qsharp_chem)接口会将其提供给 NWChem。 

在高级别上，可以按如下所示对 NWChem 和 Microsoft Quantum Development Kit 之间的相互作用进行可视化： ![化学堆栈](~/media/broombridge.png) 蓝色阴影框表示 Broombridge 架构，则各种灰显的框表示选择用于表示和处理计算化学的量程算法的其他内部数据表示形式。 

[此处](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)提供了使用 Broombridge 架构定义的多个化学表示形式。
