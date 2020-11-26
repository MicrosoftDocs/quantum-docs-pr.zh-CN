---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 7088397bd60e2779ef60afc1bb7108d937a62c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195760"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="73905-102">ArgComplexPolar 函数</span><span class="sxs-lookup"><span data-stu-id="73905-102">ArgComplexPolar function</span></span>

<span data-ttu-id="73905-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="73905-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="73905-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73905-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73905-105">返回类型为的复数的相位 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="73905-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="73905-106">输入</span><span class="sxs-lookup"><span data-stu-id="73905-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="73905-107">输入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="73905-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="73905-108">复数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="73905-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="73905-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73905-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="73905-110">阶段 $ \text{Arg} [c] = t $。</span><span class="sxs-lookup"><span data-stu-id="73905-110">Phase $\text{Arg}[c] = t$.</span></span>