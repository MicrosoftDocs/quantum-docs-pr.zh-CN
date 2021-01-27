---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854636"
---
# <a name="mresety-operation"></a><span data-ttu-id="a449f-102">MResetY 操作</span><span class="sxs-lookup"><span data-stu-id="a449f-102">MResetY operation</span></span>

<span data-ttu-id="a449f-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="a449f-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="a449f-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a449f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a449f-105">按 Y 度量单个 qubit，并将其重置为测量后的固定初始状态。</span><span class="sxs-lookup"><span data-stu-id="a449f-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="a449f-106">说明</span><span class="sxs-lookup"><span data-stu-id="a449f-106">Description</span></span>

<span data-ttu-id="a449f-107">以 $Y $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。</span><span class="sxs-lookup"><span data-stu-id="a449f-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="a449f-108">输入</span><span class="sxs-lookup"><span data-stu-id="a449f-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="a449f-109">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a449f-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a449f-110">要测量的单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="a449f-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a449f-111">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="a449f-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="a449f-112">Pauli 中测量的结果 `target` $Y $ basis。</span><span class="sxs-lookup"><span data-stu-id="a449f-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>