---
uid: Microsoft.Quantum.Intrinsic.I
title: 我的操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 0af14a9aff20da493e95c7feba6afbb907d3d69f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849410"
---
# <a name="i-operation"></a><span data-ttu-id="d6214-102">我的操作</span><span class="sxs-lookup"><span data-stu-id="d6214-102">I operation</span></span>

<span data-ttu-id="d6214-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d6214-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d6214-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d6214-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d6214-105">在单个 qubit 上执行不含 op)  (的标识操作。</span><span class="sxs-lookup"><span data-stu-id="d6214-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d6214-106">输入</span><span class="sxs-lookup"><span data-stu-id="d6214-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="d6214-107">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d6214-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="d6214-108">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6214-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d6214-109">备注</span><span class="sxs-lookup"><span data-stu-id="d6214-109">Remarks</span></span>

<span data-ttu-id="d6214-110">这是一个不能操作的。</span><span class="sxs-lookup"><span data-stu-id="d6214-110">This is a no-op.</span></span> <span data-ttu-id="d6214-111">提供此方法是为了提供完整的，因为有时在算法中调用标识或将其作为参数传递是非常有用的。</span><span class="sxs-lookup"><span data-stu-id="d6214-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>