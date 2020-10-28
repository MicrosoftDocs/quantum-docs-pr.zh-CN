---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 8b0c34915ef392e8a84706f601da71f3848a3134
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699749"
---
# <a name="equalc-function"></a><span data-ttu-id="4e772-102">EqualC 函数</span><span class="sxs-lookup"><span data-stu-id="4e772-102">EqualC function</span></span>

<span data-ttu-id="4e772-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4e772-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4e772-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e772-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e772-105">当且仅当两个输入相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="4e772-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="4e772-106">输入</span><span class="sxs-lookup"><span data-stu-id="4e772-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="4e772-107">答： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="4e772-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="4e772-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="4e772-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="4e772-109">b： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="4e772-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="4e772-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="4e772-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4e772-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="4e772-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4e772-112">`true` 当且仅当 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="4e772-112">`true` if and only if `a` is equal to `b`.</span></span>