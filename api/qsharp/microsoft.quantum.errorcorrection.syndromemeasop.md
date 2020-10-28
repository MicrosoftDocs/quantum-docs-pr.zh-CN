---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695475"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="c59e8-102">SyndromeMeasOp 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="c59e8-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="c59e8-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c59e8-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c59e8-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c59e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c59e8-105">表示一个操作，该操作用于测量纠错代码块的症状。</span><span class="sxs-lookup"><span data-stu-id="c59e8-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="c59e8-106">注解</span><span class="sxs-lookup"><span data-stu-id="c59e8-106">Remarks</span></span>

<span data-ttu-id="c59e8-107">签名 `(LogicalRegister => Syndrome)` 表示一项操作，该操作与中的 qubits 联合 `LogicalRegister` ，一些辅助 qubits 后跟辅助 qubits 的度量，以提取 `Syndrome` 表示这些度量值的值 `Result[]` 。</span><span class="sxs-lookup"><span data-stu-id="c59e8-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="c59e8-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c59e8-108">See Also</span></span>

- [<span data-ttu-id="c59e8-109">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="c59e8-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="c59e8-110">ErrorCorrection。</span><span class="sxs-lookup"><span data-stu-id="c59e8-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)