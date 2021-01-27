---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843473"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


在传统整数和由 qubits 的寄存器表示的整数之间应用按位 "异或" 运算。

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

将 `X` 操作应用到基于整数中的1位的小 endian 寄存器中的 qubits。

让我们表示， `value` 并使 y 成为编码的无符号整数 `target` ，然后 `InPlaceXorLE` 执行以下映射指定的操作： $ \ket{y}\rightarrow \ket{y\oplus a} $，其中 $ \oplus $ 为按位 "异或" 运算符。

## <a name="input"></a>输入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

一个整数，其假定为非负数。


### <a name="target--littleendian"></a>目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

用于存储 `value` 小字节序编码的量程寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

