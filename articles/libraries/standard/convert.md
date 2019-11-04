---
title: 'Q # 标准库-类型转换 |Microsoft Docs'
description: 'Q # 标准库-类型转换'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184468"
---
# <a name="type-conversions"></a><span data-ttu-id="a8235-103">类型转换</span><span class="sxs-lookup"><span data-stu-id="a8235-103">Type Conversions</span></span> #

<span data-ttu-id="a8235-104">Q # 是一种**强类型**语言。</span><span class="sxs-lookup"><span data-stu-id="a8235-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="a8235-105">特别是，Q # 不会在不同类型之间隐式强制转换。</span><span class="sxs-lookup"><span data-stu-id="a8235-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="a8235-106">例如，`1 + 2.0` 不是有效的 Q # 表达式。</span><span class="sxs-lookup"><span data-stu-id="a8235-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="a8235-107">相反，Q # 提供各种类型转换函数用于构造给定类型的新值。</span><span class="sxs-lookup"><span data-stu-id="a8235-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="a8235-108">例如，<xref:microsoft.quantum.core.length> 的输出类型为 `Int`，因此必须先将其输出转换为 `Double`，然后才能将其用作浮点表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="a8235-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="a8235-109">可以使用 <xref:microsoft.quantum.convert.intasdouble> 函数完成此操作：</span><span class="sxs-lookup"><span data-stu-id="a8235-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="a8235-110"><xref:microsoft.quantum.convert> 命名空间为使用基本内置类型（例如 `Int`、`Double`、`BigInt`、`Result`和 `Bool`）提供了常见的类型转换函数：</span><span class="sxs-lookup"><span data-stu-id="a8235-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="a8235-111"><xref:microsoft.quantum.convert> 命名空间还提供了一些更现的转换，如 `FunctionAsOperation`，它将函数 `'T -> 'U` 转换为新操作 `'T => 'U`。</span><span class="sxs-lookup"><span data-stu-id="a8235-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="a8235-112">最后，Q # 标准库提供了许多用户定义的类型，例如 <xref:microsoft.quantum.math.complex> 和 <xref:microsoft.quantum.arithmetic.littleendian>。</span><span class="sxs-lookup"><span data-stu-id="a8235-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="a8235-113">标准库与这些类型一起提供了一些函数，例如 <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>：</span><span class="sxs-lookup"><span data-stu-id="a8235-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
