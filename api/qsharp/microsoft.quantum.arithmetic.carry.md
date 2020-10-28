---
uid: Microsoft.Quantum.Arithmetic.Carry
title: 执行操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 2b977151861fb01be7d7dbad6e0a7b803fded880
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699929"
---
# <a name="carry-operation"></a>执行操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


实现可逆的执行入口。 给定一个在 qubit 中进行编码的传入位， `carryIn` 并在和中编码两个被加数位， `summand1` 计算的 `summand2` 按位 xor `carryIn` ， `summand1` 并 `summand2` 在 qubit 中将 `summand2` 为 xored 到 qubit `carryOut` 。

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="carryin--qubit"></a>carryIn： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

传入的 qubit。


### <a name="summand1--qubit"></a>summand1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

第一个被加数 qubit。


### <a name="summand2--qubit"></a>summand2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

第二个被加数 qubit 被替换为与和之和的下 `summand1` 位 `summand2` 。


### <a name="carryout--qubit"></a>carryOut： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

执行 qubit 时，将 xored，并将其总和增加。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

