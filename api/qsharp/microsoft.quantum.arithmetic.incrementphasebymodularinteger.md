---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 4ba35010d56ad01c73cb563646dc8150842da12e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846575"
---
# <a name="incrementphasebymodularinteger-operation"></a>IncrementPhaseByModularInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


按整数常量执行 qubit 寄存器的模块化增量。

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

通过 `increment` `modulus` $y $ $N $ 和在中编码的整数，让我们以 $a $ 表示。 `target`
然后，该操作将执行以下转换： \begin{align} \ket{y} \mapsto \ket{ (y + a) \operatorname{mod} N} \end{align} 将以小字节序格式编码。

## <a name="input"></a>输入

### <a name="increment--int"></a>增量： [Int](xref:microsoft.quantum.lang-ref.int)

要添加到 $y $ $a $ 的整数增量。


### <a name="modulus--int"></a>取模： [Int](xref:microsoft.quantum.lang-ref.int)

整数 $N $ mods $y + a $。


### <a name="target--phaselittleendian"></a>目标： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

$A $ 添加到的、阶段编码的小字节序格式的整数 $y $ `increment` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

假定 `target` 将最高位设置为0。
还假定目标值小于 $N $。

对于 "线路" 关系图和说明，请参阅 [arXiv： quant/0205095V3 第5页](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5)上的图5。

## <a name="see-also"></a>另请参阅

- [IncrementByModularInteger。](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)