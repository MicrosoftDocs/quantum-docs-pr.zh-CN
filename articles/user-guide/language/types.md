---
title: Q# 中的类型
description: '了解 Q # 编程语言中使用的不同类型。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 4a551ee90a0abb6e42953cf04c7f5a8ca3573f26
ms.sourcegitcommit: 682a4a5f5dd23ca58a4addf62aea4086bb308552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609135"
---
# <a name="types-in-q"></a><span data-ttu-id="ecd42-103">Q# 中的类型</span><span class="sxs-lookup"><span data-stu-id="ecd42-103">Types in Q#</span></span>

<span data-ttu-id="ecd42-104">此页对 Q # 类型模型进行了布局，并介绍了用于指定和使用类型的语法。</span><span class="sxs-lookup"><span data-stu-id="ecd42-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="ecd42-105">下一页，[键入表达式](xref:microsoft.quantum.guide.expressions)，详细说明如何创建和操作这些类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="ecd42-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="ecd42-106">我们注意到，Q # 是一种*强类型*语言，因此，仔细地使用这些类型可帮助编译器在编译时为 Q # 程序提供强大的保证。</span><span class="sxs-lookup"><span data-stu-id="ecd42-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="ecd42-107">为了尽可能提供最强的保证，在 Q # 中的类型之间进行转换时，必须使用对函数的调用来显式转换。</span><span class="sxs-lookup"><span data-stu-id="ecd42-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="ecd42-108">此类函数作为命名空间的一部分提供 <xref:microsoft.quantum.convert> 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="ecd42-109">另一方面，向上转换到兼容类型是隐式的。</span><span class="sxs-lookup"><span data-stu-id="ecd42-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="ecd42-110">Q # 提供了基元类型，可以直接使用，也可以通过多种方式从其他类型生成新类型。</span><span class="sxs-lookup"><span data-stu-id="ecd42-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="ecd42-111">本部分的其余部分介绍了每个。</span><span class="sxs-lookup"><span data-stu-id="ecd42-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="ecd42-112">基元类型</span><span class="sxs-lookup"><span data-stu-id="ecd42-112">Primitive Types</span></span>

<span data-ttu-id="ecd42-113">Q # 语言提供若干*基元类型*，可以从这些类型构造其他类型：</span><span class="sxs-lookup"><span data-stu-id="ecd42-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="ecd42-114">`Int`类型表示64位有符号整数，例如： `2` 、 `107` 、 `-5` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="ecd42-115">`BigInt`类型表示任意大小的有符号整数，例如 `2L` 、 `107L` 和 `-5L` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="ecd42-116">此类型基于 .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="ecd42-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="ecd42-117">type。</span><span class="sxs-lookup"><span data-stu-id="ecd42-117">type.</span></span>
- <span data-ttu-id="ecd42-118">`Double`类型表示双精度浮点数，例如： `0.0` 、 `-1.3` 、 `4e-7` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="ecd42-119">`Bool`类型表示布尔值，可以是 `true` 或 `false` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="ecd42-120">此 `Range` 类型表示一个由表示的整数序列， `start..step..stop` 其中表示该步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="ecd42-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="ecd42-121">对应于 `start .. stop` `start..1..stop` ，例如， `1..2..7` 表示序列 $ \{ 1、3、5、7 \} $。</span><span class="sxs-lookup"><span data-stu-id="ecd42-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="ecd42-122">`String`类型是一系列 Unicode 字符，在用户创建后不透明。</span><span class="sxs-lookup"><span data-stu-id="ecd42-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="ecd42-123">在发生错误或诊断事件时，此类型用于向传统主机报告消息。</span><span class="sxs-lookup"><span data-stu-id="ecd42-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="ecd42-124">`Unit`类型是只允许一个值的类型 `()` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="ecd42-125">此类型用于指示 Q # 函数或操作不返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="ecd42-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="ecd42-126">`Qubit`类型表示量程位或 qubit。</span><span class="sxs-lookup"><span data-stu-id="ecd42-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="ecd42-127">`Qubit`s 对用户是不透明的;仅在将其传递给其他操作时，才可以对其进行操作，而不是将其传递到其他操作。</span><span class="sxs-lookup"><span data-stu-id="ecd42-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="ecd42-128">最终，对的操作 `Qubit` 是通过对量程处理器（或其模拟）调用内部指令来实现的。</span><span class="sxs-lookup"><span data-stu-id="ecd42-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="ecd42-129">此 `Pauli` 类型表示四个 Qubit Pauli 运算符之一。</span><span class="sxs-lookup"><span data-stu-id="ecd42-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="ecd42-130">此类型用于表示旋转的基本操作，并指定要测量的可观察对象。</span><span class="sxs-lookup"><span data-stu-id="ecd42-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="ecd42-131">这是一个枚举类型，它具有四个可能 `PauliI` 的值：、 `PauliX` 、 `PauliY` 和 `PauliZ` ，它们是类型的常量 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="ecd42-132">`Result`类型表示度量值的结果。</span><span class="sxs-lookup"><span data-stu-id="ecd42-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="ecd42-133">这是具有两个可能值的枚举类型： `One` 和 `Zero` ，它们是类型的常量 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="ecd42-134">`Zero`指示已度量 + 1 eigenvalue;`One`指示-1 eigenvalue。</span><span class="sxs-lookup"><span data-stu-id="ecd42-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="ecd42-135">常量、、、、、、 `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` 和 `Zero` 都是 Q # 中的所有保留符号。</span><span class="sxs-lookup"><span data-stu-id="ecd42-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="ecd42-136">数组类型</span><span class="sxs-lookup"><span data-stu-id="ecd42-136">Array Types</span></span>

