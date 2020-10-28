---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: _ZTermToPauliGenIdx 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 1569ec742778549b8754cdca8b2d9872310e8976
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695769"
---
# <a name="_ztermtopauligenidx-function"></a><span data-ttu-id="41a60-102">_ZTermToPauliGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="41a60-102">_ZTermToPauliGenIdx function</span></span>

<span data-ttu-id="41a60-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="41a60-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="41a60-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41a60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41a60-105">根据 Paulis，将描述 Z 术语的 GeneratorIndex 转换为表达式 "GeneratorIndex []"。</span><span class="sxs-lookup"><span data-stu-id="41a60-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="41a60-106">输入</span><span class="sxs-lookup"><span data-stu-id="41a60-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="41a60-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="41a60-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="41a60-108">`GeneratorIndex` 表示 Z 术语的。</span><span class="sxs-lookup"><span data-stu-id="41a60-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="41a60-109">Output： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="41a60-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="41a60-110">"GeneratorIndex []" 将 Z 术语表示为 Pauli 术语。</span><span class="sxs-lookup"><span data-stu-id="41a60-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>