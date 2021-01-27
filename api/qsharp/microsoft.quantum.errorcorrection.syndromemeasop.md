---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850054"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="0abc9-102">SyndromeMeasOp 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="0abc9-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="0abc9-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0abc9-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0abc9-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0abc9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0abc9-105">表示一个操作，该操作用于测量纠错代码块的症状。</span><span class="sxs-lookup"><span data-stu-id="0abc9-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="0abc9-106">示例</span><span class="sxs-lookup"><span data-stu-id="0abc9-106">Example</span></span>

<span data-ttu-id="0abc9-107">Syndromes = \langle ZZI，使用草稿 \rangle 度量位翻转 $S 代码的 =，IZZ qubits $：</span><span class="sxs-lookup"><span data-stu-id="0abc9-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="0abc9-108">备注</span><span class="sxs-lookup"><span data-stu-id="0abc9-108">Remarks</span></span>

<span data-ttu-id="0abc9-109">签名 `(LogicalRegister => Syndrome)` 表示一项操作，该操作与中的 qubits 联合 `LogicalRegister` ，一些辅助 qubits 后跟辅助 qubits 的度量，以提取 `Syndrome` 表示这些度量值的值 `Result[]` 。</span><span class="sxs-lookup"><span data-stu-id="0abc9-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="0abc9-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0abc9-110">See Also</span></span>

- [<span data-ttu-id="0abc9-111">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="0abc9-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="0abc9-112">ErrorCorrection。</span><span class="sxs-lookup"><span data-stu-id="0abc9-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)