<span data-ttu-id="ecd42-137">给定任何有效的 Q # 类型 `'T` ，都有一个类型，表示类型的值的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="ecd42-138">此数组类型表示为 `'T[]` ; 例如， `Qubit[]` 或 `Int[][]` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="ecd42-139">例如，表示整数的集合 `Int[]` ，而表示值数组的数组 `(Bool, Pauli)` `(Bool, Pauli)[][]` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="ecd42-140">在第二个示例中，请注意，这表示数组的可能交错数组，而不是矩形二维数组。</span><span class="sxs-lookup"><span data-stu-id="ecd42-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="ecd42-141">Q # 不提供对矩形多维数组的支持。</span><span class="sxs-lookup"><span data-stu-id="ecd42-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="ecd42-142">使用方括号将数组的元素括起来，就可以用 Q # 源代码编写数组值，如中所示 `[PauliI, PauliX, PauliY, PauliZ]` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="ecd42-143">数组文本的类型由数组中所有项的通用基类型决定。</span><span class="sxs-lookup"><span data-stu-id="ecd42-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="ecd42-144">创建数组后，不能更改数组的元素。</span><span class="sxs-lookup"><span data-stu-id="ecd42-144">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="ecd42-145">[更新和重新分配语句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)和/或[复制和更新表达式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)可用于构造修改后的数组。</span><span class="sxs-lookup"><span data-stu-id="ecd42-145">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="ecd42-146">或者，可以使用关键字通过其大小创建数组 `new` ：</span><span class="sxs-lookup"><span data-stu-id="ecd42-146">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="ecd42-147">在这两种情况下，构造数组后， `Length` 可以使用核心函数获取作为的元素数 `Int` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-147">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="ecd42-148">数组可以使用方括号（带有类型或类型的下标）作为下标， `Int` `Range` 以获取包含数组元素子集的单个元素或新数组。</span><span class="sxs-lookup"><span data-stu-id="ecd42-148">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="ecd42-149">数组的下标是从零开始的：</span><span class="sxs-lookup"><span data-stu-id="ecd42-149">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="ecd42-150">元组类型</span><span class="sxs-lookup"><span data-stu-id="ecd42-150">Tuple Types</span></span>

