---
title: 类型 Q#
description: 了解编程语言中使用的不同类型 Q# 。
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: c4a3e6563b8cabee87d1db6b9cb1c1f1c1a7131b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835819"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="a8de7-103">类型 Q#</span><span class="sxs-lookup"><span data-stu-id="a8de7-103">Types in Q#</span></span>

<span data-ttu-id="a8de7-104">本文介绍 Q# 用于指定和使用类型的类型模型和语法。</span><span class="sxs-lookup"><span data-stu-id="a8de7-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="a8de7-105">有关如何创建和操作这些类型的表达式的详细信息，请参阅 [类型表达式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="a8de7-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="a8de7-106">我们注意 Q# 到，是一种 *强类型* 语言，因此，仔细使用这些类型可帮助编译器 Q# 在编译时提供对程序的强保证。</span><span class="sxs-lookup"><span data-stu-id="a8de7-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="a8de7-107">若要提供最强的保证，中类型之间的转换 Q# 必须使用对函数的调用进行显式转换，这种转换可表达该转换。</span><span class="sxs-lookup"><span data-stu-id="a8de7-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="a8de7-108">Q# 提供各种此类函数作为 <xref:microsoft.quantum.convert> 命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="a8de7-108">Q# provides a variety of such functions as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="a8de7-109">另一方面，向上转换到兼容类型是隐式发生的。</span><span class="sxs-lookup"><span data-stu-id="a8de7-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="a8de7-110">Q# 提供直接使用的基元类型，以及从其他类型生成新类型的各种方法。</span><span class="sxs-lookup"><span data-stu-id="a8de7-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="a8de7-111">本文的其余部分将对此进行介绍。</span><span class="sxs-lookup"><span data-stu-id="a8de7-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="a8de7-112">基元类型</span><span class="sxs-lookup"><span data-stu-id="a8de7-112">Primitive Types</span></span>

<span data-ttu-id="a8de7-113">此 Q# 语言提供以下 *基元类型*，所有这些类型都可直接在程序中使用 Q# 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-113">The Q# language provides the following *primitive types*, all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="a8de7-114">你还可以使用这些基元类型构造新类型。</span><span class="sxs-lookup"><span data-stu-id="a8de7-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="a8de7-115">`Int`类型表示64位有符号整数，例如，、 `2` `107` 、 `-5` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="a8de7-116">`BigInt`类型表示任意大小的有符号整数，例如、、 `2L` `107L` `-5L` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="a8de7-117">此类型基于 .NET <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="a8de7-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="a8de7-118">的参数。</span><span class="sxs-lookup"><span data-stu-id="a8de7-118">type.</span></span>

