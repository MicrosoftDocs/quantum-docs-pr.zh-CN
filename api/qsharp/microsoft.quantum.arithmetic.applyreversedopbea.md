---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: ApplyReversedOpBEA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1759764947cdbd84a1db945296d441a13f13767e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843587"
---
# <a name="applyreversedopbea-operation"></a>ApplyReversedOpBEA 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用小 endian 格式将使用大字节序输入的操作应用到寄存器编码的无符号整数。

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj
```


## <a name="input"></a>输入

### <a name="op--bigendian--unit--is-adj"></a>op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  为形容词

作用于大字节序注册的操作。


### <a name="register--littleendian"></a>register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要转换的小 endian 寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [ApplyReversedOpBE。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [ApplyReversedOpBEC。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [ApplyReversedOpBECA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)