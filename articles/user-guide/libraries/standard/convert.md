---
title: 标准库中的类型转换 Q#
description: 了解标准库中的常用和用户定义类型转换函数 Q# 。
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2319bf453f5fbf6bd068859ea65562423d3ff4d0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868503"
---
# <a name="type-conversions"></a><span data-ttu-id="3b630-103">类型转换</span><span class="sxs-lookup"><span data-stu-id="3b630-103">Type Conversions</span></span> #

<span data-ttu-id="3b630-104">Q#是**强类型**语言。</span><span class="sxs-lookup"><span data-stu-id="3b630-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="3b630-105">具体而言，不 Q# 会在不同类型之间隐式强制转换。</span><span class="sxs-lookup"><span data-stu-id="3b630-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="3b630-106">例如，不是 `1 + 2.0` 有效的 Q# 表达式。</span><span class="sxs-lookup"><span data-stu-id="3b630-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="3b630-107">而是 Q# 提供各种类型转换函数用于构造给定类型的新值。</span><span class="sxs-lookup"><span data-stu-id="3b630-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="3b630-108">例如，的 <xref:microsoft.quantum.core.length> 输出类型为 `Int` ，因此必须先将其输出转换为，然后才能 `Double` 将其用作浮点表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="3b630-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="3b630-109">可以使用函数执行此 <xref:microsoft.quantum.convert.intasdouble> 操作：</span><span class="sxs-lookup"><span data-stu-id="3b630-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="3b630-110"><xref:microsoft.quantum.convert>命名空间提供了用于处理基本内置类型（例如、、、和）的通用类型转换函数 `Int` `Double` `BigInt` `Result` `Bool` ：</span><span class="sxs-lookup"><span data-stu-id="3b630-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="3b630-111"><xref:microsoft.quantum.convert>命名空间还提供了一些更现的转换，例如 `FunctionAsOperation` ，将函数转换 `'T -> 'U` 为新操作 `'T => 'U` 。</span><span class="sxs-lookup"><span data-stu-id="3b630-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="3b630-112">最后， Q# 标准库提供了许多用户定义的类型，例如 <xref:microsoft.quantum.math.complex> 和 <xref:microsoft.quantum.arithmetic.littleendian> 。</span><span class="sxs-lookup"><span data-stu-id="3b630-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="3b630-113">除了这些类型之外，标准库还提供如下功能 <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> ：</span><span class="sxs-lookup"><span data-stu-id="3b630-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
