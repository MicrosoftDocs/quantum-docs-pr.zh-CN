---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 04fb0f84ddf79a3d2cfc21fdaabd16c129f6d72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194196"
---
# <a name="mresetx-operation"></a><span data-ttu-id="a17fe-102">MResetX 操作</span><span class="sxs-lookup"><span data-stu-id="a17fe-102">MResetX operation</span></span>

<span data-ttu-id="a17fe-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="a17fe-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="a17fe-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a17fe-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a17fe-105">在 X 基础上测量单个 qubit，并将其重置为固定的初始状态。</span><span class="sxs-lookup"><span data-stu-id="a17fe-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="a17fe-106">描述</span><span class="sxs-lookup"><span data-stu-id="a17fe-106">Description</span></span>

<span data-ttu-id="a17fe-107">以 $X $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。</span><span class="sxs-lookup"><span data-stu-id="a17fe-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="a17fe-108">输入</span><span class="sxs-lookup"><span data-stu-id="a17fe-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="a17fe-109">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a17fe-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a17fe-110">要测量的单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="a17fe-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a17fe-111">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="a17fe-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="a17fe-112">Pauli 中测量的结果 `target` $X $ basis。</span><span class="sxs-lookup"><span data-stu-id="a17fe-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>