---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227023"
---
# <a name="mresety-operation"></a><span data-ttu-id="64177-102">MResetY 操作</span><span class="sxs-lookup"><span data-stu-id="64177-102">MResetY operation</span></span>

<span data-ttu-id="64177-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="64177-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="64177-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="64177-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="64177-105">按 Y 度量单个 qubit，并将其重置为测量后的固定初始状态。</span><span class="sxs-lookup"><span data-stu-id="64177-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="64177-106">描述</span><span class="sxs-lookup"><span data-stu-id="64177-106">Description</span></span>

<span data-ttu-id="64177-107">以 $Y $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。</span><span class="sxs-lookup"><span data-stu-id="64177-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="64177-108">输入</span><span class="sxs-lookup"><span data-stu-id="64177-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="64177-109">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="64177-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="64177-110">要测量的单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="64177-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="64177-111">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="64177-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="64177-112">Pauli 中测量的结果 `target` $Y $ basis。</span><span class="sxs-lookup"><span data-stu-id="64177-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>