<span data-ttu-id="ecd42-151">给定零个或多个不同类型 `T0` ， `T1` ，...， `Tn` 我们可以将新的*元组类型*表示为 `(T0, T1, ..., Tn)` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-151">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="ecd42-152">用于构造新元组类型的类型本身可以是元组，如中所示 `(Int, (Qubit, Qubit))` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-152">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="ecd42-153">但这种嵌套始终是有限的，因为在任何情况下，元组类型都不能包含自身。</span><span class="sxs-lookup"><span data-stu-id="ecd42-153">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="ecd42-154">新元组类型的值是由元组中每个类型的值序列构成的元组。</span><span class="sxs-lookup"><span data-stu-id="ecd42-154">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="ecd42-155">例如， `(3, false)` 是一个其类型为元组类型的元组 `(Int, Bool)` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-155">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="ecd42-156">可以创建元组、数组的元组、子元组的元组等的数组。</span><span class="sxs-lookup"><span data-stu-id="ecd42-156">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="ecd42-157">从 Q # 0.3， `Unit` 是空元组的*类型*名称; `()` 用于空元组*值*。</span><span class="sxs-lookup"><span data-stu-id="ecd42-157">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="ecd42-158">元组实例是不可变的。</span><span class="sxs-lookup"><span data-stu-id="ecd42-158">Tuple instances are immutable.</span></span>
<span data-ttu-id="ecd42-159">Q # 不提供在创建元组内容之后更改元组内容的机制。</span><span class="sxs-lookup"><span data-stu-id="ecd42-159">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="ecd42-160">元组是一种功能强大的概念，用于在整个 Q # 中将值组合成单个值，使其更易于传递。</span><span class="sxs-lookup"><span data-stu-id="ecd42-160">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="ecd42-161">特别是，使用元组表示法，可以表达每个操作和可调用只采用一个输入，并只返回一个输出。</span><span class="sxs-lookup"><span data-stu-id="ecd42-161">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="ecd42-162">单一实例元组等效</span><span class="sxs-lookup"><span data-stu-id="ecd42-162">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="ecd42-163">可以创建单一实例（单元素）元组， `('T1)` 例如 `(5)` 或 `([1,2,3])` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-163">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="ecd42-164">不过，Q # 将单一实例元组视为完全等效于封闭类型的值。</span><span class="sxs-lookup"><span data-stu-id="ecd42-164">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="ecd42-165">也就是说，and `5` `(5)` 、or 和 between 之间没有区别 `5` `(((5)))` `(5, (6))` `(5, 6)` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-165">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="ecd42-166">它与写入编写一样有效 `(5)+3` `5+3` ，并且两个表达式的计算结果均为 `8` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="ecd42-167">此等效性适用于所有用途，包括赋值和表达式。</span><span class="sxs-lookup"><span data-stu-id="ecd42-167">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="ecd42-168">给定任意表达式，括在括号中的同一表达式是同一类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="ecd42-168">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="ecd42-169">例如， `(7)` 是一个 `Int` 表达式， `([1,2,3])` 是类型为的数组的表达式 `Int` ，是类型为的 `((1,2))` 表达式 `(Int, Int)` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-169">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="ecd42-170">具体而言，这意味着，其输入元组或输出元组类型具有一个字段的操作或函数可以被视为采用单个参数或返回单个值。</span><span class="sxs-lookup"><span data-stu-id="ecd42-170">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="ecd42-171">我们将此属性称为_单独元组等效_。</span><span class="sxs-lookup"><span data-stu-id="ecd42-171">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="ecd42-172">用户定义类型</span><span class="sxs-lookup"><span data-stu-id="ecd42-172">User-Defined Types</span></span>

<span data-ttu-id="ecd42-173">用户定义的类型声明包含关键字 `newtype` ，后跟用户定义类型的名称、 `=` 有效类型规范和终止分号。</span><span class="sxs-lookup"><span data-stu-id="ecd42-173">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="ecd42-174">例如：</span><span class="sxs-lookup"><span data-stu-id="ecd42-174">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="ecd42-175">每个 Q # 源文件可以声明任意数量的用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="ecd42-175">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="ecd42-176">类型名称在命名空间中必须是唯一的，且不能与操作和函数名称冲突。</span><span class="sxs-lookup"><span data-stu-id="ecd42-176">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="ecd42-177">即使基类型是相同的，用户定义的类型还是不同的。</span><span class="sxs-lookup"><span data-stu-id="ecd42-177">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="ecd42-178">具体而言，两个用户定义类型的值之间不会自动转换，即使基础类型相同也是如此。</span><span class="sxs-lookup"><span data-stu-id="ecd42-178">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="ecd42-179">命名与匿名项</span><span class="sxs-lookup"><span data-stu-id="ecd42-179">Named vs. anonymous items</span></span>

