---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: eabeb8e068ef32cf6717efd6e818271a667b39b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696584"
---
# <a name="reversedoplea-function"></a>ReversedOpLEA 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


给定一个采用小 endian 输入的操作，将返回采用大字节序输入的新操作。

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a>输入

### <a name="op--littleendian--unit-adj"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词

要反转其输入的操作。



## <a name="output--bigendian--unit-adj"></a>输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词

接受其输入作为大字节序注册的新操作。

## <a name="see-also"></a>另请参阅

- [ApplyReversedOpLEA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [ReversedOpLE。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [ReversedOpLEC。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [ReversedOpLECA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)