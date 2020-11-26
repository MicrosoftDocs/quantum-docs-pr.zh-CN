---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: f70d2d1352c7b2eebee7a863eba97d78d7351dab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200843"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>FiveQubitCodeEncoderImpl 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


专用操作，用于实现 5 qubit 编码器和解码器。

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>输入

### <a name="data--qubit"></a>数据： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

包含1个 qubit 的数组，这是输入 qubit。


### <a name="scratch--qubit"></a>草稿： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

一个包含4个 qubits 的数组，其中增加了冗余性。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

选择的特定编码器是从 Kliuchnikov 和 Maslov，"Clifford 电路的优化"，Phys 88，052307 (2013) 中获取的。 https://arxiv.org/abs/1305.0810、图 4b) 和总共需要11个入口。