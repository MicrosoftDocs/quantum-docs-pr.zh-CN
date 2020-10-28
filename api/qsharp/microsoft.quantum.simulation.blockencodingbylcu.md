---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700964"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


将感兴趣的运算符编码为 `BlockEncoding` 。

这将构造一个 `BlockEncoding` 单一 $U = P\cdot V\cdot P ^ \dagger $，用于对一些运算符进行编码 $H = \ sum_ {j} | \ alpha_j |U_j 是 unitaries 的线性组合。 通常，$P $ 是一种状态准备，因此 $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ $，$V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $。

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

准备某些目标状态的单一 $P $。


### <a name="selector--ts--unit-adj--ctl"></a>选择器： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

一个单一 $V $，它对 $H $ 的组件 unitaries 进行编码。



## <a name="output--ts--unit-adj--ctl"></a>输出： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

单一 $U $ 对寄存器进行操作并对其 `a` `s` 进行块编码 $H $，并满足 $U ^ \Dagger = U $。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="s"></a>我们



## <a name="remarks"></a>注解

此 `BlockEncoding` 实现为它提供了的属性 `BlockEncodingReflection` 。

## <a name="see-also"></a>另请参阅

- [BlockEncoding。](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)