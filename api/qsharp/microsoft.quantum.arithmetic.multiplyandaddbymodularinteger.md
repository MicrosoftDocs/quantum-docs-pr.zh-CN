---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696612"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>MultiplyAndAddByModularInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


对 qubit 寄存器上的整数常量执行模块化乘法和-add。

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>说明

为给定的取模实现 map $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{ (b + a \cdot x) \operatorname{mod} N} \end{align} $ $ $N $，恒定乘数 $a $，被加数 $y $。

## <a name="input"></a>输入

### <a name="constmultiplier--int"></a>constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)

要添加到每个基础状态标签的整数 $a $。


### <a name="modulus--int"></a>取模： [Int](xref:microsoft.quantum.lang-ref.int)

取模 $N $，将对执行加法和乘法运算。


### <a name="multiplier--littleendian"></a>乘法器： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

一个量程寄存器，表示其值要添加到的每个基本状态标签的无符号整数 `summand` 。


### <a name="summand--littleendian"></a>被加数： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

一个量程寄存器，表示要用作此操作的目标的无符号整数。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

- 有关线路和说明，请参阅[arXiv： quant/0205095V3 第7页](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)上的图6
- 此操作对应于 ArXiv 中的 CMULT () MOD (N) [： quant/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)

## <a name="see-also"></a>另请参阅

- [MultiplyAndAddPhaseByModularInteger。](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)