- <span data-ttu-id="a8de7-119">`Double`类型表示双精度浮点数，如、、 `0.0` `-1.3` `4e-7` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="a8de7-120">`Bool`类型表示或的布尔值 `true` `false` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="a8de7-121">此 `Range` 类型表示一个由表示的整数序列， `start..step..stop` 其中表示该步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="a8de7-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="a8de7-122">例如， `start .. stop` 对应于 `start..1..stop` ， `1..2..7` 表示序列 $ \{ 1、3、5、7 \} $。</span><span class="sxs-lookup"><span data-stu-id="a8de7-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="a8de7-123">`String`类型是一系列 Unicode 字符，在用户创建后不透明。</span><span class="sxs-lookup"><span data-stu-id="a8de7-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="a8de7-124">在发生 `string` 错误或诊断事件时，使用类型向传统主机报告消息。</span><span class="sxs-lookup"><span data-stu-id="a8de7-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="a8de7-125">`Unit`类型只能有一个值 `()` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="a8de7-126">使用此类型可指示 Q# 函数或操作不返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="a8de7-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="a8de7-127">`Qubit`类型表示量程位或 qubit。</span><span class="sxs-lookup"><span data-stu-id="a8de7-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="a8de7-128">`Qubit`s 对用户不透明。</span><span class="sxs-lookup"><span data-stu-id="a8de7-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="a8de7-129">仅在将其传递给其他操作时，才可以对其进行操作，而不是将其传递到另一个操作，而是测试 (相等性) </span><span class="sxs-lookup"><span data-stu-id="a8de7-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="a8de7-130">最终，你将通过在 `Qubit` 量程处理器 (或量程模拟器) 上调用内部指令来在上执行操作。</span><span class="sxs-lookup"><span data-stu-id="a8de7-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="a8de7-131">此 `Pauli` 类型表示四个 Qubit Pauli 运算符之一。</span><span class="sxs-lookup"><span data-stu-id="a8de7-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="a8de7-132">使用此类型可表示旋转的基本操作，并指定要测量的可观察对象。</span><span class="sxs-lookup"><span data-stu-id="a8de7-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="a8de7-133">这是一个枚举类型，它具有四个可能 `PauliI` 的值：、 `PauliX` 、 `PauliY` 和 `PauliZ` ，它们是类型的常量 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="a8de7-134">`Result`类型表示度量值的结果。</span><span class="sxs-lookup"><span data-stu-id="a8de7-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="a8de7-135">它是具有两个可能值的枚举类型： `One` 和 `Zero` ，它们是类型的常量 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="a8de7-136">`Zero` 指示已度量 + 1 eigenvalue; `One` 指示已测量-1 eigenvalue。</span><span class="sxs-lookup"><span data-stu-id="a8de7-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="a8de7-137">常量 `true` 、、、、、、 `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` 和 `Zero` 是中的所有保留符号 Q# 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="a8de7-138">数组类型</span><span class="sxs-lookup"><span data-stu-id="a8de7-138">Array Types</span></span>

* <span data-ttu-id="a8de7-139">对于任何有效 Q# 类型，都存在一个类型，该类型表示该类型的值的数组。</span><span class="sxs-lookup"><span data-stu-id="a8de7-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="a8de7-140">例如， `Qubit[]` 和 `(Bool, Pauli)[]` 表示 `Qubit` 值和 `(Bool, Pauli)` 元组值的数组。</span><span class="sxs-lookup"><span data-stu-id="a8de7-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="a8de7-141">数组的数组也是有效的。</span><span class="sxs-lookup"><span data-stu-id="a8de7-141">An array of arrays is also valid.</span></span> <span data-ttu-id="a8de7-142">在前面的示例中，将指示数组的数组 `(Bool, Pauli)` `(Bool, Pauli)[][]` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="a8de7-143">此示例 `(Bool, Pauli)[][]` 表示数组的可能交错数组，而不是矩形二维数组。</span><span class="sxs-lookup"><span data-stu-id="a8de7-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="a8de7-144">Q# 不支持矩形多维数组。</span><span class="sxs-lookup"><span data-stu-id="a8de7-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="a8de7-145">使用方括号将数组值用方括号 Q# 括起来，如中所示 `[PauliI, PauliX, PauliY, PauliZ]` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="a8de7-146">数组中所有项的通用基类型确定数组文本的类型。</span><span class="sxs-lookup"><span data-stu-id="a8de7-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="a8de7-147">因此，使用没有公共基类型的元素构造数组将引发错误。</span><span class="sxs-lookup"><span data-stu-id="a8de7-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="a8de7-148">有关示例，请参阅 [callables 的数组](xref:microsoft.quantum.guide.expressions#arrays-of-callables)。</span><span class="sxs-lookup"><span data-stu-id="a8de7-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="a8de7-149">创建后，不能更改数组的元素。</span><span class="sxs-lookup"><span data-stu-id="a8de7-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="a8de7-150">若要构造修改后的数组，请使用 [更新和重新分配语句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) 或 [副本和更新表达式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)。</span><span class="sxs-lookup"><span data-stu-id="a8de7-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="a8de7-151">或者，可以使用关键字通过其大小创建数组 `new` ：</span><span class="sxs-lookup"><span data-stu-id="a8de7-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="a8de7-152">使用 core 函数 `Length` 获取数组中的元素数作为 `Int` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="a8de7-153">数组可以为下标，以获取包含数组元素子集的单个元素或新数组。</span><span class="sxs-lookup"><span data-stu-id="a8de7-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="a8de7-154">数组的下标从零开始，必须是类型 `Int` 或类型 `Range` ：</span><span class="sxs-lookup"><span data-stu-id="a8de7-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="a8de7-155">元组类型</span><span class="sxs-lookup"><span data-stu-id="a8de7-155">Tuple Types</span></span>

