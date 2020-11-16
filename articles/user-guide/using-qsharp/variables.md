---
title: '中的变量 Q#'
description: '了解如何使用中的不同变量 Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 67c71c09e004d77360902360fefc7a7752e4a829
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690934"
---
# <a name="variables-in-no-locq"></a><span data-ttu-id="39242-103">中的变量 Q#</span><span class="sxs-lookup"><span data-stu-id="39242-103">Variables in Q#</span></span>

<span data-ttu-id="39242-104">Q# 区分可变和不可变的符号（或 *变量* ，它们被绑定/分配到表达式）。</span><span class="sxs-lookup"><span data-stu-id="39242-104">Q# distinguishes between mutable and immutable symbols, or *variables* , which are bound/assigned to expressions.</span></span>
<span data-ttu-id="39242-105">通常，建议使用不可变符号，因为它允许编译器执行更多优化。</span><span class="sxs-lookup"><span data-stu-id="39242-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="39242-106">绑定的左侧由一个符号元组和一个表达式的右侧组成。</span><span class="sxs-lookup"><span data-stu-id="39242-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="39242-107">不可变变量</span><span class="sxs-lookup"><span data-stu-id="39242-107">Immutable Variables</span></span>

<span data-ttu-id="39242-108">您可以通过使用关键字，将中任何类型的值分配 Q# 给变量以便在操作或函数内重复使用 `let` 。</span><span class="sxs-lookup"><span data-stu-id="39242-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="39242-109">不可变绑定包含关键字 `let` ，后跟符号或符号元组、等号 `=` 、用于将 (符号绑定到) 的表达式以及终止分号。</span><span class="sxs-lookup"><span data-stu-id="39242-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="39242-110">例如：</span><span class="sxs-lookup"><span data-stu-id="39242-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="39242-111">这会将 Pauli 运算符的特定数组分配给变量名 (或 "symbol" ) `measurementOperator` 。</span><span class="sxs-lookup"><span data-stu-id="39242-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="39242-112">在前面的示例中，无需显式指定新变量的类型，因为语句右侧的表达式 `let` 是明确的，编译器将推断正确的类型。</span><span class="sxs-lookup"><span data-stu-id="39242-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="39242-113">使用定义的变量 `let` 是 *不可变* 的，这意味着，定义后，不能再以任何方式对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="39242-113">Variables defined using `let` are *immutable* , meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="39242-114">这可以实现多个有利的优化，包括对要对变量进行排序以便应用操作变体的传统逻辑的优化 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="39242-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="39242-115">可变变量</span><span class="sxs-lookup"><span data-stu-id="39242-115">Mutable Variables</span></span>

