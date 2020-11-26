---
uid: Microsoft.Quantum.Simulation._MultiplyGeneratorSystem
title: _MultiplyGeneratorSystem 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 9fdc52bdea69e9507510a51be258eaba8e61f673
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229675"
---
# <a name="_multiplygeneratorsystem-function"></a><span data-ttu-id="e2f62-102">_MultiplyGeneratorSystem 函数</span><span class="sxs-lookup"><span data-stu-id="e2f62-102">_MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="e2f62-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e2f62-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e2f62-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2f62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2f62-105">将中所有字词的系数相乘 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="e2f62-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function _MultiplyGeneratorSystem (multiplier : Double, idxTerm : Int, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="e2f62-106">输入</span><span class="sxs-lookup"><span data-stu-id="e2f62-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="e2f62-107">乘数： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e2f62-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="idxterm--int"></a><span data-ttu-id="e2f62-108">idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e2f62-108">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="e2f62-109">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e2f62-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>





## <a name="output--generatorindex"></a><span data-ttu-id="e2f62-110">输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e2f62-110">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>



## <a name="remarks"></a><span data-ttu-id="e2f62-111">备注</span><span class="sxs-lookup"><span data-stu-id="e2f62-111">Remarks</span></span>

<span data-ttu-id="e2f62-112">这是一个中间步骤，不应调用。</span><span class="sxs-lookup"><span data-stu-id="e2f62-112">This is an intermediate step and should not be called.</span></span>