---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 18228d45c4df280b004c595a7b0f1e2a607b8b2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700073"
---
# <a name="standardamplitudeamplification-function"></a>StandardAmplitudeAmplification 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

软件包 [](https://nuget.org/packages/)


标准振幅放大算法

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="niterations--int"></a>nIterations： [Int](xref:microsoft.quantum.lang-ref.int)

$n $ 的幅度放大次数的迭代数


### <a name="stateoracle--stateoracle"></a>stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

准备开始状态的单一 oracle $A $


### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

用于标记 qubit 的索引



## <a name="output--qubit--unit-adj--ctl"></a>Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

实现标准振幅放大量程算法的操作

## <a name="remarks"></a>注解

这是由所选的反射阶段所获得的标准幅度放大算法，通过 `AmpAmpPhasesStandard` 假定 \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\End{align} 此操作 {0} \_ 在大多数情况下准备状态 \begin{align} \operatorname{AmpAmpByOracle}\ket {f} \ket {0} \_ s = \Sin ( # B1 2n + 1) \sin ^ {-1} ( \lambda) # A5\ket {1} \_ f\ket {\ text {target}} \_ s + \cdots\ket {0} \_ f \end{align} `flagQubit` `auxiliaryRegister` {0} \_ {0} \_

## <a name="references"></a>参考

- [*G. Brassard，Hoyer，Mosca，Tapp*](https://arxiv.org/abs/quant-ph/0005055)