<span data-ttu-id="ecd42-180">Q # 文件可以定义包含任何合法类型的单个值的新命名类型。</span><span class="sxs-lookup"><span data-stu-id="ecd42-180">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="ecd42-181">对于任何元组类型 `T` ，可以声明一个新的用户定义类型，该类型是具有语句的的子类型 `T` `newtype` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-181">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="ecd42-182">例如 @"microsoft.quantum.math" ，在命名空间中，复数定义为用户定义的类型：</span><span class="sxs-lookup"><span data-stu-id="ecd42-182">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="ecd42-183">此语句创建一个新类型，其中包含两个匿名项类型 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-183">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="ecd42-184">除了匿名项以外，用户定义类型还支持从 Q # 版本0.7 或更高版本开始的*命名项*。</span><span class="sxs-lookup"><span data-stu-id="ecd42-184">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="ecd42-185">例如，对于 `Re` 表示复数实部和虚部的双精度值，我们可以命名为的项 `Im` ：</span><span class="sxs-lookup"><span data-stu-id="ecd42-185">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="ecd42-186">为用户定义类型中的一个项命名并不意味着需要命名所有项-支持命名项和未命名项的任意组合。</span><span class="sxs-lookup"><span data-stu-id="ecd42-186">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="ecd42-187">此外，内部项还可以命名为。</span><span class="sxs-lookup"><span data-stu-id="ecd42-187">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="ecd42-188">下面定义的类型（ `Nested` 例如）具有基础类型 `(Double, (Int, String))` ，其中只命名了类型为的项 `Int` ，所有其他项都是匿名的。</span><span class="sxs-lookup"><span data-stu-id="ecd42-188">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="ecd42-189">命名项的优点是可以通过*访问运算符*直接访问它们 `::` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-189">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="ecd42-190">除了为可能复杂的元组类型提供短别名外，定义此类类型的一个明显优势在于它们可以记录特定值的意图。</span><span class="sxs-lookup"><span data-stu-id="ecd42-190">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="ecd42-191">返回到的示例 `Complex` ，一个还可以将2d 极坐标定义为用户定义的类型：</span><span class="sxs-lookup"><span data-stu-id="ecd42-191">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="ecd42-192">尽管和都 `Complex` `Polar` 具有基础类型，但这 `(Double, Double)` 两种类型在 Q # 中是完全不兼容的，但最大程度地减少了意外调用带有极坐标的复杂数学函数的风险，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ecd42-192">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="ecd42-193">通过这种方式，用户定义类型与 F # 中的记录具有类似的角色，例如。</span><span class="sxs-lookup"><span data-stu-id="ecd42-193">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="ecd42-194">使用解包运算符访问匿名项</span><span class="sxs-lookup"><span data-stu-id="ecd42-194">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="ecd42-195">为了访问匿名项，首先需要使用后缀运算符来提取换行值 `!` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-195">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="ecd42-196">使用 "解包" 运算符， `!` 可以提取用户定义类型中包含的值。</span><span class="sxs-lookup"><span data-stu-id="ecd42-196">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="ecd42-197">此类 "解包" 表达式的类型为用户定义类型的基础类型。</span><span class="sxs-lookup"><span data-stu-id="ecd42-197">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="ecd42-198">解包运算符仅解包一层包装。</span><span class="sxs-lookup"><span data-stu-id="ecd42-198">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="ecd42-199">可以使用多个解包运算符来访问乘换行值。</span><span class="sxs-lookup"><span data-stu-id="ecd42-199">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="ecd42-200">例如：</span><span class="sxs-lookup"><span data-stu-id="ecd42-200">For instance:</span></span>

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

