---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: MultiplexOperationsBruteForceFromGenerator 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 395102c7ffffa81d1a9b6cbf29c9cc22fae6057e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852522"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a>MultiplexOperationsBruteForceFromGenerator 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用 $U $ 的乘法控制的单一操作，该操作将应用单一 $V _j $，由 n qubit number state $ \ket{j} $ 控制。

$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a>unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int) -> t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl) 

一个元组，其中第一个元素 `Int` 是 unitaries $N $ 的数量，第二个元素 `(Int -> ('T => () is Adj + Ctl))` 是在 $ [0，N-1] $ 中采用整数 $j $ 并输出单一运算 $V _j $ 的函数。


### <a name="index--littleendian"></a>index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。


### <a name="target--t"></a>目标： t

泛型 qubit 注册 $V _j $ 作用于。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

`coefficients` 如果指定少于 $ 2 ^ n $，则将用标识元素填充。 此版本通过通过 n 个控制的单一运算符循环直接实现。