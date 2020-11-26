---
uid: Microsoft.Quantum.Math.AbsSquaredComplexPolar
title: AbsSquaredComplexPolar 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsSquaredComplexPolar
qsharp.summary: Returns the squared absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 51ec302d5120b2af58c00fc20c5c8cf739f189b1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211281"
---
# <a name="abssquaredcomplexpolar-function"></a><span data-ttu-id="166cc-102">AbsSquaredComplexPolar 函数</span><span class="sxs-lookup"><span data-stu-id="166cc-102">AbsSquaredComplexPolar function</span></span>

<span data-ttu-id="166cc-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="166cc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="166cc-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="166cc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="166cc-105">返回类型的复数的平方绝对值 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="166cc-105">Returns the squared absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsSquaredComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="166cc-106">输入</span><span class="sxs-lookup"><span data-stu-id="166cc-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="166cc-107">输入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="166cc-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="166cc-108">复数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="166cc-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="166cc-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="166cc-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="166cc-110">平方绝对值 $ | c | ^ 2 = r ^ 2 $。</span><span class="sxs-lookup"><span data-stu-id="166cc-110">Squared absolute value $|c|^2 = r^2$.</span></span>