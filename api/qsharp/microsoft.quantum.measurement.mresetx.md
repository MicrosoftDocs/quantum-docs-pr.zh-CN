---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701004"
---
# <a name="mresetx-operation"></a><span data-ttu-id="6762a-102">MResetX 操作</span><span class="sxs-lookup"><span data-stu-id="6762a-102">MResetX operation</span></span>

<span data-ttu-id="6762a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="6762a-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="6762a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6762a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6762a-105">在 X 基础上测量单个 qubit，并将其重置为固定的初始状态。</span><span class="sxs-lookup"><span data-stu-id="6762a-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="6762a-106">说明</span><span class="sxs-lookup"><span data-stu-id="6762a-106">Description</span></span>

<span data-ttu-id="6762a-107">以 $X $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。</span><span class="sxs-lookup"><span data-stu-id="6762a-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="6762a-108">输入</span><span class="sxs-lookup"><span data-stu-id="6762a-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="6762a-109">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6762a-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6762a-110">要测量的单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="6762a-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6762a-111">输出： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="6762a-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6762a-112">Pauli 中测量的结果 `target` $X $ basis。</span><span class="sxs-lookup"><span data-stu-id="6762a-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>