---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 81dd998353f674d55afe85dd20904047391bdb40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699740"
---
# <a name="notequalcp-function"></a><span data-ttu-id="c42ce-102">NotEqualCP 函数</span><span class="sxs-lookup"><span data-stu-id="c42ce-102">NotEqualCP function</span></span>

<span data-ttu-id="c42ce-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c42ce-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c42ce-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c42ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c42ce-105">当且仅当两个输入不相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="c42ce-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="c42ce-106">输入</span><span class="sxs-lookup"><span data-stu-id="c42ce-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="c42ce-107">答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="c42ce-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="c42ce-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="c42ce-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="c42ce-109">b： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="c42ce-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="c42ce-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="c42ce-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c42ce-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="c42ce-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c42ce-112">`true` 当且仅当不 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="c42ce-112">`true` if and only if `a` is not equal to `b`.</span></span>