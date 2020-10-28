---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695323"
---
# <a name="mresetz-operation"></a><span data-ttu-id="bb314-102">MResetZ 操作</span><span class="sxs-lookup"><span data-stu-id="bb314-102">MResetZ operation</span></span>

<span data-ttu-id="bb314-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="bb314-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="bb314-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb314-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb314-105">度量 Z 基准中的单个 qubit，并将其重置为固定的初始状态。</span><span class="sxs-lookup"><span data-stu-id="bb314-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="bb314-106">说明</span><span class="sxs-lookup"><span data-stu-id="bb314-106">Description</span></span>

<span data-ttu-id="bb314-107">以 $Z $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。</span><span class="sxs-lookup"><span data-stu-id="bb314-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="bb314-108">输入</span><span class="sxs-lookup"><span data-stu-id="bb314-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="bb314-109">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bb314-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bb314-110">要测量的单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="bb314-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="bb314-111">输出： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="bb314-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="bb314-112">Pauli 中测量的结果 `target` $Z $ basis。</span><span class="sxs-lookup"><span data-stu-id="bb314-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>