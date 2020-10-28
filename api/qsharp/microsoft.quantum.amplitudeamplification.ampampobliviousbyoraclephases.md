---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpObliviousByOraclePhases
title: AmpAmpObliviousByOraclePhases 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpObliviousByOraclePhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpObliviousByOraclePhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfromstatepreparation".
ms.openlocfilehash: eb1b03b26848eada800ead999804c214d7f09ef8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696653"
---
# <a name="ampampobliviousbyoraclephases-function"></a>AmpAmpObliviousByOraclePhases 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

软件包 [](https://nuget.org/packages/)


> [!WARNING]
> AmpAmpObliviousByOraclePhases 已被弃用。 请改用 <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation>。
>
> 请使用 @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfromstatepreparation"。



```qsharp
function AmpAmpObliviousByOraclePhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="phases--reflectionphases"></a>阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)




### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)




### <a name="signaloracle--obliviousoracle"></a>signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)




### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--qubitqubit--unit-adj--ctl"></a>Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

