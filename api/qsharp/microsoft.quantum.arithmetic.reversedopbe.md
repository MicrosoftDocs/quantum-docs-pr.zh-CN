---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 170f63e60e6c26dbdd33af02c6a3387a1b3dbc44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696594"
---
# <a name="reversedopbe-function"></a>ReversedOpBE 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


给定一个采用大字节序输入的操作，将返回采用小 endian 输入的新操作。

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a>输入

### <a name="op--bigendian--unit"></a>op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

要反转其输入的操作。



## <a name="output--littleendian--unit"></a>输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [单元](xref:microsoft.quantum.lang-ref.unit) 

接受其输入作为小字节序注册的新操作。

## <a name="see-also"></a>另请参阅

- [ApplyReversedOpBE。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [ReversedOpBEA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [ReversedOpBEC。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [ReversedOpBECA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)