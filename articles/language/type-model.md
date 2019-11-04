---
title: 'Q # 类型模型 |Microsoft Docs'
description: 'Q # 类型模型'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184740"
---
# <a name="the-type-model"></a><span data-ttu-id="fe0da-103">类型模型</span><span class="sxs-lookup"><span data-stu-id="fe0da-103">The Type Model</span></span>

<span data-ttu-id="fe0da-104">本部分介绍了 Q # 类型的模型，并介绍了用于指定和使用类型的语法。</span><span class="sxs-lookup"><span data-stu-id="fe0da-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="fe0da-105">我们注意到，Q # 是一种*强类型*语言，因此，仔细地使用这些类型可帮助编译器在编译时为 Q # 程序提供强大的保证。</span><span class="sxs-lookup"><span data-stu-id="fe0da-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="fe0da-106">为了尽可能提供最强的保证，在 Q # 中的类型之间进行转换时，必须使用对函数的调用来显式转换。</span><span class="sxs-lookup"><span data-stu-id="fe0da-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="fe0da-107">此类函数作为 <xref:microsoft.quantum.convert> 命名空间的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="fe0da-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="fe0da-108">另一方面，向上转换到兼容类型是隐式的。</span><span class="sxs-lookup"><span data-stu-id="fe0da-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="fe0da-109">Q # 提供了基元类型，可以直接使用，也可以通过多种方式从其他类型生成新类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="fe0da-110">本部分的其余部分介绍了每个。</span><span class="sxs-lookup"><span data-stu-id="fe0da-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="fe0da-111">基元类型</span><span class="sxs-lookup"><span data-stu-id="fe0da-111">Primitive Types</span></span>

<span data-ttu-id="fe0da-112">Q # 语言提供若干*基元类型*，可以从这些类型构造其他类型：</span><span class="sxs-lookup"><span data-stu-id="fe0da-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="fe0da-113">`Int` 类型表示64位有符号整数，例如： `2`、`107``-5`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="fe0da-114">`BigInt` 类型表示任意大小的有符号整数，如 `2L`、`107L``-5L`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="fe0da-115">此类型基于 .NET <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="fe0da-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="fe0da-116">类别.</span><span class="sxs-lookup"><span data-stu-id="fe0da-116">type.</span></span>
- <span data-ttu-id="fe0da-117">`Double` 类型表示双精度浮点数，例如： `0.0`、`-1.3``4e-7`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="fe0da-118">`Bool` 类型表示可 `true` 或 `false`的布尔值。</span><span class="sxs-lookup"><span data-stu-id="fe0da-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="fe0da-119">`Qubit` 类型表示量程位或 qubit。</span><span class="sxs-lookup"><span data-stu-id="fe0da-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="fe0da-120">用户不透明 `Qubit`;仅在将其传递给其他操作时，才可以对其进行操作，而不是将其传递到其他操作。</span><span class="sxs-lookup"><span data-stu-id="fe0da-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="fe0da-121">最终，对 `Qubit`的操作是通过对量程处理器（或其模拟）调用内部指令来实现的。</span><span class="sxs-lookup"><span data-stu-id="fe0da-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="fe0da-122">`Pauli` 类型表示四个 qubit Pauli 运算符之一。</span><span class="sxs-lookup"><span data-stu-id="fe0da-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="fe0da-123">此类型用于表示旋转的基本操作，并指定要测量的可观察对象。</span><span class="sxs-lookup"><span data-stu-id="fe0da-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="fe0da-124">这是一个枚举类型，它具有四个可能的值： `PauliI`、`PauliX`、`PauliY`和 `PauliZ`，它们是类型 `Pauli`的常量。</span><span class="sxs-lookup"><span data-stu-id="fe0da-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="fe0da-125">`Result` 类型表示度量值的结果。</span><span class="sxs-lookup"><span data-stu-id="fe0da-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="fe0da-126">这是具有两个可能值的枚举类型： `One` 和 `Zero`，它们是 `Result`类型的常量。</span><span class="sxs-lookup"><span data-stu-id="fe0da-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="fe0da-127">`Zero` 指示已度量 + 1 eigenvalue;`One` 指示-1 eigenvalue。</span><span class="sxs-lookup"><span data-stu-id="fe0da-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="fe0da-128">`Range` 类型表示由 `start..step..stop`表示的整数序列，其中表示步骤为选项。</span><span class="sxs-lookup"><span data-stu-id="fe0da-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="fe0da-129">这与 `start..1..stop``start .. stop` 相对应，例如 `1..2..7` 表示序列 $\{1、3、5、7\}$。</span><span class="sxs-lookup"><span data-stu-id="fe0da-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="fe0da-130">`String` 类型是一系列 Unicode 字符，在用户创建后不透明。</span><span class="sxs-lookup"><span data-stu-id="fe0da-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="fe0da-131">在发生错误或诊断事件时，此类型用于向传统主机报告消息。</span><span class="sxs-lookup"><span data-stu-id="fe0da-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="fe0da-132">`Unit` 类型是仅允许 `()`一个值的类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="fe0da-133">此类型用于指示 Q # 函数或操作不返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="fe0da-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="fe0da-134">常量 `true`、`false`、`PauliI`、`PauliX`、`PauliY`、`PauliZ`、`One`和 `Zero` 都是 Q # 中的所有保留符号。</span><span class="sxs-lookup"><span data-stu-id="fe0da-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="fe0da-135">数组类型</span><span class="sxs-lookup"><span data-stu-id="fe0da-135">Array Types</span></span>

