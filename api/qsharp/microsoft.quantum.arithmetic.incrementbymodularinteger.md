---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 8a02d22facce8f58180752b6d063ac55d75ca537
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222943"
---
# <a name="incrementbymodularinteger-operation"></a>IncrementByModularInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


按整数常量执行 qubit 寄存器的模块化增量。

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

通过 `increment` `modulus` $y $ $N $ 和在中编码的整数，让我们以 $a $ 表示。 `target`
然后，操作执行以下转换： \begin{align} \ket{y} \mapsto \ket{ (y + a) \operatorname{mod} N} \end{align} 整数以小 endian 格式编码。

## <a name="input"></a>输入

### <a name="increment--int"></a>增量： [Int](xref:microsoft.quantum.lang-ref.int)

要添加到 $y $ $a $ 的整数增量。


### <a name="modulus--int"></a>取模： [Int](xref:microsoft.quantum.lang-ref.int)

整数 $N $ mods $y + a $。


### <a name="target--littleendian"></a>目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

`LittleEndian`$A $ 添加到的格式中的整数 $y $ `increment` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

假定目标的初始值小于 $N $，并且 $a $ $N 增量小于 $。
请注意， <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> 在基础上实现相同的操作 `PhaseLittleEndian` 。

## <a name="see-also"></a>另请参阅

- [IncrementPhaseByModularInteger。](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)