---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: 81abe75e2a315fe9a994147242f3c8c9bde586ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824719"
---
# <a name="steanecodeencoderimpl-operation"></a>SteaneCodeEncoderImpl 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


专用操作，用于实现 Steane 代码编码器和解码器。

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>输入

### <a name="data--qubit"></a>数据： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

包含1个 qubit 的数组，这是输入 qubit。


### <a name="scratch--qubit"></a>草稿： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

包含6个 qubits 的数组，这会增加冗余性。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