<span data-ttu-id="a8de7-156">元组是一种功能强大的概念 Q# ，可用于将值组合成单个值，使其更易于传递。</span><span class="sxs-lookup"><span data-stu-id="a8de7-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="a8de7-157">特别是，使用元组表示法，可以表达每个操作和可调用只采用一个输入，并只返回一个输出。</span><span class="sxs-lookup"><span data-stu-id="a8de7-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="a8de7-158">给定零个或多个不同类型 `T0` ， `T1` ，...， `Tn` 可将新的  *元组类型* 表示为 `(T0, T1, ..., Tn)` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="a8de7-159">用于构造新元组类型的类型本身可以是元组，如中所示 `(Int, (Qubit, Qubit))` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="a8de7-160">但这种嵌套始终是有限的，因为在任何情况下，元组类型都不能包含自身。</span><span class="sxs-lookup"><span data-stu-id="a8de7-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="a8de7-161">新元组类型的值是由元组中每个类型的值序列组成的元组。</span><span class="sxs-lookup"><span data-stu-id="a8de7-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="a8de7-162">例如， `(3, false)` 是一个其类型为元组类型的元组 `(Int, Bool)` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="a8de7-163">可以创建元组、数组的元组、子元组的元组等的数组。</span><span class="sxs-lookup"><span data-stu-id="a8de7-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="a8de7-164">Q#从0.3 到， `Unit` 是空元组的*类型*名称; `()` 用于空元组的*值*。</span><span class="sxs-lookup"><span data-stu-id="a8de7-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="a8de7-165">元组实例是不可变的。</span><span class="sxs-lookup"><span data-stu-id="a8de7-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="a8de7-166">Q# 创建后，不提供更改元组内容的机制。</span><span class="sxs-lookup"><span data-stu-id="a8de7-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="a8de7-167">单一实例元组等效</span><span class="sxs-lookup"><span data-stu-id="a8de7-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="a8de7-168">可以创建单独 (单元素) 元组 `('T1)` ，例如 `(5)` 或 `([1,2,3])` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="a8de7-169">但是，将 Q# 单一实例元组视为等效于所包含的类型的值。</span><span class="sxs-lookup"><span data-stu-id="a8de7-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="a8de7-170">也就是说，and `5` `(5)` 、or 和 between 之间没有区别 `5` `(((5)))` `(5, (6))` `(5, 6)` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="a8de7-171">这与编写时一样有效 `(5)+3` `5+3` ; 两个表达式的计算结果均为 `8` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="a8de7-172">此等效性适用于所有用途，包括赋值和表达式。</span><span class="sxs-lookup"><span data-stu-id="a8de7-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="a8de7-173">给定任意表达式，括在括号中的同一表达式是同一类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="a8de7-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="a8de7-174">例如， `(7)` 是类型为的表达式， `Int` 它是类型的 `([1,2,3])` 表达式 `Int[]` ， `((1,2))` 是类型的表达式 `(Int, Int)` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="a8de7-175">具体而言，这意味着您可以查看其输入元组或输出元组类型具有一个字段的操作或函数，以采用单个参数或返回单个值。</span><span class="sxs-lookup"><span data-stu-id="a8de7-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="a8de7-176">我们将此属性称为 _单独元组等效_。</span><span class="sxs-lookup"><span data-stu-id="a8de7-176">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="a8de7-177">用户定义类型</span><span class="sxs-lookup"><span data-stu-id="a8de7-177">User-Defined Types</span></span>

