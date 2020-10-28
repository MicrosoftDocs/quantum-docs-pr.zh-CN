---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5e9aa6e6dfef74bca004170cf2b1cd91aa13f0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696590"
---
# <a name="reversedopbec-function"></a>ReversedOpBEC 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


给定一个采用大字节序输入的操作，将返回采用小 endian 输入的新操作。

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a>输入

### <a name="op--bigendian--unit-ctl"></a>op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

要反转其输入的操作。



## <a name="output--littleendian--unit-ctl"></a>输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

接受其输入作为小字节序注册的新操作。

## <a name="see-also"></a>另请参阅

- [ApplyReversedOpBEC。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [ReversedOpBE。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [ReversedOpBEA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [ReversedOpBECA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)