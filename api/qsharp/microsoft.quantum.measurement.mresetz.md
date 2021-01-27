---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853741"
---
# <a name="mresetz-operation"></a><span data-ttu-id="0ffc8-102">MResetZ 操作</span><span class="sxs-lookup"><span data-stu-id="0ffc8-102">MResetZ operation</span></span>

<span data-ttu-id="0ffc8-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="0ffc8-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="0ffc8-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0ffc8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0ffc8-105">度量 Z 基准中的单个 qubit，并将其重置为固定的初始状态。</span><span class="sxs-lookup"><span data-stu-id="0ffc8-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="0ffc8-106">说明</span><span class="sxs-lookup"><span data-stu-id="0ffc8-106">Description</span></span>

<span data-ttu-id="0ffc8-107">以 $Z $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。</span><span class="sxs-lookup"><span data-stu-id="0ffc8-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="0ffc8-108">输入</span><span class="sxs-lookup"><span data-stu-id="0ffc8-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="0ffc8-109">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0ffc8-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0ffc8-110">要测量的单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="0ffc8-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="0ffc8-111">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="0ffc8-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="0ffc8-112">Pauli 中测量的结果 `target` $Z $ basis。</span><span class="sxs-lookup"><span data-stu-id="0ffc8-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>