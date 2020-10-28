---
uid: Microsoft.Quantum.Intrinsic.I
title: 我的操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 555f714047a38f49ccd94a77dc14a46d6f4988ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696648"
---
# <a name="i-operation"></a><span data-ttu-id="90295-102">我的操作</span><span class="sxs-lookup"><span data-stu-id="90295-102">I operation</span></span>

<span data-ttu-id="90295-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="90295-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="90295-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90295-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90295-105">在单个 qubit 上执行不含 op)  (的标识操作。</span><span class="sxs-lookup"><span data-stu-id="90295-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="90295-106">输入</span><span class="sxs-lookup"><span data-stu-id="90295-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="90295-107">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="90295-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="90295-108">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90295-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="90295-109">注解</span><span class="sxs-lookup"><span data-stu-id="90295-109">Remarks</span></span>

<span data-ttu-id="90295-110">这是一个不能操作的。</span><span class="sxs-lookup"><span data-stu-id="90295-110">This is a no-op.</span></span> <span data-ttu-id="90295-111">提供此方法是为了提供完整的，因为有时在算法中调用标识或将其作为参数传递是非常有用的。</span><span class="sxs-lookup"><span data-stu-id="90295-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>