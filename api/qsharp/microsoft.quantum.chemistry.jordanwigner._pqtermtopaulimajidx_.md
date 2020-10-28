---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliMajIdx_
title: _PQTermToPauliMajIdx_ 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b75e9b61e05d6451bab378108c75b10334ac1e44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695791"
---
# <a name="_pqtermtopaulimajidx_-function"></a><span data-ttu-id="dc20c-102">_PQTermToPauliMajIdx_ 函数</span><span class="sxs-lookup"><span data-stu-id="dc20c-102">_PQTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="dc20c-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="dc20c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="dc20c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc20c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc20c-105">将描述 PQ 术语的 GeneratorIndex 转换为表达式 "GeneratorIndex []" （Paulis）</span><span class="sxs-lookup"><span data-stu-id="dc20c-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="dc20c-106">输入</span><span class="sxs-lookup"><span data-stu-id="dc20c-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="dc20c-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="dc20c-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="dc20c-108">`GeneratorIndex` 表示 PQ 术语的。</span><span class="sxs-lookup"><span data-stu-id="dc20c-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="dc20c-109">输出： [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="dc20c-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="dc20c-110">"GeneratorIndex []" 表示 PQ 术语为 Pauli 字词。</span><span class="sxs-lookup"><span data-stu-id="dc20c-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>