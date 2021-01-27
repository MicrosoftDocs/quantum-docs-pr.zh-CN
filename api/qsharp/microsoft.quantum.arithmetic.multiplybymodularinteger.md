---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846493"
---
# <a name="multiplybymodularinteger-operation"></a>MultiplyByModularInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对 qubit 寄存器上的整数常量执行模块化乘法运算。

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

让我们 `modulus` 通过 $N $ 和 `constMultiplier` $a $ 来表示。
然后，此操作实现了以下映射定义的单一操作： $ $ \begin{align} \ket{y} \mapsto \ket{ (\cdot y) \operatorname{mod} N} \end{align} $ $，用于 $0 $ 和 $N-$1 之间的所有 $y $。

## <a name="input"></a>输入

### <a name="constmultiplier--int"></a>constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)

乘数相乘的常量。 必须与模数共同。


### <a name="modulus--int"></a>取模： [Int](xref:microsoft.quantum.lang-ref.int)

乘法运算执行取模运算 `modulus` 。


### <a name="multiplier--littleendian"></a>乘法器： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

与常量相乘的数字。
这是一个 qubits 编码数组，用小 endian 格式的整数编码。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

- 对于 "线路" 关系图和解释，请参阅 [arXiv 的第8页上的图7： quant/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- 此操作对应于 ArXiv 中的 U ₐ [： quant/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)