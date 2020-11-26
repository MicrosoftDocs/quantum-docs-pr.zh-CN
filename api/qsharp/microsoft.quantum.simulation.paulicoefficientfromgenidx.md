---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 59ddadabb5c77cdb0d2e3620a09433992e85f663
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225051"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="de07d-102">PauliCoefficientFromGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="de07d-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="de07d-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="de07d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="de07d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de07d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de07d-105">提取由描述的 Pauli 术语的系数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="de07d-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="de07d-106">输入</span><span class="sxs-lookup"><span data-stu-id="de07d-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="de07d-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="de07d-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="de07d-108">`GeneratorIndex` 对 Pauli 术语进行编码的类型。</span><span class="sxs-lookup"><span data-stu-id="de07d-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="de07d-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="de07d-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="de07d-110">描述的术语的系数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="de07d-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>