---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b26ad3515cb801b122858b9474aea76a0e5c498b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695147"
---
# <a name="notequalc-function"></a><span data-ttu-id="35e38-102">NotEqualC 函数</span><span class="sxs-lookup"><span data-stu-id="35e38-102">NotEqualC function</span></span>

<span data-ttu-id="35e38-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="35e38-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="35e38-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35e38-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35e38-105">当且仅当两个输入不相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="35e38-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="35e38-106">输入</span><span class="sxs-lookup"><span data-stu-id="35e38-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="35e38-107">答： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="35e38-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="35e38-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="35e38-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="35e38-109">b： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="35e38-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="35e38-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="35e38-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="35e38-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="35e38-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="35e38-112">`true` 当且仅当不 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="35e38-112">`true` if and only if `a` is not equal to `b`.</span></span>