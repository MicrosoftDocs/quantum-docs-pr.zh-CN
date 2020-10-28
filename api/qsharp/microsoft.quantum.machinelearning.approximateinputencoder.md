---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 67ef7a47a2e036f0953d946b4ace0e6673b173bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696733"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="e0cb7-102">ApproximateInputEncoder 函数</span><span class="sxs-lookup"><span data-stu-id="e0cb7-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="e0cb7-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e0cb7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e0cb7-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0cb7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0cb7-105">给定一组系数和公差后，将返回状态准备操作，以便将每个系数准备为计算基础状态的相应波幅，直到达到给定的公差。</span><span class="sxs-lookup"><span data-stu-id="e0cb7-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="e0cb7-106">输入</span><span class="sxs-lookup"><span data-stu-id="e0cb7-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="e0cb7-107">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e0cb7-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e0cb7-108">将给定系数编码为输入状态时使用的近似容差。</span><span class="sxs-lookup"><span data-stu-id="e0cb7-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="e0cb7-109">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e0cb7-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e0cb7-110">要编码为输入状态的系数。</span><span class="sxs-lookup"><span data-stu-id="e0cb7-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="e0cb7-111">输出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="e0cb7-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="e0cb7-112">准备将给定的系数作为给定寄存器上的输入状态的状态准备操作。</span><span class="sxs-lookup"><span data-stu-id="e0cb7-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>