<span data-ttu-id="fe0da-136">给定任意有效的 Q # 类型 `'T`，都有一个类型表示 `'T`类型的值数组。</span><span class="sxs-lookup"><span data-stu-id="fe0da-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="fe0da-137">此数组类型表示为 `'T[]`;例如，`Qubit[]` 或 `Int[][]`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="fe0da-138">例如，整数的集合 `Int[]`表示，而 `(Bool, Pauli)` 值数组的数组则 `(Bool, Pauli)[][]`表示。</span><span class="sxs-lookup"><span data-stu-id="fe0da-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="fe0da-139">在第二个示例中，请注意，这表示数组的可能交错数组，而不是矩形二维数组。</span><span class="sxs-lookup"><span data-stu-id="fe0da-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="fe0da-140">Q # 不提供对矩形多维数组的支持。</span><span class="sxs-lookup"><span data-stu-id="fe0da-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="fe0da-141">通过在数组的元素周围使用方括号（如 `[PauliI, PauliX, PauliY, PauliZ]`中所示），可以用 Q # 源代码来编写数组值。</span><span class="sxs-lookup"><span data-stu-id="fe0da-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="fe0da-142">数组文本的类型由数组中所有项的通用基类型决定。</span><span class="sxs-lookup"><span data-stu-id="fe0da-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="fe0da-143">创建数组后，不能更改数组的元素。</span><span class="sxs-lookup"><span data-stu-id="fe0da-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="fe0da-144">更新和重新分配语句和/或复制和更新表达式可用于构造修改后的数组。</span><span class="sxs-lookup"><span data-stu-id="fe0da-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="fe0da-145">或者，可以使用 `new` 关键字创建数组的大小：</span><span class="sxs-lookup"><span data-stu-id="fe0da-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="fe0da-146">在任一情况下，一旦构造了某个数组，就可以使用核心函数 `Length` 获取作为 `Int`的元素数。</span><span class="sxs-lookup"><span data-stu-id="fe0da-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="fe0da-147">数组可以使用方括号（带有类型 `Int` 或类型 `Range`的下标）作为下标，以获取包含数组元素子集的单个元素或新数组。</span><span class="sxs-lookup"><span data-stu-id="fe0da-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="fe0da-148">数组的下标是从零开始的：</span><span class="sxs-lookup"><span data-stu-id="fe0da-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="fe0da-149">元组类型</span><span class="sxs-lookup"><span data-stu-id="fe0da-149">Tuple Types</span></span>

