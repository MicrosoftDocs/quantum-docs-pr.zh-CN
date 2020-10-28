---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliGenIdx
title: _ZZTermToPauliGenIdx 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: f8a173e2adb4494a08b48158a010f264562bbaa6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695764"
---
# <a name="_zztermtopauligenidx-function"></a><span data-ttu-id="5675c-102">_ZZTermToPauliGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="5675c-102">_ZZTermToPauliGenIdx function</span></span>

<span data-ttu-id="5675c-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="5675c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="5675c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5675c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5675c-105">根据 Paulis，将描述 ZZ 术语的 GeneratorIndex 转换为表达式 "GeneratorIndex []"。</span><span class="sxs-lookup"><span data-stu-id="5675c-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="5675c-106">输入</span><span class="sxs-lookup"><span data-stu-id="5675c-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="5675c-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="5675c-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="5675c-108">`GeneratorIndex` 表示 ZZ 术语的。</span><span class="sxs-lookup"><span data-stu-id="5675c-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="5675c-109">Output： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="5675c-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="5675c-110">将 ZZ 术语表示为 Pauli 术语的 "GeneratorIndex []"。</span><span class="sxs-lookup"><span data-stu-id="5675c-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>