---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223096"
---
# <a name="fixedpoint-user-defined-type"></a>FixedPoint 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)


表示 qubits 编码固定点数字的寄存器。 包含一个整数，该整数等于二进制点左侧的 qubits 数，即，qubits 权重大于或等于1，以及一个量程寄存器。

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