<span data-ttu-id="fe0da-150">给定零个或多个不同类型 `T0`，`T1`，...，`Tn`，则可以将新的*元组类型*表示为 `(T0, T1, ..., Tn)`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="fe0da-151">用于构造新元组类型的类型本身可以是元组，如 `(Int, (Qubit, Qubit))`中所示。</span><span class="sxs-lookup"><span data-stu-id="fe0da-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="fe0da-152">但这种嵌套始终是有限的，因为在任何情况下，元组类型都不能包含自身。</span><span class="sxs-lookup"><span data-stu-id="fe0da-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="fe0da-153">新元组类型的值是由元组中每个类型的值序列构成的元组。</span><span class="sxs-lookup"><span data-stu-id="fe0da-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="fe0da-154">例如，`(3, false)` 是其类型为 `(Int, Bool)`元组类型的元组。</span><span class="sxs-lookup"><span data-stu-id="fe0da-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="fe0da-155">可以创建元组、数组的元组、子元组的元组等的数组。</span><span class="sxs-lookup"><span data-stu-id="fe0da-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="fe0da-156">从 Q # 0.3，`Unit` 是空元组的*类型*名称;`()` 用于空元组*值*。</span><span class="sxs-lookup"><span data-stu-id="fe0da-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="fe0da-157">元组实例是不可变的。</span><span class="sxs-lookup"><span data-stu-id="fe0da-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="fe0da-158">Q # 不提供在创建元组内容之后更改元组内容的机制。</span><span class="sxs-lookup"><span data-stu-id="fe0da-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="fe0da-159">元组是一种功能强大的概念，用于在整个 Q # 中将值组合成单个值，使其更易于传递。</span><span class="sxs-lookup"><span data-stu-id="fe0da-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="fe0da-160">特别是，使用元组表示法，可以表达每个操作和可调用只采用一个输入，并只返回一个输出。</span><span class="sxs-lookup"><span data-stu-id="fe0da-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="fe0da-161">单一实例元组等效</span><span class="sxs-lookup"><span data-stu-id="fe0da-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="fe0da-162">可以创建单一实例（单元素）元组，`('T1)`，如 `(5)` 或 `([1,2,3])`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="fe0da-163">不过，Q # 将单一实例元组视为完全等效于封闭类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe0da-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="fe0da-164">也就是说，`5` 和 `(5)`之间，或者在 `5` 和 `(((5)))`之间，或者在 `(5, (6))` 和 `(5, 6)`之间没有任何区别。</span><span class="sxs-lookup"><span data-stu-id="fe0da-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="fe0da-165">此等效性适用于所有用途，包括赋值和表达式。</span><span class="sxs-lookup"><span data-stu-id="fe0da-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="fe0da-166">与写入 `5+3`一样，编写 `(5)+3` 都是有效的，并且这两个表达式的计算结果都是 `8`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="fe0da-167">具体而言，这意味着，其输入元组或输出元组类型具有一个字段的操作或函数可以被视为采用单个参数或返回单个值。</span><span class="sxs-lookup"><span data-stu-id="fe0da-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="fe0da-168">我们将此属性称为_单独元组等效_。</span><span class="sxs-lookup"><span data-stu-id="fe0da-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="fe0da-169">用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="fe0da-169">User-Defined Types</span></span>

<span data-ttu-id="fe0da-170">Q # 文件可以定义包含任何合法类型的单个值的新命名类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="fe0da-171">对于任何元组类型 `T`，可以声明一个新的用户定义类型，该类型是具有 `newtype` 语句 `T` 的子类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="fe0da-172">例如，在 @"microsoft.quantum.canon" 命名空间中，复数定义为用户定义的类型：</span><span class="sxs-lookup"><span data-stu-id="fe0da-172">In the @"microsoft.quantum.canon" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="fe0da-173">此语句创建一个新类型，该类型具有两个 `Double`类型的匿名项。</span><span class="sxs-lookup"><span data-stu-id="fe0da-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="fe0da-174">除了匿名项以外，用户定义类型还支持从 Q # 版本0.7 或更高版本开始的命名项。</span><span class="sxs-lookup"><span data-stu-id="fe0da-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="fe0da-175">例如，对于表示复数实部和虚部 `Im` 的双精度值，我们可以将 `Re` 命名为：</span><span class="sxs-lookup"><span data-stu-id="fe0da-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="fe0da-176">为用户定义类型中的一个项命名并不意味着需要命名所有项-支持命名项和未命名项的任意组合。</span><span class="sxs-lookup"><span data-stu-id="fe0da-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="fe0da-177">此外，也可以将内部项命名为。</span><span class="sxs-lookup"><span data-stu-id="fe0da-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="fe0da-178">下面定义的类型 `Nested` （例如）具有基础类型 `(Double, (Int, String))`，其中仅命名 `Int` 类型的项，所有其他项都是匿名的。</span><span class="sxs-lookup"><span data-stu-id="fe0da-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="fe0da-179">命名项的优点是可以通过访问运算符 `::`直接访问它们。</span><span class="sxs-lookup"><span data-stu-id="fe0da-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="fe0da-180">为了访问匿名项，首先需要使用后缀运算符 `!`来提取换行值。</span><span class="sxs-lookup"><span data-stu-id="fe0da-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="fe0da-181">"解包" 运算符 `!`允许提取用户定义类型中包含的值。</span><span class="sxs-lookup"><span data-stu-id="fe0da-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="fe0da-182">此类 "解包" 表达式的类型为用户定义类型的基础类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="fe0da-183">解包运算符仅解包一层包装。</span><span class="sxs-lookup"><span data-stu-id="fe0da-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="fe0da-184">可以使用多个解包运算符来访问乘换行值。</span><span class="sxs-lookup"><span data-stu-id="fe0da-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="fe0da-185">对于实例：</span><span class="sxs-lookup"><span data-stu-id="fe0da-185">For instance:</span></span>

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

