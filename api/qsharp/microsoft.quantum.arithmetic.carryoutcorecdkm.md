---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699928"
---
# <a name="carryoutcorecdkm-operation"></a>CarryOutCoreCDKM 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


RippleCarryAdderCDKM 中与上述 ApplyOuterCDKMAdder 操作一起使用的核心操作，即 conjugated，用于获取 RippleCarryAdderCDKM 的内部操作。 此操作计算执行 qubit，并对输入的部分应用一系列 NOT 入口 `ys` 。

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第一个 qubit 注册。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第二个 qubit 寄存器。


### <a name="ancilla--qubit"></a>ancilla： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

传递给此操作的 RippleCarryAdderCDKM 中使用的 ancilla qubit。


### <a name="carry--qubit"></a>携带： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

在 RippleCarryAdderCDKM 操作中执行 qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>参考

- Steven Cuccaro、Thomas Draper、Samuel Kutin、David Petrie Moulton： "A 新的量程波纹-携带加法线路"，2004。
  https://arxiv.org/abs/quant-ph/0410184v1