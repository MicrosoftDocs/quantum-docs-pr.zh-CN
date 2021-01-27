---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 33049b09405529bd418ff8652b6cb0f11bf734f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849070"
---
# <a name="notequalc-function"></a><span data-ttu-id="fd06f-102">NotEqualC 函数</span><span class="sxs-lookup"><span data-stu-id="fd06f-102">NotEqualC function</span></span>

<span data-ttu-id="fd06f-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fd06f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fd06f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd06f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd06f-105">当且仅当两个输入不相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="fd06f-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="fd06f-106">输入</span><span class="sxs-lookup"><span data-stu-id="fd06f-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="fd06f-107">答： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="fd06f-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="fd06f-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="fd06f-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="fd06f-109">b： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="fd06f-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="fd06f-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="fd06f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fd06f-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="fd06f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fd06f-112">`true` 当且仅当不 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="fd06f-112">`true` if and only if `a` is not equal to `b`.</span></span>