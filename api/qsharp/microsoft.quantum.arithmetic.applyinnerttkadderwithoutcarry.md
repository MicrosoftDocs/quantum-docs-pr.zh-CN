---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 656dc947ab88a7e7f1e8e8722c5262470307f7dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190949"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a>ApplyInnerTTKAdderWithoutCarry 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


为操作 RippleCarryAdderNoCarryTTK 实现内部加法函数。 这是与外部操作 conjugated 的内部操作，用于构造完整的提供程序。

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register 将第一个整数被加数输入编码为 RippleCarryAdderNoCarryTTK。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register 被加数输入的第二个整数。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

指定的受控操作利用操作的对称和相互取消来改善将控件添加到每个操作的默认实现。

## <a name="references"></a>参考

- Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro： "量程加法线路和无限制扇出"、量程信息和计算、2010。
  https://arxiv.org/abs/0910.2530