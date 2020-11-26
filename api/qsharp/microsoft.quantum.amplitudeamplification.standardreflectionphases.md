---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 316c8f22a16859ebb439824eda9a5aa02c750b5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191119"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="32d14-102">StandardReflectionPhases 函数</span><span class="sxs-lookup"><span data-stu-id="32d14-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="32d14-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="32d14-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="32d14-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32d14-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32d14-105">计算标准振幅放大的部分反射阶段。</span><span class="sxs-lookup"><span data-stu-id="32d14-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="32d14-106">输入</span><span class="sxs-lookup"><span data-stu-id="32d14-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="32d14-107">nIterations： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32d14-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="32d14-108">要为其生成部分反射阶段的波幅放大迭代数。</span><span class="sxs-lookup"><span data-stu-id="32d14-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="32d14-109">输出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="32d14-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="32d14-110">用于实现指定为部分反射的阶段的操作</span><span class="sxs-lookup"><span data-stu-id="32d14-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="32d14-111">备注</span><span class="sxs-lookup"><span data-stu-id="32d14-111">Remarks</span></span>

<span data-ttu-id="32d14-112">所有阶段都是 $ \pi $，除了第一次反射（对于开始状态）和最后一次反射（为 $0 $）。</span><span class="sxs-lookup"><span data-stu-id="32d14-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>