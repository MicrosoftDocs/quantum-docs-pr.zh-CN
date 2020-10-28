---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700069"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="67eb5-102">StandardReflectionPhases 函数</span><span class="sxs-lookup"><span data-stu-id="67eb5-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="67eb5-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="67eb5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="67eb5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="67eb5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="67eb5-105">计算标准振幅放大的部分反射阶段。</span><span class="sxs-lookup"><span data-stu-id="67eb5-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="67eb5-106">输入</span><span class="sxs-lookup"><span data-stu-id="67eb5-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="67eb5-107">nIterations： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="67eb5-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="67eb5-108">要为其生成部分反射阶段的波幅放大迭代数。</span><span class="sxs-lookup"><span data-stu-id="67eb5-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="67eb5-109">输出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="67eb5-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="67eb5-110">用于实现指定为部分反射的阶段的操作</span><span class="sxs-lookup"><span data-stu-id="67eb5-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="67eb5-111">注解</span><span class="sxs-lookup"><span data-stu-id="67eb5-111">Remarks</span></span>

<span data-ttu-id="67eb5-112">所有阶段都是 $ \pi $，除了第一次反射（对于开始状态）和最后一次反射（为 $0 $）。</span><span class="sxs-lookup"><span data-stu-id="67eb5-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>