---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 3a4872be6b81498c26ab9a14134940c5ef8628b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696583"
---
# <a name="reversedoplec-function"></a>ReversedOpLEC 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


给定一个采用小 endian 输入的操作，将返回采用大字节序输入的新操作。

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a>输入

### <a name="op--littleendian--unit-ctl"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

要反转其输入的操作。



## <a name="output--bigendian--unit-ctl"></a>输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

接受其输入作为大字节序注册的新操作。

## <a name="see-also"></a>另请参阅

- [ApplyReversedOpLEC。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [ReversedOpLE。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [ReversedOpLEA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [ReversedOpLECA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)