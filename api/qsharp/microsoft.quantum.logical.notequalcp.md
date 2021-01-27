---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 85225109a3822a9b63a231631f3d7265143418b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814400"
---
# <a name="notequalcp-function"></a><span data-ttu-id="32ba9-102">NotEqualCP 函数</span><span class="sxs-lookup"><span data-stu-id="32ba9-102">NotEqualCP function</span></span>

<span data-ttu-id="32ba9-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="32ba9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="32ba9-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32ba9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32ba9-105">当且仅当两个输入不相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="32ba9-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="32ba9-106">输入</span><span class="sxs-lookup"><span data-stu-id="32ba9-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="32ba9-107">答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="32ba9-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="32ba9-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="32ba9-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="32ba9-109">b： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="32ba9-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="32ba9-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="32ba9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="32ba9-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="32ba9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32ba9-112">`true` 当且仅当不 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="32ba9-112">`true` if and only if `a` is not equal to `b`.</span></span>