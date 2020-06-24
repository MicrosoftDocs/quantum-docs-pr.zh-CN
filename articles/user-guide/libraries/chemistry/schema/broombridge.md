---
title: Broombridge 量程化学架构
description: Broombridge 量程化学架构概述，用于建模 Microsoft Quantum Development Kit 的实际化学问题。
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: 708c4277080c358cb35a49fbf1dde0394d331043
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274431"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge 量程化学架构 # 

强大的计算化学软件（如[NWChem](http://www.nwchem-sw.org/) ）允许您对各种真实的化学问题进行建模。 若要使用 Microsoft 量程化学库来访问 NWChem 分子模型，请使用名为**Broombridge**的基于[YAML](https://en.wikipedia.org/wiki/YAML)的架构。 此名称被选作了引用，其中某些圆圈中的一个[路标](https://en.wikipedia.org/wiki/Broom_Bridge)Celebrated 为 Hamiltonians 的 birthplace。 

[NWChem](https://github.com/nwchemgit/nwchem)是一个开放源代码项目，根据许可教育社区许可证（ECL）2.0 许可证授权。 [Broombridge 量程化学架构](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)）是一个开源架构，其中包括[RFC 2119](https://tools.ietf.org/html/rfc2119)后面的[定义](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)和在 MIT 许可证下授权的[验证程序脚本](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)。 

Broombridge 是 YAML 的，它是一种用于表示电子结构问题的可人工读取的结构化、可人工阅读的方式。 具体而言，可以表示以下数据：
- Fermionic Hamiltonians 可使用 electron 和双整型表示。
- 使用创建序列可展示地面和兴奋状态。
- 可以指定能源水平的上限和下限。

可以使用各种方法从 NWChem 生成数据，例如，使用完全安装的 NWChem 来运行化学标签（例如，在运行时输出 Broombridge 的[NWChem 库](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)中提供的标签）或 NWChem 的 docker 映像（也可用于从化学卡座生成 Broombridge）。 若要快速开始使用计算化学，无需安装任何化学软件，可以使用[EMSL 箭头](https://arrows.emsl.pnnl.gov/api/qsharp_chem)提供的 NWChem 视觉对象界面。

从较高层次来看，NWChem 与 Microsoft Quantum Development Kit 之间的相互作用可以按如下所示进行可视化： ![ 化学堆栈 ](~/media/broombridge.png) 蓝色阴影框表示 Broombridge 架构，而不同灰色阴影框表示选择的其他内部数据表示形式，这些数据表示法表示和处理基于实际化学问题的计算化学的量程算法。

量程开发工具包示例存储库中的[整数/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)文件夹包含使用 Broombridge 架构定义的多个化学表示形式。
