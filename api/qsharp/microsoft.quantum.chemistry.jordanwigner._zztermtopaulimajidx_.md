---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliMajIdx_
title: _ZZTermToPauliMajIdx_ 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 8c9223d54585f91e1616021bf0643e558d57589c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695762"
---
# <a name="_zztermtopaulimajidx_-function"></a><span data-ttu-id="e5620-102">_ZZTermToPauliMajIdx_ 函数</span><span class="sxs-lookup"><span data-stu-id="e5620-102">_ZZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="e5620-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e5620-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e5620-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5620-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5620-105">根据 Paulis，将描述 ZZ 术语的 GeneratorIndex 转换为表达式 "GeneratorIndex []"。</span><span class="sxs-lookup"><span data-stu-id="e5620-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="e5620-106">输入</span><span class="sxs-lookup"><span data-stu-id="e5620-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="e5620-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e5620-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e5620-108">`GeneratorIndex` 表示 ZZ 术语的。</span><span class="sxs-lookup"><span data-stu-id="e5620-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="e5620-109">输出： [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="e5620-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="e5620-110">将 ZZ 术语表示为 Pauli 术语的 "GeneratorIndex []"。</span><span class="sxs-lookup"><span data-stu-id="e5620-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>