<span data-ttu-id="a8de7-178">用户定义的类型声明包含关键字 `newtype` ，后跟用户定义类型的名称、 `=` 有效类型规范和终止分号。</span><span class="sxs-lookup"><span data-stu-id="a8de7-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="a8de7-179">例如：</span><span class="sxs-lookup"><span data-stu-id="a8de7-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="a8de7-180">每个 Q# 源文件可以声明任意数量的用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="a8de7-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="a8de7-181">类型名称在命名空间中必须是唯一的，且不能与操作和函数名称冲突。</span><span class="sxs-lookup"><span data-stu-id="a8de7-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="a8de7-182">用户定义类型是不同的，即使基类型相同也是如此。</span><span class="sxs-lookup"><span data-stu-id="a8de7-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="a8de7-183">具体而言，两个用户定义类型的值之间不会自动转换，即使基础类型相同也是如此。</span><span class="sxs-lookup"><span data-stu-id="a8de7-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="a8de7-184">命名与匿名项</span><span class="sxs-lookup"><span data-stu-id="a8de7-184">Named vs. anonymous items</span></span>

<span data-ttu-id="a8de7-185">Q#文件可以定义包含任何合法类型的单个值的新命名类型。</span><span class="sxs-lookup"><span data-stu-id="a8de7-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="a8de7-186">对于任何元组类型 `T` ，可以使用语句声明一个新的用户定义类型，该类型是的子类型 `T` `newtype` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="a8de7-187">@"microsoft.quantum.math"例如，在命名空间中，复数定义为用户定义的类型：</span><span class="sxs-lookup"><span data-stu-id="a8de7-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="a8de7-188">此语句创建一个新类型，其中包含两个匿名项类型 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="a8de7-189">除了匿名项以外，用户定义类型还支持0.7 或更高版本中的 *命名项* Q# 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="a8de7-190">例如，可以将的项命名为， `Real` 表示复数的实部和 `Imag` 虚部：</span><span class="sxs-lookup"><span data-stu-id="a8de7-190">For example, you could name the items to `Real` for the double representing the real part of a complex number and `Imag` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
<span data-ttu-id="a8de7-191">为用户定义类型中的一个项命名并不意味着需要命名所有项-支持命名项和未命名项的任意组合。</span><span class="sxs-lookup"><span data-stu-id="a8de7-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="a8de7-192">此外，内部项还可以命名为。</span><span class="sxs-lookup"><span data-stu-id="a8de7-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="a8de7-193">`Nested`例如，下面定义的类型具有基础类型 `(Double, (Int, String))` ，其类型仅为类型为的项 `Int` ，所有其他项都是匿名的。</span><span class="sxs-lookup"><span data-stu-id="a8de7-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="a8de7-194">命名项的优点是可以通过 *访问运算符*直接访问它们 `::` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

<span data-ttu-id="a8de7-195">除了为可能复杂的元组类型提供短别名以外，定义此类类型的一个明显优势在于它们可以记录特定值的意图。</span><span class="sxs-lookup"><span data-stu-id="a8de7-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="a8de7-196">返回到的示例 `Complex` ，还可以将极坐标表示形式定义为用户定义的类型：</span><span class="sxs-lookup"><span data-stu-id="a8de7-196">Returning to the example of `Complex`, one could have also defined a polar coordinate represenation as a user-defined type:</span></span>

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

<span data-ttu-id="a8de7-197">尽管 `Complex` 和 `ComplexPolar` 都有基础类型，但这 `(Double, Double)` 两种类型在中完全不兼容 Q# ，但在极大程度上，最大程度地降低意外调用复杂数学函数的风险，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a8de7-197">Even though both `Complex` and `ComplexPolar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="a8de7-198">使用解包运算符访问匿名项</span><span class="sxs-lookup"><span data-stu-id="a8de7-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="a8de7-199">若要访问匿名项，请首先使用后缀运算符提取包装的值 `!` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="a8de7-200">使用 "解包" 运算符， `!` 可以提取用户定义类型中包含的值。</span><span class="sxs-lookup"><span data-stu-id="a8de7-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="a8de7-201">此类 "解包" 表达式的类型为用户定义类型的基础类型。</span><span class="sxs-lookup"><span data-stu-id="a8de7-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="a8de7-202">单个解包运算符对一层包装进行了解包。</span><span class="sxs-lookup"><span data-stu-id="a8de7-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="a8de7-203">使用多个解包运算符来访问乘换行值。</span><span class="sxs-lookup"><span data-stu-id="a8de7-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="a8de7-204">例如：</span><span class="sxs-lookup"><span data-stu-id="a8de7-204">For example:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="a8de7-205">有关解包运算符的更多详细信息，请参阅[ Q# 中的类型表达式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="a8de7-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="a8de7-206">创建用户定义类型的值</span><span class="sxs-lookup"><span data-stu-id="a8de7-206">Creating values of user-defined types</span></span>

