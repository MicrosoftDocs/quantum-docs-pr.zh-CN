---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695485"
---
# <a name="steanecodeencoderimpl-operation"></a>SteaneCodeEncoderImpl 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

软件包 [](https://nuget.org/packages/)


专用操作，用于实现 Steane 代码编码器和解码器。

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="data--qubit"></a>数据： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

包含1个 qubit 的数组，这是输入 qubit。


### <a name="scratch--qubit"></a>草稿： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

包含6个 qubits 的数组，这会增加冗余性。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

