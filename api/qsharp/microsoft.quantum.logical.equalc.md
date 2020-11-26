---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 4c511489888613d95adaf154c005b3211af75446
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198378"
---
# <a name="equalc-function"></a><span data-ttu-id="34161-102">EqualC 函数</span><span class="sxs-lookup"><span data-stu-id="34161-102">EqualC function</span></span>

<span data-ttu-id="34161-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="34161-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="34161-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34161-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34161-105">当且仅当两个输入相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="34161-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="34161-106">输入</span><span class="sxs-lookup"><span data-stu-id="34161-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="34161-107">答： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="34161-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="34161-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="34161-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="34161-109">b： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="34161-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="34161-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="34161-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="34161-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="34161-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="34161-112">`true` 当且仅当 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="34161-112">`true` if and only if `a` is equal to `b`.</span></span>