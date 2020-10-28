---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696611"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>MultiplyAndAddPhaseByModularInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


与 MultiplyAndAddByModularInteger 相同，但假定被加数将整数编码为 QFT。

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a>输入

### <a name="constmultiplier--int"></a>constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)

要添加到每个基础状态标签的整数 $a $。


### <a name="modulus--int"></a>取模： [Int](xref:microsoft.quantum.lang-ref.int)

取模 $N $，将对执行加法和乘法运算。


### <a name="multiplier--littleendian"></a>乘法器： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

一个量程寄存器，表示其值要添加到的每个基本状态标签的无符号整数 `summand` 。


### <a name="phasesummand--phaselittleendian"></a>phaseSummand： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

一个量程寄存器，表示要用作此操作的目标的无符号整数。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

假定 `phaseSummand` 将最高位设置为0。
还假定的值 `phaseSummand` 小于 $N $。

## <a name="see-also"></a>另请参阅

- [MultiplyAndAddByModularInteger。](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)