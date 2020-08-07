---
title: 量子化学示例应用程序
description: 了解 Microsoft 量子化学库的示例应用程序。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: a0bc79c7fb41069ee7865dbf2f1cfd7851fda32d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869284"
---
# <a name="quantum-chemistry-examples"></a>量子化学示例

在量子化学概念中，我们手动构造了示例 Hamiltonian 费米子。 现将[模拟 Hamiltonian 动力学](xref:microsoft.quantum.libraries.standard.algorithms)中概述的化学模拟算法与 canon 库中的[量子相位估计](xref:microsoft.quantum.libraries.characterization)结合起来。 通过这种结合，我们能够获取所表示的分子中的能级估计值，这是量子化学在量子计算机上的关键应用之一。 

我们还研究了一些可以实现大规模量子化学实验的示例，但没有逐个指定 Hamiltonian 的术语。 我们首先研究用于加载以 [Broombridge 架构](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)编码的化学 Hamiltonian。

对于因太大而无法在[完全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)上进行模拟的分子，仍可执行有趣的科学研究。 例如，通过将[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)设为目标，仍可以评估执行大型化学模拟的资源成本。

现在，让我们通过几个提供的示例解释化学模拟库的有趣应用。
