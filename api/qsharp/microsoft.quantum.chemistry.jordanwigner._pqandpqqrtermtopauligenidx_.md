---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _PQandPQQRTermToPauliGenIdx_ 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 17acd2c09129275af90222e30fd96a7551e18b50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203529"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="70d82-102">_PQandPQQRTermToPauliGenIdx_ 函数</span><span class="sxs-lookup"><span data-stu-id="70d82-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="70d82-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="70d82-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="70d82-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="70d82-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="70d82-105">根据 Paulis 将描述 PQ 或 PQQR 字词的 GeneratorIndex 转换为表达式 "GeneratorIndex []"</span><span class="sxs-lookup"><span data-stu-id="70d82-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="70d82-106">输入</span><span class="sxs-lookup"><span data-stu-id="70d82-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="70d82-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="70d82-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="70d82-108">`GeneratorIndex` 表示 PQ 或 PQQR 术语的。</span><span class="sxs-lookup"><span data-stu-id="70d82-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="70d82-109">Output： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="70d82-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="70d82-110">"GeneratorIndex []" 将 PQ 或 PQQR 字词表示为 Pauli 字词。</span><span class="sxs-lookup"><span data-stu-id="70d82-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>