---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696140"
---
# <a name="approximateqft-operation"></a>ApproximateQFT 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将大致的量程傅立叶转换 (AQFT) 应用到一个量程寄存器。

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

确定 QFT 线路中发生的受控 Z 旋转在哪个级别上被修剪的近似值参数。

近似值参数 a 确定 Z 旋转的修剪级别，即∈ {0 ... n} 和所有 Z 旋转 2π/2k，其中 k>从 QFT 线路中删除。 知道，对于 k >= log ₂ (n) + log ₂ (1/ε) + 3 1 可以绑定 | |QFT-AQFT | |<ε。


### <a name="qs--bigendian"></a>qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

应用大致量程傅立叶转换的 n qubits 的量程寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

AQFT 需要 2π/2k 和 Hadamard 入口的 Z 旋转入口。

输入和输出假定为以大字节序编码进行编码。

## <a name="references"></a>参考

- [*Roetteler，Beth* ，Appl.exe，Commun。计算机.19 (3) ： 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv： quant/0201067v1](https://arxiv.org/abs/quant-ph/0201067)