<span data-ttu-id="ecd42-201">有关解包运算符的更多详细信息，请参阅[Q # 中的类型表达式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="ecd42-201">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="ecd42-202">创建用户定义类型的值</span><span class="sxs-lookup"><span data-stu-id="ecd42-202">Creating values of user-defined types</span></span>

<span data-ttu-id="ecd42-203">可以通过调用相应的类型构造函数来创建用户定义类型的值：</span><span class="sxs-lookup"><span data-stu-id="ecd42-203">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="ecd42-204">或者，可以使用[复制和更新表达式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)从现有值创建新值。</span><span class="sxs-lookup"><span data-stu-id="ecd42-204">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="ecd42-205">与 for 数组一样，此类表达式会复制原始表达式的所有项值（指定的已命名项除外）。</span><span class="sxs-lookup"><span data-stu-id="ecd42-205">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="ecd42-206">对于这些值，这些值将设置为在表达式的右侧定义的值。</span><span class="sxs-lookup"><span data-stu-id="ecd42-206">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="ecd42-207">对于用户定义的类型中的命名项，还存在可用于数组项的任何其他语言结构（例如，[更新和重新分配语句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)）。</span><span class="sxs-lookup"><span data-stu-id="ecd42-207">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="ecd42-208">用户定义的类型可以在任何其他类型可以使用的任何地方使用。</span><span class="sxs-lookup"><span data-stu-id="ecd42-208">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="ecd42-209">具体而言，可以定义用户定义类型的数组，并将用户定义类型作为元组类型的元素包括在内。</span><span class="sxs-lookup"><span data-stu-id="ecd42-209">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="ecd42-210">注意无法创建递归类型结构。</span><span class="sxs-lookup"><span data-stu-id="ecd42-210">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="ecd42-211">也就是说，定义用户定义类型的类型不能是包含用户定义类型的元素的元组类型。</span><span class="sxs-lookup"><span data-stu-id="ecd42-211">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="ecd42-212">通常，用户定义类型可能没有彼此之间的循环依赖关系，因此以下类型定义将是非法的：</span><span class="sxs-lookup"><span data-stu-id="ecd42-212">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="ecd42-213">操作和函数类型</span><span class="sxs-lookup"><span data-stu-id="ecd42-213">Operation and Function Types</span></span>

<span data-ttu-id="ecd42-214">任何可调用的基本类型都编写为 `('Tinput => 'Tresult)` 或 `('Tinput -> 'Tresult)` ，其中 `'Tinput` 和 `'Tresult` 都是类型。</span><span class="sxs-lookup"><span data-stu-id="ecd42-214">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="ecd42-215">这些是可调用的*签名*。</span><span class="sxs-lookup"><span data-stu-id="ecd42-215">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="ecd42-216">所有 Q # callables 都视为采用单个值作为输入，并返回单个值作为输出。</span><span class="sxs-lookup"><span data-stu-id="ecd42-216">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="ecd42-217">输入和输出值都可以是元组。</span><span class="sxs-lookup"><span data-stu-id="ecd42-217">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="ecd42-218">不返回结果的 Callables `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-218">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="ecd42-219">不带输入的 Callables 将空元组作为输入。</span><span class="sxs-lookup"><span data-stu-id="ecd42-219">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="ecd42-220">第一个窗体（带有 `=>` ）用于操作; 第二个窗体用于 `->` 函数。</span><span class="sxs-lookup"><span data-stu-id="ecd42-220">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="ecd42-221">例如， `((Qubit, Pauli) => Result)` 表示可能的 qubit 测量操作的签名。</span><span class="sxs-lookup"><span data-stu-id="ecd42-221">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="ecd42-222">*函数*类型由其签名完全指定。</span><span class="sxs-lookup"><span data-stu-id="ecd42-222">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="ecd42-223">例如，计算角度正弦值的函数将具有类型 `(Double -> Double)` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-223">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="ecd42-224">*操作*---但不是函数---具有一些其他特征，这些特征表示为操作类型的一部分。</span><span class="sxs-lookup"><span data-stu-id="ecd42-224">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="ecd42-225">此类特征包括有关操作支持的*函子*的信息。</span><span class="sxs-lookup"><span data-stu-id="ecd42-225">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="ecd42-226">例如，如果可以将操作的执行条件设置为其他 qubits 的状态，则它应支持 `Controlled` 函子; 如果操作具有反向，则它应支持 `Adjoint` 函子。</span><span class="sxs-lookup"><span data-stu-id="ecd42-226">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="ecd42-227">在[Q # 中的操作和函数](xref:microsoft.quantum.guide.operationsfunctions)上详细讨论了函子和操作，但此处我们只讨论了如何更改操作签名。</span><span class="sxs-lookup"><span data-stu-id="ecd42-227">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="ecd42-228">为了要求对 `Controlled` 操作类型中的和/或 `Adjoint` 函子提供支持，我们需要添加一个批注，指示相应的特性。</span><span class="sxs-lookup"><span data-stu-id="ecd42-228">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="ecd42-229">批注 `is Ctl` （例如 `(Qubit => Unit is Ctl)` ）指示操作可控制---也就是说，它是在另一个 qubit 或 qubits 的状态下进行条件执行。</span><span class="sxs-lookup"><span data-stu-id="ecd42-229">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="ecd42-230">同样， `is Adj` 指示操作具有 adjoint; 或者，它可以是 "反转" 的，以便依次应用操作，并将其 adjoint 为状态使状态保持不变。</span><span class="sxs-lookup"><span data-stu-id="ecd42-230">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="ecd42-231">如果我们希望要求该类型的操作同时支持 `Adjoint` 和 `Controlled` 函子，我们可以将其表示为 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-231">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="ecd42-232">例如，内置 Pauli 操作的类型为 <xref:microsoft.quantum.intrinsic.x> `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-232">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="ecd42-233">不支持任何函子的操作类型由其输入和输出类型单独指定，无附加批注。</span><span class="sxs-lookup"><span data-stu-id="ecd42-233">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="ecd42-234">类型参数化的函数和操作</span><span class="sxs-lookup"><span data-stu-id="ecd42-234">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="ecd42-235">可调用类型可以包含类型参数。</span><span class="sxs-lookup"><span data-stu-id="ecd42-235">Callable types may contain type parameters.</span></span>
<span data-ttu-id="ecd42-236">类型参数由单个引号作为前缀的符号指示;例如， `'A` 是一个合法的类型参数。</span><span class="sxs-lookup"><span data-stu-id="ecd42-236">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="ecd42-237">有关定义类型参数化 callables 的详细信息，请在 "Q #" 页的 "[操作和函数" 中](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)提供。</span><span class="sxs-lookup"><span data-stu-id="ecd42-237">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="ecd42-238">类型参数可能在单个签名中出现多次。</span><span class="sxs-lookup"><span data-stu-id="ecd42-238">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="ecd42-239">例如，将其他函数应用于数组的每个元素并返回所收集结果的函数将具有签名 `(('A[], 'A->'A) -> 'A[])` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-239">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="ecd42-240">同样，返回两个运算的组合的函数可能具有签名 `((('A=>'B), ('B=>'C)) -> ('A=>'C))` 。</span><span class="sxs-lookup"><span data-stu-id="ecd42-240">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="ecd42-241">调用类型参数化的可调用时，具有相同类型参数的所有参数都必须具有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="ecd42-241">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="ecd42-242">Q # 不提供约束可能替换为类型参数的可能类型的机制。</span><span class="sxs-lookup"><span data-stu-id="ecd42-242">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="whats-next"></a><span data-ttu-id="ecd42-243">下一步是什么？</span><span class="sxs-lookup"><span data-stu-id="ecd42-243">What's Next?</span></span>
<span data-ttu-id="ecd42-244">现在，你已了解了所有类型，这些类型构成了 Q # 语言，你可以转到[q # 中的类型表达式](xref:microsoft.quantum.guide.expressions)，以了解如何创建和操作这些不同类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="ecd42-244">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


