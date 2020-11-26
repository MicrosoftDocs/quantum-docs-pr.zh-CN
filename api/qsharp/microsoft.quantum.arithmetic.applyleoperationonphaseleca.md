---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLECA
title: ApplyLEOperationOnPhaseLECA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLECA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 4762eb17b4c11e46b5b94498b7fc8fd2f855c659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190677"
---
# <a name="applyleoperationonphaseleca-operation"></a>ApplyLEOperationOnPhaseLECA 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用一个 <xref:microsoft.quantum.arithmetic.phaselittleendian> 在类型为的目标寄存器上采用注册为输入的操作 <xref:microsoft.quantum.arithmetic.littleendian> 。

```qsharp
operation ApplyLEOperationOnPhaseLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="op--littleendian--unit--is-adj--ctl"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

要应用的操作。


### <a name="target--phaselittleendian"></a>目标： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

要向其应用操作的寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

通过使用将寄存器转换为 `LittleEndian` <xref:microsoft.quantum.canon.qftle> ，然后在应用后将其返回到其原始表示形式 `op` 。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyLEOperationonPhaseLE](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [Canon. ApplyLEOperationonPhaseLEA](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [Canon. ApplyLEOperationonPhaseLEC](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)