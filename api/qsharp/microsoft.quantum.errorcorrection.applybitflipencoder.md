---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695532"
---
# <a name="applybitflipencoder-operation"></a>ApplyBitFlipEncoder 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

软件包 [](https://nuget.org/packages/)


用于实现位翻转编码器和解码器的专用操作。

请注意，此编码器可以利用就地一致恢复，在这种情况下，它将 "导致" 的初始状态描述的错误 `auxQubits` 。
具体而言，如果 `auxQubits` 最初处于状态 $ \ket {10} $，这将导致在编码的 qubit 上出现 $X _1 $ 错误。

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="coherentrecovery--bool"></a>coherentRecovery： [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="data--qubit"></a>数据： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="scratch--qubit"></a>草稿： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>参考

- doi>10.1145： 10.1103/PhysRevA 85.044302