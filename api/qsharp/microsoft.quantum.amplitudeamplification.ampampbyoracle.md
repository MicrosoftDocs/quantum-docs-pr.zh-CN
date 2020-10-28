---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByOracle
title: AmpAmpByOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByOracle
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByOracle has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification".
ms.openlocfilehash: dbf64a6b310aa5846274b37eabfd0386e0749eaa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696658"
---
# <a name="ampampbyoracle-function"></a><span data-ttu-id="cea03-102">AmpAmpByOracle 函数</span><span class="sxs-lookup"><span data-stu-id="cea03-102">AmpAmpByOracle function</span></span>

<span data-ttu-id="cea03-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="cea03-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="cea03-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cea03-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="cea03-105">AmpAmpByOracle 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="cea03-105">AmpAmpByOracle has been deprecated.</span></span> <span data-ttu-id="cea03-106">请改用 <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification>。</span><span class="sxs-lookup"><span data-stu-id="cea03-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification> instead.</span></span>
>
> <span data-ttu-id="cea03-107">请使用 @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification"。</span><span class="sxs-lookup"><span data-stu-id="cea03-107">Please use @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification".</span></span>



```qsharp
function AmpAmpByOracle (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="cea03-108">输入</span><span class="sxs-lookup"><span data-stu-id="cea03-108">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="cea03-109">nIterations： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cea03-109">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="stateoracle--stateoracle"></a><span data-ttu-id="cea03-110">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="cea03-110">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="cea03-111">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cea03-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="cea03-112">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="cea03-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

