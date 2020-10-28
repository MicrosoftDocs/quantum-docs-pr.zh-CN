---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 1f9567f327b5afc3054acbf1a615b44a54453004
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695793"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="a2340-102">_PQTermToPauliGenIdx_ 函数</span><span class="sxs-lookup"><span data-stu-id="a2340-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="a2340-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a2340-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a2340-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2340-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2340-105">将描述 PQ 术语的 GeneratorIndex 转换为表达式 "GeneratorIndex []" （Paulis）</span><span class="sxs-lookup"><span data-stu-id="a2340-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="a2340-106">输入</span><span class="sxs-lookup"><span data-stu-id="a2340-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="a2340-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a2340-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a2340-108">`GeneratorIndex` 表示 PQ 术语的。</span><span class="sxs-lookup"><span data-stu-id="a2340-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="a2340-109">Output： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="a2340-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="a2340-110">"GeneratorIndex []" 表示 PQ 术语为 Pauli 字词。</span><span class="sxs-lookup"><span data-stu-id="a2340-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>