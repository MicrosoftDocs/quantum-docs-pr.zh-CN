---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 644d68affbdb508938f76de5025a1a463e7284e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223079"
---
# <a name="greaterthan-operation"></a>GreaterThan 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对编码到 qubit 寄存器中的两个整数应用大于比较，并根据比较结果翻转目标 qubit。

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

严格大于比较两个整数 $x $ 和 $y $，并以 qubit 寄存器 xs 和 y) 编码。 如果 $x > y $，则会翻转结果 qubit，否则结果 qubit 将保留其状态。

## <a name="input"></a>输入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register $x $ 的第一个整数编码。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register $y $ 的第二个整数编码。


### <a name="result--qubit"></a>result： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

如果 $x > y $，将翻转的单个 qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

使用 $x-y = (x ' + y) "$，其中，表示一个的补码。

## <a name="references"></a>参考

- Steven Cuccaro、Thomas Draper、Samuel Kutin、David Petrie Moulton： "A 新的量程波纹-携带加法线路"，2004。
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas Haener，圣马丁 Roetteler，Krysta Svore： "使用 2n + 2 qubits 和基于 Toffoli 的模块乘法进行因式分解"，2016 https://arxiv.org/abs/1611.07995