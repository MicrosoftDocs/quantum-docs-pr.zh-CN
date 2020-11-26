---
uid: Microsoft.Quantum.Simulation.IdxToCoeff
title: IdxToCoeff 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToCoeff
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: 4e10b61e56b791a39841385ec79893c1392b9563
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225119"
---
# <a name="idxtocoeff-function"></a><span data-ttu-id="4c498-102">IdxToCoeff 函数</span><span class="sxs-lookup"><span data-stu-id="4c498-102">IdxToCoeff function</span></span>

<span data-ttu-id="4c498-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4c498-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4c498-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4c498-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4c498-105">用于实现 `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="4c498-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToCoeff (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToCoeff : (Microsoft.Quantum.Simulation.GeneratorIndex -> Double)) : Double
```


## <a name="input"></a><span data-ttu-id="4c498-106">输入</span><span class="sxs-lookup"><span data-stu-id="4c498-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="4c498-107">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c498-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="4c498-108">genFun： [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4c498-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtocoeff--generatorindex---double"></a><span data-ttu-id="4c498-109">genIdxToCoeff： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4c498-109">genIdxToCoeff : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="4c498-110">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4c498-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="see-also"></a><span data-ttu-id="4c498-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c498-111">See Also</span></span>

- [<span data-ttu-id="4c498-112">PauliBlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="4c498-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)