---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliMajIdx_
title: _PQandPQQRTermToPauliMajIdx_ 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 4ba13f42064d9311ffb29dbd9363aa3be978e702
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695796"
---
# <a name="_pqandpqqrtermtopaulimajidx_-function"></a><span data-ttu-id="a4227-102">_PQandPQQRTermToPauliMajIdx_ 函数</span><span class="sxs-lookup"><span data-stu-id="a4227-102">_PQandPQQRTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="a4227-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a4227-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a4227-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4227-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4227-105">根据 Paulis 将描述 PQ 或 PQQR 字词的 GeneratorIndex 转换为表达式 "GeneratorIndex []"</span><span class="sxs-lookup"><span data-stu-id="a4227-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="a4227-106">输入</span><span class="sxs-lookup"><span data-stu-id="a4227-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="a4227-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a4227-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a4227-108">`GeneratorIndex` 表示 PQ 或 PQQR 术语的。</span><span class="sxs-lookup"><span data-stu-id="a4227-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="a4227-109">输出： [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="a4227-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="a4227-110">"GeneratorIndex []" 将 PQ 或 PQQR 字词表示为 Pauli 字词。</span><span class="sxs-lookup"><span data-stu-id="a4227-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>