<span data-ttu-id="a8de7-207">通过调用相应的类型构造函数来创建用户定义类型的值：</span><span class="sxs-lookup"><span data-stu-id="a8de7-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="a8de7-208">或者，您可以使用 [复制和更新表达式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)从现有值创建新值。</span><span class="sxs-lookup"><span data-stu-id="a8de7-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="a8de7-209">与在数组中一样，复制和更新表达式会复制原始表达式的所有项值（指定的已命名项除外）。</span><span class="sxs-lookup"><span data-stu-id="a8de7-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="a8de7-210">对于这些异常，这些项的值是在表达式的右侧定义的值。</span><span class="sxs-lookup"><span data-stu-id="a8de7-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="a8de7-211">对于用户定义类型中的命名项，还存在可用于数组项的任何其他语言构造（例如， [更新和重新分配语句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)）。</span><span class="sxs-lookup"><span data-stu-id="a8de7-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

* <span data-ttu-id="a8de7-212">你可以使用任何其他类型的任意位置的用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="a8de7-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="a8de7-213">具体而言，可以定义用户定义类型的数组，并将用户定义类型作为元组类型的元素包括在内。</span><span class="sxs-lookup"><span data-stu-id="a8de7-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="a8de7-214">无法创建递归类型结构。</span><span class="sxs-lookup"><span data-stu-id="a8de7-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="a8de7-215">也就是说，定义用户定义类型的类型不能是包含用户定义类型的元素的元组类型。</span><span class="sxs-lookup"><span data-stu-id="a8de7-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="a8de7-216">更常见的情况是，用户定义类型可能没有彼此之间的循环依赖关系，因此下面的一组类型定义无效：</span><span class="sxs-lookup"><span data-stu-id="a8de7-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="a8de7-217">操作和函数类型</span><span class="sxs-lookup"><span data-stu-id="a8de7-217">Operation and Function Types</span></span>

<span data-ttu-id="a8de7-218">给定类型 `'Tinput` 和 `'Tresult` ：</span><span class="sxs-lookup"><span data-stu-id="a8de7-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="a8de7-219">`('Tinput => 'Tresult)` 是任何 *操作*的基本类型，例如 `((Qubit, Pauli) => Result)` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-219">`('Tinput => 'Tresult)` is the basic type for any *operation*, for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="a8de7-220">`('Tinput -> 'Tresult)` 是任何 *函数*的基本类型，例如 `(Int -> Int)` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-220">`('Tinput -> 'Tresult)` is the basic type for any *function*, for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="a8de7-221">这些是可调用的 *签名* 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="a8de7-222">所有 Q# callables 采用单个值作为输入，并返回单个值作为输出。</span><span class="sxs-lookup"><span data-stu-id="a8de7-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="a8de7-223">可以对输入和输出值使用元组。</span><span class="sxs-lookup"><span data-stu-id="a8de7-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="a8de7-224">不返回结果的 Callables，返回 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="a8de7-225">不带输入的 Callables 将空元组作为输入。</span><span class="sxs-lookup"><span data-stu-id="a8de7-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="a8de7-226">函子</span><span class="sxs-lookup"><span data-stu-id="a8de7-226">Functors</span></span>

