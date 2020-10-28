---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 6ebc4e97cb6d515e99e85922d03ca246b56084ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696585"
---
# <a name="reversedople-function"></a>ReversedOpLE 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


给定一个采用小 endian 输入的操作，将返回采用大字节序输入的新操作。

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a>输入

### <a name="op--littleendian--unit"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

要反转其输入的操作。



## <a name="output--bigendian--unit"></a>输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [单元](xref:microsoft.quantum.lang-ref.unit) 

接受其输入作为大字节序注册的新操作。

## <a name="see-also"></a>另请参阅

- [ApplyReversedOpLE。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [ReversedOpLEA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [ReversedOpLEC。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [ReversedOpLECA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)