---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699864"
---
# <a name="incrementbyinteger-operation"></a>IncrementByInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


使用阶段旋转，将未签名的量程寄存器增加一个传统整数。

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>说明

假定将 `target` 无符号整数编码 $x $ in 小字节序编码，并且 `increment` 等于 $a $。
然后，此操作实现一个单一 $ \ket{x} \mapsto \ket{x + a} $，其中添加操作执行取模 $ 2 ^ n $，其中 $n = \texttt{Length (target！ ) } $。

## <a name="input"></a>输入

### <a name="increment--int"></a>增量： [Int](xref:microsoft.quantum.lang-ref.int)

的整数，该整数用于 `target` 递增。


### <a name="target--littleendian"></a>目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

量程寄存器使用小字节序编码对无符号整数进行编码。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

