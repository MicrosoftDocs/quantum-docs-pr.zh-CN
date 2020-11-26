---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpObliviousByOraclePhases
title: AmpAmpObliviousByOraclePhases 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpObliviousByOraclePhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpObliviousByOraclePhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfromstatepreparation".
ms.openlocfilehash: 70e31e5ed020babefe78227a666b6c464bddaa1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191748"
---
# <a name="ampampobliviousbyoraclephases-function"></a>AmpAmpObliviousByOraclePhases 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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





## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

