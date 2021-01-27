---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 83bf5ba245038ad1c7c6ed4e8cdb493317276e6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817163"
---
# <a name="equalcp-function"></a><span data-ttu-id="14911-102">EqualCP 函数</span><span class="sxs-lookup"><span data-stu-id="14911-102">EqualCP function</span></span>

<span data-ttu-id="14911-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="14911-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="14911-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14911-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14911-105">当且仅当两个输入相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="14911-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="14911-106">输入</span><span class="sxs-lookup"><span data-stu-id="14911-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="14911-107">答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="14911-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="14911-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="14911-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="14911-109">b： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="14911-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="14911-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="14911-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="14911-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="14911-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="14911-112">`true` 当且仅当 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="14911-112">`true` if and only if `a` is equal to `b`.</span></span>