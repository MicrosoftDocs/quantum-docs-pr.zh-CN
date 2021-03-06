---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852273"
---
# <a name="qftle-operation"></a>QFTLE 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对包含小 endian 表示形式整数的量程寄存器执行量程傅立叶转换。

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="qs--littleendian"></a>qs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

量程傅立叶转换应用于的量程寄存器



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

输入和输出假定为 little endian 编码。

## <a name="see-also"></a>另请参阅

- [Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)