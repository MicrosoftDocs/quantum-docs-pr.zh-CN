---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: c90eac291ebe718d10377399184ad705bb51673e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824695"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX 函数

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦7，1，3⟧ Steane 量程代码的稳定的 X 部分的解码器。

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>输入

### <a name="syndrome--syndrome"></a>症状： [症状](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

从测量稳定的 X 部分获得的症状数组。



## <a name="output--pauli"></a>Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

一组 Pauli 操作，当应用于已编码的量程系统时，它会更正对应于的错误 `syndrome` 。

## <a name="remarks"></a>备注

所选的解码器使用⟦7，1，3⟧ Steane 代码的 CSS 代码属性，即，它会单独更正 X 错误和 Z 错误。 此代码的一个属性是，X 的位置分别是 x 的分别是 X 的3位编码，这是 X 的3位编码，被视为整数。

## <a name="references"></a>参考

- D. Gottesman、"稳定代码和量程错误纠正" 博士学位 Thesis，Caltech，1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>另请参阅

- [ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [ErrorCorrection. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)