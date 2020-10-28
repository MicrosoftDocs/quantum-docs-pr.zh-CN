---
uid: Microsoft.Quantum.Arithmetic.Sum
title: 操作总数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696561"
---
# <a name="sum-operation"></a>操作总数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


实现可逆的 sum 入口。 给定一个以 qubit 编码的传入位 `carryIn` ，以及在和中编码的两个被加数位 `summand1` `summand2` ，计算的和的按位 xor `carryIn` `summand1` `summand2` `summand2` 。

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="carryin--qubit"></a>carryIn： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

传入的 qubit。


### <a name="summand1--qubit"></a>summand1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

第一个被加数 qubit。


### <a name="summand2--qubit"></a>summand2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

第二个被加数 qubit 被替换为与和之和的下 `summand1` 位 `summand2` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

与 `Carry` 操作相反，此操作不会计算出执行位。