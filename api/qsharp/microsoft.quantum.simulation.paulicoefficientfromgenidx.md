---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: eb4f7a538e85ade4b095aa3ea5eab4448eda2491
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847997"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="27179-102">PauliCoefficientFromGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="27179-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="27179-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="27179-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="27179-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27179-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27179-105">提取由描述的 Pauli 术语的系数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="27179-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="27179-106">输入</span><span class="sxs-lookup"><span data-stu-id="27179-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="27179-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="27179-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="27179-108">`GeneratorIndex` 对 Pauli 术语进行编码的类型。</span><span class="sxs-lookup"><span data-stu-id="27179-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="27179-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27179-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27179-110">描述的术语的系数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="27179-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>