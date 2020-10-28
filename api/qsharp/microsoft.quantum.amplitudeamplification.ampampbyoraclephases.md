---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByOraclePhases
title: AmpAmpByOraclePhases 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByOraclePhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByOraclePhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation".
ms.openlocfilehash: e45b6b0fdb3aa9a9c0a934e09e1aabd4ea42e0cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696657"
---
# <a name="ampampbyoraclephases-function"></a><span data-ttu-id="64585-102">AmpAmpByOraclePhases 函数</span><span class="sxs-lookup"><span data-stu-id="64585-102">AmpAmpByOraclePhases function</span></span>

<span data-ttu-id="64585-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="64585-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="64585-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64585-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="64585-105">AmpAmpByOraclePhases 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="64585-105">AmpAmpByOraclePhases has been deprecated.</span></span> <span data-ttu-id="64585-106">请改用 <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation>。</span><span class="sxs-lookup"><span data-stu-id="64585-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> instead.</span></span>
>
> <span data-ttu-id="64585-107">请使用 @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation"。</span><span class="sxs-lookup"><span data-stu-id="64585-107">Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation".</span></span>



```qsharp
function AmpAmpByOraclePhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="64585-108">输入</span><span class="sxs-lookup"><span data-stu-id="64585-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="64585-109">阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="64585-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="stateoracle--stateoracle"></a><span data-ttu-id="64585-110">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="64585-110">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="64585-111">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="64585-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="64585-112">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="64585-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

