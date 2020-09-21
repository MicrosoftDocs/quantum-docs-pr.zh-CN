---
title: 标准库中的类型转换 Q#
description: 了解标准库中的常用和用户定义类型转换函数 Q# 。
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: aa8a1ad624067906998d2735c7a95174a163ce97
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835598"
---
# <a name="type-conversions"></a>类型转换 #

Q# 是 **强类型** 语言。
具体而言，不 Q# 会在不同类型之间隐式强制转换。 例如，不是 `1 + 2.0` 有效的 Q# 表达式。
而是 Q# 提供各种类型转换函数用于构造给定类型的新值。

例如，的 <xref:microsoft.quantum.core.length> 输出类型为 `Int` ，因此必须先将其输出转换为，然后才能 `Double` 将其用作浮点表达式的一部分。
可以使用函数执行此 <xref:microsoft.quantum.convert.intasdouble> 操作：

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert>命名空间提供了用于处理基本内置类型（例如、、、和）的通用类型转换函数 `Int` `Double` `BigInt` `Result` `Bool` ：

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert>命名空间还提供了一些更现的转换，例如 `FunctionAsOperation` ，将函数转换 `'T -> 'U` 为新操作 `'T => 'U` 。

最后， Q# 标准库提供了许多用户定义的类型，例如 <xref:microsoft.quantum.math.complex> 和 <xref:microsoft.quantum.arithmetic.littleendian> 。
除了这些类型之外，标准库还提供如下功能 <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> ：

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
