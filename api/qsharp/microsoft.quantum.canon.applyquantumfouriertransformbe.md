---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696285"
---
# <a name="applyquantumfouriertransformbe-operation"></a>ApplyQuantumFourierTransformBE 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


对包含大字节序表示形式整数的量程寄存器执行量程傅立叶转换。

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>输入

### <a name="qs--bigendian"></a>qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

量程傅立叶转换应用于的量程寄存器



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

输入和输出假定为大字节序编码。

## <a name="see-also"></a>另请参阅

- [Canon. ApproximateQFT](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)