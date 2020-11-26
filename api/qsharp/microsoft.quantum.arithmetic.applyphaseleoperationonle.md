---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: adccad53e8d874cb2879d7005711624bbcc69201
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190762"
---
# <a name="applyphaseleoperationonle-operation"></a>ApplyPhaseLEOperationOnLE 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用一个 <xref:microsoft.quantum.arithmetic.littleendian> 在类型为的目标寄存器上采用注册为输入的操作 <xref:microsoft.quantum.arithmetic.phaselittleendian> 。

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>输入

### <a name="op--phaselittleendian--unit"></a>op： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

要应用的操作。


### <a name="target--littleendian"></a>目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要向其应用操作的寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

通过使用将寄存器转换为 `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> ，然后在应用后将其返回到其原始表示形式 `op` 。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyPhaseLEOperationonLEA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Canon. ApplyPhaseLEOperationonLEA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Canon. ApplyPhaseLEOperationonLECA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)