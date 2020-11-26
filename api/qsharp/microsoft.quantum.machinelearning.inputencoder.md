---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 019161c0ef6cdec6875518ab58c8159b0f142149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211740"
---
# <a name="inputencoder-function"></a><span data-ttu-id="2b25d-102">InputEncoder 函数</span><span class="sxs-lookup"><span data-stu-id="2b25d-102">InputEncoder function</span></span>

<span data-ttu-id="2b25d-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2b25d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2b25d-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2b25d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2b25d-105">给定一组系数和公差后，将返回状态准备操作，以便将每个系数准备为计算基础状态的相应波幅。</span><span class="sxs-lookup"><span data-stu-id="2b25d-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="2b25d-106">输入</span><span class="sxs-lookup"><span data-stu-id="2b25d-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="2b25d-107">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2b25d-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2b25d-108">要编码为输入状态的系数。</span><span class="sxs-lookup"><span data-stu-id="2b25d-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="2b25d-109">输出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="2b25d-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="2b25d-110">准备将给定的系数作为给定寄存器上的输入状态的状态准备操作。</span><span class="sxs-lookup"><span data-stu-id="2b25d-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>