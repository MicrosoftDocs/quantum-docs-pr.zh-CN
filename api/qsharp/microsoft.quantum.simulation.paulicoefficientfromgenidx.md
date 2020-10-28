---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 5bbc8d6113fb36bfd4050b98538bb61bbac02185
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696679"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="f19ed-102">PauliCoefficientFromGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="f19ed-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="f19ed-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f19ed-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f19ed-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f19ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f19ed-105">提取由描述的 Pauli 术语的系数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="f19ed-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="f19ed-106">输入</span><span class="sxs-lookup"><span data-stu-id="f19ed-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="f19ed-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f19ed-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f19ed-108">`GeneratorIndex` 对 Pauli 术语进行编码的类型。</span><span class="sxs-lookup"><span data-stu-id="f19ed-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="f19ed-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f19ed-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f19ed-110">描述的术语的系数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="f19ed-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>