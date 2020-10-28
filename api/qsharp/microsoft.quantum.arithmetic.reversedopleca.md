---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b5413e43ad50ba7252705ef53b21e63650dbb2a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696580"
---
# <a name="reversedopleca-function"></a>ReversedOpLECA 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


给定一个采用小 endian 输入的操作，将返回采用大字节序输入的新操作。

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="op--littleendian--unit-adj--ctl"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl

要反转其输入的操作。



## <a name="output--bigendian--unit-adj--ctl"></a>输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl

接受其输入作为大字节序注册的新操作。

## <a name="see-also"></a>另请参阅

- [ApplyReversedOpLECA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [ReversedOpLE。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [ReversedOpLEA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [ReversedOpLEC。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)