<span data-ttu-id="a8de7-227">*函数* 类型由其签名完全指定。</span><span class="sxs-lookup"><span data-stu-id="a8de7-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="a8de7-228">例如，计算角度正弦值的函数将具有类型 `(Double -> Double)` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="a8de7-229">*操作* 具有一些其他特征，这些特征表示为操作类型的一部分。</span><span class="sxs-lookup"><span data-stu-id="a8de7-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="a8de7-230">此类特征包括有关操作支持的 *函子* 的信息。</span><span class="sxs-lookup"><span data-stu-id="a8de7-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="a8de7-231">例如，如果运行操作依赖于其他 qubits 的状态，则它应支持 `Controlled` 函子; 如果操作具有反向，则它应支持 `Adjoint` 函子。</span><span class="sxs-lookup"><span data-stu-id="a8de7-231">For example, if the running of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="a8de7-232">本文仅讨论函子如何更改操作签名。</span><span class="sxs-lookup"><span data-stu-id="a8de7-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="a8de7-233">有关函子和操作的更多详细信息，请参阅[中 Q# 的操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="a8de7-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="a8de7-234">若要要求对 `Controlled` 操作类型中的和/或函子提供支持 `Adjoint` ，需要添加指示相应特征的注释。</span><span class="sxs-lookup"><span data-stu-id="a8de7-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="a8de7-235">批注 `is Ctl` (例如， `(Qubit => Unit is Ctl)`) 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="a8de7-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="a8de7-236">也就是说，它的运行依赖于另一个 qubit 或 qubits 的状态。</span><span class="sxs-lookup"><span data-stu-id="a8de7-236">That is, its run relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="a8de7-237">同样，批注 `is Adj` 指示操作具有 adjoint，也就是说，它可以 "反转" 以便连续应用操作，然后将其 adjoint 为状态，使状态保持不变。</span><span class="sxs-lookup"><span data-stu-id="a8de7-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="a8de7-238">如果你希望要求该类型的操作同时支持 `Adjoint` 和 `Controlled` 函子，则可以将此表示为 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="a8de7-239">例如，内置 Pauli 操作的类型为 <xref:microsoft.quantum.intrinsic.x> `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-239">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="a8de7-240">不支持任何函子的操作类型由其输入和输出类型单独指定，无附加批注。</span><span class="sxs-lookup"><span data-stu-id="a8de7-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="a8de7-241">类型参数化的函数和操作</span><span class="sxs-lookup"><span data-stu-id="a8de7-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="a8de7-242">可调用类型可以包含 *类型参数*。</span><span class="sxs-lookup"><span data-stu-id="a8de7-242">Callable types may contain *type parameters*.</span></span>
<span data-ttu-id="a8de7-243">使用以单引号为前缀的符号指示类型参数;例如， `'A` 是一个合法的类型参数。</span><span class="sxs-lookup"><span data-stu-id="a8de7-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="a8de7-244">有关如何定义类型参数化 callables 的详细信息和详细信息，请参阅[中的 Q# 操作和函数](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)。</span><span class="sxs-lookup"><span data-stu-id="a8de7-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="a8de7-245">类型参数可能在单个签名中出现多次。</span><span class="sxs-lookup"><span data-stu-id="a8de7-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="a8de7-246">例如，将其他函数应用于数组的每个元素并返回所收集结果的函数具有签名 `(('A[], 'A->'A) -> 'A[])` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="a8de7-247">同样，返回两个操作的组合的函数具有签名 `((('A=>'B), ('B=>'C)) -> ('A=>'C))` 。</span><span class="sxs-lookup"><span data-stu-id="a8de7-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="a8de7-248">调用类型参数化的可调用时，具有相同类型参数的所有参数都必须具有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="a8de7-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="a8de7-249">Q# 不提供一种机制来约束用户可能替换为类型参数的可能类型。</span><span class="sxs-lookup"><span data-stu-id="a8de7-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8de7-250">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a8de7-250">Next steps</span></span>

<span data-ttu-id="a8de7-251">现在，你已了解构成语言的所有类型 Q# ，请参阅[中 Q# 的类型表达式](xref:microsoft.quantum.guide.expressions)，了解如何创建和操作这些不同类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="a8de7-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
