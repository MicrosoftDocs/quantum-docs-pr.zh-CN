---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: cc7922b2940cb979394958d5eb4e9933144eb062
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843152"
---
# <a name="incrementphasebyinteger-operation"></a>IncrementPhaseByInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用阶段旋转，将未签名的量程寄存器增加一个传统整数。

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

假定将 `target` 无符号整数编码 $x $ in 小字节序编码，并且 `increment` 等于 $a $。
然后，此操作实现一个单一 $ \ket{x} \mapsto \ket{x + a} $，其中添加操作执行取模 $ 2 ^ n $，其中 $n = \texttt{Length (target！ ) } $。

## <a name="input"></a>输入

### <a name="increment--int"></a>增量： [Int](xref:microsoft.quantum.lang-ref.int)

的整数，该整数用于 `target` 递增。


### <a name="target--phaselittleendian"></a>目标： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

在双 (QFT) 基础上，量程寄存器使用小字节序编码对无符号整数进行编码。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

请注意，我们已简化了此线路，因为增量为传统常量，而不是量程寄存器。

请参阅 [ arXiv： quant/0008033v1 的第6页 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) 上的图和说明。

## <a name="references"></a>参考

- [*Thomas Draper*，arXiv： quant/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>另请参阅

- [IncrementByInteger。](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)