<span data-ttu-id="39242-116">作为使用创建变量的替代方法 `let` ， `mutable` 关键字创建一个可变变量，该变量在最初使用关键字创建后 *可以* 重新绑定 `set` 。</span><span class="sxs-lookup"><span data-stu-id="39242-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="39242-117">稍后可将在语句中声明并绑定的符号重新绑定 `mutable` 到代码中的其他值。</span><span class="sxs-lookup"><span data-stu-id="39242-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="39242-118">如果稍后在代码中重新绑定符号，则其类型不会更改，并且新绑定的值必须与该类型兼容。</span><span class="sxs-lookup"><span data-stu-id="39242-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="39242-119">重新绑定可变符号</span><span class="sxs-lookup"><span data-stu-id="39242-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="39242-120">您可以使用语句重新绑定可变变量 `set` 。</span><span class="sxs-lookup"><span data-stu-id="39242-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="39242-121">此类重新绑定包含关键字 `set` ，后跟符号或符号元组、等号 `=` 、用于将符号重新绑定到)  (的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="39242-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="39242-122">下面是重新绑定语句方法的一些示例。</span><span class="sxs-lookup"><span data-stu-id="39242-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="39242-123">应用和重新分配语句</span><span class="sxs-lookup"><span data-stu-id="39242-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="39242-124">`set`如果右侧包含二元运算符的应用程序，则特定类型的语句（即 *apply 和重新分配* 语句）提供了一种简便的连接方式，并将结果重新绑定到运算符的左侧参数。</span><span class="sxs-lookup"><span data-stu-id="39242-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="39242-125">例如，</span><span class="sxs-lookup"><span data-stu-id="39242-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="39242-126">`counter`在循环的每次迭代中递增计数器的值 `for` 。</span><span class="sxs-lookup"><span data-stu-id="39242-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="39242-127">前面的代码等效于</span><span class="sxs-lookup"><span data-stu-id="39242-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="39242-128">类似的语句适用于所有的二元运算符，其中左侧的类型与表达式类型匹配。</span><span class="sxs-lookup"><span data-stu-id="39242-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="39242-129">这些语句提供了一种简便的方法来累计值。</span><span class="sxs-lookup"><span data-stu-id="39242-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="39242-130">例如，supposing `qubits` 是 qubits 的一种注册：</span><span class="sxs-lookup"><span data-stu-id="39242-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="39242-131">更新和重新分配语句</span><span class="sxs-lookup"><span data-stu-id="39242-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="39242-132">在右侧的 [复制和更新表达式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 中存在类似的连接。</span><span class="sxs-lookup"><span data-stu-id="39242-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="39242-133">相应地，对于用户定义的类型中的 *命名项* 以及 *数组项* ，都存在 *更新和重新分配* 语句。</span><span class="sxs-lookup"><span data-stu-id="39242-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items* .</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="39242-134">对于数组， [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) 在标准库中， Q# 可以为许多常见数组初始化和操作需要提供所需的工具，从而有助于避免第一次更新数组项。</span><span class="sxs-lookup"><span data-stu-id="39242-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="39242-135">如果需要，更新和重新分配语句提供了一种替代方法：</span><span class="sxs-lookup"><span data-stu-id="39242-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="39242-136">例如，使用中提供的数组的库工具， [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) 可以轻松地定义一个函数，该函数返回一个类型数组，该数组的 `Pauli` 索引处的元素 `i` 采用给定的 `Pauli` 值，其他所有项都是 (`PauliI`) 的标识。</span><span class="sxs-lookup"><span data-stu-id="39242-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="39242-137">下面是此类函数的两个定义，第二个是利用我们的处理工具。</span><span class="sxs-lookup"><span data-stu-id="39242-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

<span data-ttu-id="39242-138">您可以改为使用 from 来创建类型数组，而不是遍历数组中的每个索引，并有条件地将其设置为 `PauliI` 或给定 `pauli` ，而 `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) `PauliI` 只需返回已在索引中更改了特定值的复制和更新表达式 `location` ：</span><span class="sxs-lookup"><span data-stu-id="39242-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="39242-139">元组析构</span><span class="sxs-lookup"><span data-stu-id="39242-139">Tuple Deconstruction</span></span>

<span data-ttu-id="39242-140">除了分配单个变量外，还可以使用 `let` 和 `mutable` 关键字（或任何其他绑定构造，如）将 `set` [元组类型](xref:microsoft.quantum.guide.types#tuple-types)的内容解压缩。</span><span class="sxs-lookup"><span data-stu-id="39242-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="39242-141">此窗体的赋值被称为 *析构* 该元组的元素。</span><span class="sxs-lookup"><span data-stu-id="39242-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="39242-142">如果绑定右侧是元组，则可以在赋值时析构该元组。</span><span class="sxs-lookup"><span data-stu-id="39242-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="39242-143">此类 deconstructions 可以涉及嵌套元组，只要右侧的元组形状与符号元组的形状兼容，所有完整或部分析构都有效。</span><span class="sxs-lookup"><span data-stu-id="39242-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="39242-144">例如：</span><span class="sxs-lookup"><span data-stu-id="39242-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="39242-145">绑定范围</span><span class="sxs-lookup"><span data-stu-id="39242-145">Binding Scopes</span></span>

<span data-ttu-id="39242-146">通常，符号绑定超出范围，并且在中出现的语句块的末尾变为不起作用。</span><span class="sxs-lookup"><span data-stu-id="39242-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="39242-147">此规则有两种例外情况：</span><span class="sxs-lookup"><span data-stu-id="39242-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="39242-148">循环的循环变量的绑定处于 `for` for 循环的主体的范围内，但不在循环结束后。</span><span class="sxs-lookup"><span data-stu-id="39242-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="39242-149">循环的所有三个部分 `repeat` / `until` (主体、测试和修正) 视为单个作用域，因此，在主体中绑定的符号可用于测试中，并提供修正。</span><span class="sxs-lookup"><span data-stu-id="39242-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="39242-150">对于这两种类型的循环，每次循环都在其自己的作用域中运行，因此更早传递中的绑定在稍后的传递中不可用。</span><span class="sxs-lookup"><span data-stu-id="39242-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="39242-151">有关这些循环的详细信息，请参阅 [控制流](xref:microsoft.quantum.guide.controlflow)。</span><span class="sxs-lookup"><span data-stu-id="39242-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="39242-152">内部块从外部块继承符号绑定。</span><span class="sxs-lookup"><span data-stu-id="39242-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="39242-153">每个块只能绑定一个符号;定义与作用域中的另一个符号名称相同的符号是非法的， (不 ) "隐藏"。</span><span class="sxs-lookup"><span data-stu-id="39242-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="39242-154">以下顺序是合法的：</span><span class="sxs-lookup"><span data-stu-id="39242-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="39242-155">和</span><span class="sxs-lookup"><span data-stu-id="39242-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="39242-156">但这是非法的：</span><span class="sxs-lookup"><span data-stu-id="39242-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="39242-157">如下所示：</span><span class="sxs-lookup"><span data-stu-id="39242-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="39242-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="39242-158">Next steps</span></span>

<span data-ttu-id="39242-159">了解如何使用中 [的 Qubits](xref:microsoft.quantum.guide.qubits) Q# 。</span><span class="sxs-lookup"><span data-stu-id="39242-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>