<span data-ttu-id="fe0da-186">有关更多详细信息，请查看有关[解包](xref:microsoft.quantum.language.expressions#unwrap-expressions)和[运算符优先级](xref:microsoft.quantum.language.expressions#operator-precedence)的部分。</span><span class="sxs-lookup"><span data-stu-id="fe0da-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="fe0da-187">可以通过调用相应的类型构造函数来创建用户定义类型的值：</span><span class="sxs-lookup"><span data-stu-id="fe0da-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="fe0da-188">或者，可以使用[复制和更新表达式](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)从现有值创建新值。</span><span class="sxs-lookup"><span data-stu-id="fe0da-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="fe0da-189">与 for 数组一样，此类表达式会复制原始表达式的所有项值（指定的已命名项除外）。</span><span class="sxs-lookup"><span data-stu-id="fe0da-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="fe0da-190">对于这些值，这些值将设置为在表达式的右侧定义的值。</span><span class="sxs-lookup"><span data-stu-id="fe0da-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="fe0da-191">对于用户定义的类型中的命名项，还存在可用于数组项的任何其他语言结构（例如，[更新和重新分配语句](xref:microsoft.quantum.language.statements#update-and-reassign-statement)）。</span><span class="sxs-lookup"><span data-stu-id="fe0da-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="fe0da-192">用户定义的类型可以在任何其他类型可以使用的任何地方使用。</span><span class="sxs-lookup"><span data-stu-id="fe0da-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="fe0da-193">具体而言，可以定义用户定义类型的数组，并将用户定义类型作为元组类型的元素包括在内。</span><span class="sxs-lookup"><span data-stu-id="fe0da-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="fe0da-194">无法创建递归类型结构。</span><span class="sxs-lookup"><span data-stu-id="fe0da-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="fe0da-195">也就是说，定义用户定义类型的类型不能是包含用户定义类型的元素的元组类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="fe0da-196">通常，用户定义类型可能没有彼此之间的循环依赖关系，因此以下类型定义将是非法的：</span><span class="sxs-lookup"><span data-stu-id="fe0da-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="fe0da-197">除了为可能复杂的元组类型提供短别名外，定义此类类型的一个明显优势在于它们可以记录特定值的意图。</span><span class="sxs-lookup"><span data-stu-id="fe0da-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="fe0da-198">返回到 `Complex`的示例中，一个还可以将2D 极坐标定义为用户定义的类型：</span><span class="sxs-lookup"><span data-stu-id="fe0da-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="fe0da-199">即使 `Complex` 和 `Polar` 都具有基础类型 `(Double, Double)`，两种类型在 Q # 中完全不兼容，最大限度地降低意外调用具有极坐标的复杂数学函数的风险，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="fe0da-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="fe0da-200">通过这种方式，用户定义类型与中F#的记录具有类似的角色，例如。</span><span class="sxs-lookup"><span data-stu-id="fe0da-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="fe0da-201">操作和函数类型</span><span class="sxs-lookup"><span data-stu-id="fe0da-201">Operation and Function Types</span></span>

<span data-ttu-id="fe0da-202">Q #_操作_是一个量程子例程。</span><span class="sxs-lookup"><span data-stu-id="fe0da-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="fe0da-203">也就是说，它是包含量程操作的可调用例程。</span><span class="sxs-lookup"><span data-stu-id="fe0da-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="fe0da-204">Q #_函数_是在量程算法中使用的传统子例程。</span><span class="sxs-lookup"><span data-stu-id="fe0da-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="fe0da-205">它可能包含传统代码，但不包含量程运算。</span><span class="sxs-lookup"><span data-stu-id="fe0da-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="fe0da-206">具体而言，函数不能分配或借用 qubits，也不能调用操作。</span><span class="sxs-lookup"><span data-stu-id="fe0da-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="fe0da-207">不过，可以通过这些操作或 qubits 来进行处理。</span><span class="sxs-lookup"><span data-stu-id="fe0da-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="fe0da-208">函数是完全确定的，因此调用具有相同参数的函数将始终产生相同的结果。</span><span class="sxs-lookup"><span data-stu-id="fe0da-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="fe0da-209">操作和函数共同称为_callables_。</span><span class="sxs-lookup"><span data-stu-id="fe0da-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="fe0da-210">可以在下面查看一些[示例](#examples)。</span><span class="sxs-lookup"><span data-stu-id="fe0da-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="fe0da-211">所有 Q # callables 都视为采用单个值作为输入，并返回单个值作为输出。</span><span class="sxs-lookup"><span data-stu-id="fe0da-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="fe0da-212">输入和输出值都可以是元组。</span><span class="sxs-lookup"><span data-stu-id="fe0da-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="fe0da-213">不 `Unit`返回结果的 Callables。</span><span class="sxs-lookup"><span data-stu-id="fe0da-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="fe0da-214">不带输入的 Callables 将空元组作为输入。</span><span class="sxs-lookup"><span data-stu-id="fe0da-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="fe0da-215">任何可调用的基本类型都编写为 `('Tinput => 'Tresult)` 或 `('Tinput -> 'Tresult)`，其中 `'Tinput` 和 `'Tresult` 都是类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="fe0da-216">第一种窗体（带有 `=>`）用于操作;函数的第二个窗体，其中包含 `->`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="fe0da-217">例如，`((Qubit, Pauli) => Result)` 表示可能的 qubit 测量操作的签名。</span><span class="sxs-lookup"><span data-stu-id="fe0da-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="fe0da-218">函数类型由其签名完全指定。</span><span class="sxs-lookup"><span data-stu-id="fe0da-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="fe0da-219">例如，计算角度正弦值的函数的类型 `(Double -> Double)`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="fe0da-220">操作（但不是函数）具有某些其他特征，这些_特征_表示为操作类型的一部分。</span><span class="sxs-lookup"><span data-stu-id="fe0da-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="fe0da-221">此类特征包括有关操作支持的函子的信息。</span><span class="sxs-lookup"><span data-stu-id="fe0da-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="fe0da-222">函子是生成基本操作专用化的元操作;请参阅下面的[函子](#functors)。</span><span class="sxs-lookup"><span data-stu-id="fe0da-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="fe0da-223">操作类型由其输入类型、输出类型及其特征来指定。</span><span class="sxs-lookup"><span data-stu-id="fe0da-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="fe0da-224">为了要求对操作类型中的 `Controlled` 和/或 `Adjoint` 函子提供支持，我们需要添加一个批注以指示相应的特性。</span><span class="sxs-lookup"><span data-stu-id="fe0da-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="fe0da-225">批注 `is Ctl` 例如，指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="fe0da-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="fe0da-226">如果希望要求该类型的操作同时支持 `Adjoint` 和 `Controlled` 函子，我们可以将其表示为 `(Qubit => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="fe0da-227">已使用的操作特征 `Adj` 和 `Ctl` 严格地说，这是两个预定义的标签集，其中每个标签都指示特定操作特征，如对特定函子的支持。</span><span class="sxs-lookup"><span data-stu-id="fe0da-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="fe0da-228">因此，`+` 用于指示这两个集的并集，并且 `*` 用于指示交集（即这两个集共有的标签）。</span><span class="sxs-lookup"><span data-stu-id="fe0da-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="fe0da-229">例如，Pauli `X` 操作的类型 `(Qubit => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="fe0da-230">不支持任何函子的操作类型由其输入和输出类型单独指定，无附加批注。</span><span class="sxs-lookup"><span data-stu-id="fe0da-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="fe0da-231">类型参数化的函数和操作</span><span class="sxs-lookup"><span data-stu-id="fe0da-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="fe0da-232">可调用类型可以包含类型参数。</span><span class="sxs-lookup"><span data-stu-id="fe0da-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="fe0da-233">类型参数由单个引号作为前缀的符号指示;例如，`'A` 是合法的类型参数。</span><span class="sxs-lookup"><span data-stu-id="fe0da-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="fe0da-234">类型参数可能在单个签名中出现多次。</span><span class="sxs-lookup"><span data-stu-id="fe0da-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="fe0da-235">例如，将另一个函数应用于数组的每个元素并返回所收集结果的函数将 `(('A[], 'A->'A) -> 'A[])`签名。</span><span class="sxs-lookup"><span data-stu-id="fe0da-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="fe0da-236">同样，返回两个操作的组合的函数可能具有签名 `((('A=>'B), ('B=>'C)) -> ('A=>'C))`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="fe0da-237">调用类型参数化的可调用时，具有相同类型参数的所有参数都必须具有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="fe0da-238">Q # 不提供约束可能替换为类型参数的可能类型的机制。</span><span class="sxs-lookup"><span data-stu-id="fe0da-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="fe0da-239">类型兼容性</span><span class="sxs-lookup"><span data-stu-id="fe0da-239">Type Compatibility</span></span>

<span data-ttu-id="fe0da-240">具有更多函子支持的操作可能会在具有较少函子但需要相同签名的操作的任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="fe0da-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="fe0da-241">例如，类型 `(Qubit => Unit is Adj)` 的操作可在需要 `(Qubit => Unit)` 类型的操作的任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="fe0da-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="fe0da-242">Q # 对于可调用的返回类型是协变的：返回类型 `'A` 的可调用与具有相同输入类型的可调用和与 `'A` 兼容的结果类型兼容。</span><span class="sxs-lookup"><span data-stu-id="fe0da-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="fe0da-243">Q # 对于输入类型是逆变的：使用类型 `'A` 作为输入的可调用与具有相同结果类型的可调用和与 `'A`兼容的输入类型兼容。</span><span class="sxs-lookup"><span data-stu-id="fe0da-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="fe0da-244">也就是说，提供以下定义：</span><span class="sxs-lookup"><span data-stu-id="fe0da-244">That is, given the following definitions:</span></span>

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="fe0da-245">以下为 true：</span><span class="sxs-lookup"><span data-stu-id="fe0da-245">the following are true:</span></span>

- <span data-ttu-id="fe0da-246">可以使用 `Invertible` 或 `Unitary`的 `inner` 参数调用操作 `ConjugateInvertibleWith`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-246">The operation `ConjugateInvertibleWith` may be invoked with an `inner` argument of either `Invertible` or `Unitary`.</span></span>
- <span data-ttu-id="fe0da-247">可以使用 `Unitary`的 `inner` 参数调用 `ConjugateUnitaryWith` 操作，但是不能 `Invertible`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-247">The operation `ConjugateUnitaryWith` may be invoked with an `inner` argument of `Unitary`, but not `Invertible`.</span></span>
- <span data-ttu-id="fe0da-248">类型 `(Qubit[] => Unit is Adj + Ctl)` 的值可能从 `ConjugateInvertibleWith`返回。</span><span class="sxs-lookup"><span data-stu-id="fe0da-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertibleWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe0da-249">Q # 0.3 在用户定义类型的行为上引入了显著的差异。</span><span class="sxs-lookup"><span data-stu-id="fe0da-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="fe0da-250">用户定义的类型被视为基础类型的包装版本，而不是作为子类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="fe0da-251">这意味着，如果需要基础类型的值，用户定义类型的值将无法使用。</span><span class="sxs-lookup"><span data-stu-id="fe0da-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="fe0da-252">函子</span><span class="sxs-lookup"><span data-stu-id="fe0da-252">Functors</span></span>

<span data-ttu-id="fe0da-253">Q # 中的函子是一个工厂，它定义了其他操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="fe0da-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="fe0da-254">在定义新操作的实现时，函子有权访问基操作的实现。</span><span class="sxs-lookup"><span data-stu-id="fe0da-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="fe0da-255">因此，函子可以比传统的高级函数执行更复杂的功能。</span><span class="sxs-lookup"><span data-stu-id="fe0da-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="fe0da-256">函子在 Q # 类型系统中没有表示形式。</span><span class="sxs-lookup"><span data-stu-id="fe0da-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="fe0da-257">因此，目前不可能将其绑定到变量或将其作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="fe0da-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="fe0da-258">函子可通过将其应用于操作来使用，返回新操作。</span><span class="sxs-lookup"><span data-stu-id="fe0da-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="fe0da-259">例如，将 `Adjoint` 函子应用到 `Y` 操作而生成的操作将以 `Adjoint Y`形式写入。</span><span class="sxs-lookup"><span data-stu-id="fe0da-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="fe0da-260">然后，可以像任何其他操作一样调用新操作。</span><span class="sxs-lookup"><span data-stu-id="fe0da-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="fe0da-261">因此，`Adjoint Y(q1)` 将 Adjoint 函子应用于 `Y` 操作以生成新的操作，并将该新操作应用于 `q1`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="fe0da-262">同样，`Controlled X(controls, target)` 将控制的函子应用于 `X` 操作以生成新的操作，并将该新操作应用到 `controls` 和 `target`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="fe0da-263">Q # 中的两个标准函子是 `Adjoint` 和 `Controlled`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="fe0da-264">Adjoint</span><span class="sxs-lookup"><span data-stu-id="fe0da-264">Adjoint</span></span>

<span data-ttu-id="fe0da-265">在量程计算中，操作的 adjoint 是操作的复杂共轭转置。</span><span class="sxs-lookup"><span data-stu-id="fe0da-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="fe0da-266">对于实现单一运算符的操作，adjoint 是操作的反向操作。</span><span class="sxs-lookup"><span data-stu-id="fe0da-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="fe0da-267">对于只调用一组 qubits 上的其他单一操作序列的简单操作，可以通过在反向序列中对同一 qubits 应用子操作的 adjoints 来计算 adjoint。</span><span class="sxs-lookup"><span data-stu-id="fe0da-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="fe0da-268">给定一个操作表达式，可以使用 `Adjoint` 函子生成新的操作表达式。</span><span class="sxs-lookup"><span data-stu-id="fe0da-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="fe0da-269">例如，`Adjoint QFT` 指定 `QFT` 操作的 adjoint。</span><span class="sxs-lookup"><span data-stu-id="fe0da-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="fe0da-270">新操作与基本操作具有相同的签名和类型。</span><span class="sxs-lookup"><span data-stu-id="fe0da-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="fe0da-271">具体而言，新操作还允许 `Adjoint`，并且仅当基本操作执行时才允许 `Controlled`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="fe0da-272">Adjoint 函子是其自身的反向;也就是说，`Adjoint Adjoint Op` 始终与 `Op`相同。</span><span class="sxs-lookup"><span data-stu-id="fe0da-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="fe0da-273">操控</span><span class="sxs-lookup"><span data-stu-id="fe0da-273">Controlled</span></span>

<span data-ttu-id="fe0da-274">操作的受控版本是新操作，仅当所有控件 qubits 都处于指定状态时，才会有效地应用基本操作。</span><span class="sxs-lookup"><span data-stu-id="fe0da-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="fe0da-275">如果控件 qubits 在 superposition 中，则会将基本操作一致应用到 superposition 的相应部分。</span><span class="sxs-lookup"><span data-stu-id="fe0da-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="fe0da-276">因此，受控操作通常用于生成牵连。</span><span class="sxs-lookup"><span data-stu-id="fe0da-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="fe0da-277">在 Q # 中，受控版本始终采用控制 qubits 的数组，并且指定的状态始终为所有控件 qubits 都处于计算（`PauliZ`） `One` 状态，$ \ket{1}$。</span><span class="sxs-lookup"><span data-stu-id="fe0da-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="fe0da-278">可以通过将适当的单一操作应用于受控操作之前的控件 qubits 来实现基于其他状态的控制，然后在受控操作后应用单一操作的逆。</span><span class="sxs-lookup"><span data-stu-id="fe0da-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="fe0da-279">例如，在受控操作前后将 `X` 操作应用于控件 qubit，将导致操作控制该 qubit 的 `Zero` 状态（$ \ket{0}$）;应用 `H` 操作之前和之后，将控制 `PauliX` `One` 状态，即 Pauli X，$ \ket{-} \mathrel{： =} （\ket{0}-\ket{1}）/\sqrt{2}$ 而不是 `PauliZ` `One` 状态。</span><span class="sxs-lookup"><span data-stu-id="fe0da-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="fe0da-280">给定一个操作表达式，可以使用 `Controlled` 函子生成新的操作表达式。</span><span class="sxs-lookup"><span data-stu-id="fe0da-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="fe0da-281">新操作的签名基于原始操作的签名。</span><span class="sxs-lookup"><span data-stu-id="fe0da-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="fe0da-282">结果类型是相同的，但输入类型是具有 qubit 数组的两元组，它将控件 qubit 保存为第一个元素，并将原始操作的参数作为第二个元素。</span><span class="sxs-lookup"><span data-stu-id="fe0da-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="fe0da-283">新操作支持 `Controlled`，且仅当原始操作执行时才支持 `Adjoint`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="fe0da-284">如果原始操作只使用了一个参数，则会在此处播放单独的元组等效性。</span><span class="sxs-lookup"><span data-stu-id="fe0da-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="fe0da-285">例如，`Controlled X` 是 `X` 操作的受控版本。</span><span class="sxs-lookup"><span data-stu-id="fe0da-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="fe0da-286">`X` 具有类型 `(Qubit => Unit is Adj + Ctl)`，因此 `Controlled X` 具有类型 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`;由于单独的元组等效，这与 `((Qubit[], Qubit) => Unit is Adj + Ctl)`相同。</span><span class="sxs-lookup"><span data-stu-id="fe0da-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="fe0da-287">如果基本操作采用多个参数，请记住将操作的受控版本的相应参数括在括号中，以将其转换为元组。</span><span class="sxs-lookup"><span data-stu-id="fe0da-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="fe0da-288">例如，`Controlled Rz` 是 `Rz` 操作的受控版本。</span><span class="sxs-lookup"><span data-stu-id="fe0da-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="fe0da-289">`Rz` 具有类型 `((Double, Qubit) => Unit is Adj + Ctl)`，因此 `Controlled Rz` 具有类型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="fe0da-290">因此，`Controlled Rz(controls, (0.1, target))` 是 `Controlled Rz` 的有效调用（请注意 `0.1, target`之间的括号）。</span><span class="sxs-lookup"><span data-stu-id="fe0da-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="fe0da-291">作为另一个示例，可以按 `Controlled X([control], target)`实现 `CNOT(control, target)`。</span><span class="sxs-lookup"><span data-stu-id="fe0da-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="fe0da-292">如果目标应由2个 control qubits （CCNOT）控制，则可以使用 `Controlled X([control1, control2], target)` 语句。</span><span class="sxs-lookup"><span data-stu-id="fe0da-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="fe0da-293">示例</span><span class="sxs-lookup"><span data-stu-id="fe0da-293">Examples</span></span>

<span data-ttu-id="fe0da-294">此 Q # 操作示例来自[测量](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement)示例。</span><span class="sxs-lookup"><span data-stu-id="fe0da-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="fe0da-295">在操作中，可以分配 qubits 并对这些 qubits （如 `H` 和 `X`）使用量程操作：</span><span class="sxs-lookup"><span data-stu-id="fe0da-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit

            set result = M(qubit);      // Measure the qubit

            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="fe0da-296">此函数示例来自[PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)示例。</span><span class="sxs-lookup"><span data-stu-id="fe0da-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="fe0da-297">它包含纯传统代码。</span><span class="sxs-lookup"><span data-stu-id="fe0da-297">It contains purely classical code.</span></span> <span data-ttu-id="fe0da-298">您可以看到，与上面的示例不同，不会分配任何 qubits，也不会使用任何量程运算。</span><span class="sxs-lookup"><span data-stu-id="fe0da-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="fe0da-299">还可以将函数传递给 qubits 以进行处理，如本示例中的[ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis)示例。</span><span class="sxs-lookup"><span data-stu-id="fe0da-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="fe0da-300">Qubits 会传递到函数并用于处理，不过，在任何时候都不会修改 qubit 状态。</span><span class="sxs-lookup"><span data-stu-id="fe0da-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
