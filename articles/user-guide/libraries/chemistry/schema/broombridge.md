---
title: Broombridge 量程化学架构
description: Broombridge 量程化学架构概述，用于建模 Microsoft Quantum Development Kit 的实际化学问题。
author: martinro
ms.author: martinro
ms.date: 10/17/2018
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
no-loc:
- Q#
- $$v
ms.openlocfilehash: e83d2d52fcdb2a30179ca6994d2c90f41cef7dbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856196"
---
# <a name="broombridge-quantum-chemistry-schema"></a><span data-ttu-id="4856f-103">Broombridge 量程化学架构</span><span class="sxs-lookup"><span data-stu-id="4856f-103">Broombridge Quantum Chemistry Schema</span></span> # 

<span data-ttu-id="4856f-104">强大的计算化学软件（如 [NWChem](http://www.nwchem-sw.org/) ）允许您对各种真实的化学问题进行建模。</span><span class="sxs-lookup"><span data-stu-id="4856f-104">Powerful computational chemistry software such as [NWChem](http://www.nwchem-sw.org/) allows you to model a wide range of real-world chemistry problems.</span></span> <span data-ttu-id="4856f-105">若要使用 Microsoft 量程化学库来访问 NWChem 分子模型，请使用名为 **Broombridge** 的基于 [YAML](https://en.wikipedia.org/wiki/YAML)的架构。</span><span class="sxs-lookup"><span data-stu-id="4856f-105">In order to access NWChem molecular models with the Microsoft Quantum Chemistry library, you use a [YAML](https://en.wikipedia.org/wiki/YAML)-based schema named **Broombridge**.</span></span> <span data-ttu-id="4856f-106">此名称被选作了引用，其中某些圆圈中的一个 [路标](https://en.wikipedia.org/wiki/Broom_Bridge) Celebrated 为 Hamiltonians 的 birthplace。</span><span class="sxs-lookup"><span data-stu-id="4856f-106">The name was chosen in reference to a [landmark](https://en.wikipedia.org/wiki/Broom_Bridge) which in some circles is celebrated as a birthplace of Hamiltonians.</span></span> 

<span data-ttu-id="4856f-107">[NWChem](https://github.com/nwchemgit/nwchem) 是一种开放源代码项目，根据许可教育社区许可证 (ECL) 2.0 许可证授权。</span><span class="sxs-lookup"><span data-stu-id="4856f-107">[NWChem](https://github.com/nwchemgit/nwchem) is an Open Source project licensed under the permissive Educational Community License (ECL) 2.0 license.</span></span> <span data-ttu-id="4856f-108">[Broombridge 量程化学架构](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) 是一种开放源架构，其中包含[RFC 2119](https://tools.ietf.org/html/rfc2119)后面的[定义](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)，以及在 MIT 许可证下授权的[验证程序脚本](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)。</span><span class="sxs-lookup"><span data-stu-id="4856f-108">The [Broombridge Quantum Chemistry Schema](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) is an Open Source schema that includes a [definition](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) following [RFC 2119](https://tools.ietf.org/html/rfc2119) and a [validator script](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licensed under the MIT license.</span></span> 

<span data-ttu-id="4856f-109">Broombridge 是 YAML 的，它是一种用于表示电子结构问题的可人工读取的结构化、可人工阅读的方式。</span><span class="sxs-lookup"><span data-stu-id="4856f-109">Being YAML-based, Broombridge is a structured, human-readable and human-editable way of representing electronic structure problems.</span></span> <span data-ttu-id="4856f-110">具体而言，可以表示以下数据：</span><span class="sxs-lookup"><span data-stu-id="4856f-110">In particular, the following data can be represented:</span></span>
- <span data-ttu-id="4856f-111">Fermionic Hamiltonians 可使用 electron 和双整型表示。</span><span class="sxs-lookup"><span data-stu-id="4856f-111">Fermionic Hamiltonians can be represented using one- and two-electron integrals.</span></span>
- <span data-ttu-id="4856f-112">使用创建序列可展示地面和兴奋状态。</span><span class="sxs-lookup"><span data-stu-id="4856f-112">Ground and excited states can be presented using creation sequences.</span></span>
- <span data-ttu-id="4856f-113">可以指定能源水平的上限和下限。</span><span class="sxs-lookup"><span data-stu-id="4856f-113">Upper and lower bounds of energy levels can be specified.</span></span>

<span data-ttu-id="4856f-114">可以使用各种方法从 NWChem 生成数据，例如，使用完全安装的 NWChem 来运行化学标签 (例如，在 [NWChem 库](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) 中提供的，它将 Broombridge 作为 "运行") 的一部分输出，或者也可用于生成 NWChem 的 docker 图像。</span><span class="sxs-lookup"><span data-stu-id="4856f-114">Data can be generated from NWChem using various methods, such as using a full installation of NWChem to run chemistry decks (for example the ones provided in the [NWChem library](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) that output Broombridge as part of the run), or a docker image of NWChem which can also be used to generate Broombridge from chemistry decks.</span></span> <span data-ttu-id="4856f-115">若要快速开始使用计算化学，无需安装任何化学软件，可以使用 [EMSL 箭头](https://arrows.emsl.pnnl.gov/api/qsharp_chem)提供的 NWChem 视觉对象界面。</span><span class="sxs-lookup"><span data-stu-id="4856f-115">To get started with computational chemistry quickly without having to install any chemistry software, you can use the visual interface to NWChem provided by [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span>

<span data-ttu-id="4856f-116">从较高层次来看，NWChem 与 Microsoft Quantum Development Kit 之间的相互作用可以按如下所示进行可视化： ![ 化学堆栈 ](~/media/broombridge.png) 蓝色阴影框表示 Broombridge 架构，而不同灰色阴影框表示选择的其他内部数据表示形式，这些数据表示法表示和处理基于实际化学问题的计算化学的量程算法。</span><span class="sxs-lookup"><span data-stu-id="4856f-116">At a high level, the interplay between NWChem and the Microsoft Quantum Development Kit can be visualized as follows: ![Chemistry stack](~/media/broombridge.png) The blue shaded box represents the Broombridge schema, the various grey shaded boxes represent other internal data representations that were chosen to represent and process quantum algorithms for computational chemistry based on real-world chemistry problems.</span></span>

<span data-ttu-id="4856f-117">量程开发工具包示例存储库中的 [整数/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) 文件夹包含使用 Broombridge 架构定义的多个化学表示形式。</span><span class="sxs-lookup"><span data-stu-id="4856f-117">The [Integral/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains multiple chemical representations defined using the Broombridge schema.</span></span>
