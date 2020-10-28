---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696006"
---
# <a name="multiplexoperations-operation"></a>MultiplexOperations 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


应用由数值状态数组控制的操作的数组。

也就是说，应用 $U $ 的乘法控制的单一操作，该操作在通过 $n $-qubit number state $ \ket{j} $ 控制时应用单一 $V _j $。

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>输入

### <a name="unitaries--t--unit-adj--ctl"></a>unitaries：不 => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl []

最多 $ 2 ^ n $ 单一操作的数组。 $J $ th 操作由以小字节序格式编码的数字状态 $ \ket{j} $ 进行索引。


### <a name="index--littleendian"></a>index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。


### <a name="target--t"></a>目标： t

泛型 qubit 注册 $V _j $ 作用于。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>注解

`coefficients` 如果指定少于 $ 2 ^ n $，则将用标识元素填充。 此实现使用 $n-$1 辅助 qubits。

## <a name="references"></a>参考

- 对于具有量程加速的第一个量子模拟，Andrew Childs，Dmitri Maslov，Yunseong，Neil，Ross，人民币元 Su https://arxiv.org/abs/1711.10980