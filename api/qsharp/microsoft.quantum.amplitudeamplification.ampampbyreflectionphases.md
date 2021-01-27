---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByReflectionPhases
title: AmpAmpByReflectionPhases 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByReflectionPhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByReflectionPhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections".
ms.openlocfilehash: 407041deb2c2253c1a2ec6f58ccb696749617577
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843978"
---
# <a name="ampampbyreflectionphases-function"></a><span data-ttu-id="8d623-102">AmpAmpByReflectionPhases 函数</span><span class="sxs-lookup"><span data-stu-id="8d623-102">AmpAmpByReflectionPhases function</span></span>

<span data-ttu-id="8d623-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="8d623-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="8d623-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d623-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="8d623-105">AmpAmpByReflectionPhases 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="8d623-105">AmpAmpByReflectionPhases has been deprecated.</span></span> <span data-ttu-id="8d623-106">请改用 <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections>。</span><span class="sxs-lookup"><span data-stu-id="8d623-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> instead.</span></span>
>
> <span data-ttu-id="8d623-107">请使用 @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections"。</span><span class="sxs-lookup"><span data-stu-id="8d623-107">Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections".</span></span>



```qsharp
function AmpAmpByReflectionPhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="8d623-108">输入</span><span class="sxs-lookup"><span data-stu-id="8d623-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="8d623-109">阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="8d623-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="8d623-110">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="8d623-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="8d623-111">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="8d623-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="8d623-112">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="8d623-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

