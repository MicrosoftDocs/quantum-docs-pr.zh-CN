---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b522691d6826933122e2ebac051b15e35b9902e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695773"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="546dd-102">_V0123TermToPauliGenIdx_ 函数</span><span class="sxs-lookup"><span data-stu-id="546dd-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="546dd-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="546dd-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="546dd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="546dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="546dd-105">将描述 PQRS 术语的 GeneratorIndex 转换为表达式 "GeneratorIndex []" （Paulis）</span><span class="sxs-lookup"><span data-stu-id="546dd-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="546dd-106">输入</span><span class="sxs-lookup"><span data-stu-id="546dd-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="546dd-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="546dd-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="546dd-108">`GeneratorIndex` 表示 PQRS 术语的。</span><span class="sxs-lookup"><span data-stu-id="546dd-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="546dd-109">Output： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="546dd-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="546dd-110">"GeneratorIndex []" 表示 PQRS 术语为 Pauli 字词。</span><span class="sxs-lookup"><span data-stu-id="546dd-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>