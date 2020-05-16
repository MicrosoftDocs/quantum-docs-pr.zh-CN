---
title: 问答中的变量#
description: 填充说明
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430894"
---
# <a name="variables-in-q"></a><span data-ttu-id="fdcf2-103">问答中的变量#</span><span class="sxs-lookup"><span data-stu-id="fdcf2-103">Variables in Q#</span></span>

<span data-ttu-id="fdcf2-104">Q # 区分可变和不可变符号，或 "变量" （绑定/分配到表达式）。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-104">Q# distinguishes between mutable and immutable symbols, or "variables", which are bound/assigned to expressions.</span></span>
<span data-ttu-id="fdcf2-105">通常，建议使用不可变符号，因为它允许编译器执行更多优化。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="fdcf2-106">绑定的左侧由符号元组和表达式的右侧组成的位置组成。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-106">The left-hand-side of a binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="fdcf2-107">不可变变量</span><span class="sxs-lookup"><span data-stu-id="fdcf2-107">Immutable Variables</span></span>

<span data-ttu-id="fdcf2-108">使用关键字，可以将 Q # 中任何类型的值分配给变量以便在操作或函数中重复使用 `let` 。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-108">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>

<span data-ttu-id="fdcf2-109">不可变绑定包含关键字 `let` ，后跟符号或符号元组、等号 `=` 、要将符号绑定到的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="fdcf2-110">例如：</span><span class="sxs-lookup"><span data-stu-id="fdcf2-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="fdcf2-111">这会将一个特定的 Pauli 运算符数组分配给变量名（或 "symbol"） `measurementOperator` 。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="fdcf2-112">我们不需要显式指定新变量的类型，因为语句右侧的表达式 `let` 是明确的，并且该类型由编译器推断。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-112">We did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="fdcf2-113">使用定义的变量 `let` 是*不可变*的，也就是说，定义后，将无法再以任何方式对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-113">Variables defined using `let` are *immutable*, meaning that once it has been defined, it can no longer be changed in any way.</span></span>
<span data-ttu-id="fdcf2-114">这允许实现多种优化，包括对要重新排序的变量进行优化，以便应用 `Adjoint` 操作的变体。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-114">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="fdcf2-115">可变变量</span><span class="sxs-lookup"><span data-stu-id="fdcf2-115">Mutable Variables</span></span>

<span data-ttu-id="fdcf2-116">作为使用创建变量的替代方法 `let` ， `mutable` 关键字将创建一个可变变量，该变量在最初使用关键字创建后*可*重新绑定 `set` 。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-116">As an alternative to creating a variable with `let`, the `mutable` keyword will create a mutable variable that *can* be re-bound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="fdcf2-117">声明并作为语句的一部分绑定的符号 `mutable` 可能会在后面的代码中重新绑定到不同的值。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-117">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> <span data-ttu-id="fdcf2-118">如果稍后在代码中重新绑定符号，则其类型不会更改，并且新绑定的值需要与该类型兼容。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="fdcf2-119">重新绑定可变符号</span><span class="sxs-lookup"><span data-stu-id="fdcf2-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="fdcf2-120">可以使用语句重新绑定可变变量 `set` 。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-120">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="fdcf2-121">此类重新绑定包含关键字 `set` ，后跟符号或符号元组、等号、将 `=` 符号重新绑定到的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="fdcf2-122">在这里，我们提供了一些可能的重新绑定语句技术示例</span><span class="sxs-lookup"><span data-stu-id="fdcf2-122">Here, we provide some possible examples of rebinding statement techniques</span></span>

### <a name="apply-and-reassign-statements"></a><span data-ttu-id="fdcf2-123">应用和重新分配语句</span><span class="sxs-lookup"><span data-stu-id="fdcf2-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="fdcf2-124">`set`如果右侧包含二元运算符的应用程序，并将结果重新绑定到运算符的左侧参数，则我们将一种特定类型的语句称为 "*应用" 和 "重新分配*" 语句。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-124">A particular kind of `set`-statement we refer to as an *apply-and-reassign* statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="fdcf2-125">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="fdcf2-125">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="fdcf2-126">`counter`在循环的每次迭代中递增计数器的值 `for` 。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="fdcf2-127">上述代码等效于</span><span class="sxs-lookup"><span data-stu-id="fdcf2-127">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="fdcf2-128">类似的语句可用于所有的二元运算符，其中左侧的类型与表达式类型匹配。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-128">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="fdcf2-129">这为示例提供了一种简单的方法来累计值。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-129">This provides for example a convenient way to accumulate values.</span></span>

<span data-ttu-id="fdcf2-130">例如，supposing `qubits` 是 qubits 的 regsiter：</span><span class="sxs-lookup"><span data-stu-id="fdcf2-130">For example, supposing `qubits` is a regsiter of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a><span data-ttu-id="fdcf2-131">更新和重新分配语句</span><span class="sxs-lookup"><span data-stu-id="fdcf2-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="fdcf2-132">在右侧的[复制和更新表达式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)中存在类似的连接。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand-side.</span></span>
<span data-ttu-id="fdcf2-133">相应地，对于用户定义的类型中的*命名项*以及*数组项*，都存在*更新和重新分配*语句。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

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

<span data-ttu-id="fdcf2-134">对于数组， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 在标准库中，可以为许多常见数组初始化和操作需求提供必要的工具，从而有助于避免第一次更新数组项。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in our standard libraries provides the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="fdcf2-135">如果需要，更新和重新分配语句提供了一种替代方法：</span><span class="sxs-lookup"><span data-stu-id="fdcf2-135">Update-and-reassign statements provide an alternative if needed:</span></span>

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

<span data-ttu-id="fdcf2-136">例如，使用在中提供的数组的库工具， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 可以轻松地定义一个函数，该函数返回一个 Paulis 数组，其中 Pauli 的索引 `i` 采用给定值，所有其他项都是标识。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can, for example, easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity.</span></span>

<span data-ttu-id="fdcf2-137">下面是此类函数的两个定义，第二个是利用我们的处理工具。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

<span data-ttu-id="fdcf2-138">我们可以使用 from 创建的数组，而不是循环访问数组中的每个索引，并有条件地将其设置为 `PauliI` 或 `Pauli` ，而只是 `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) `PauliI` 返回一个复制和更新表达式，在此表达式中，我们在索引处更改了特定值 `location` ：</span><span class="sxs-lookup"><span data-stu-id="fdcf2-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or `Pauli`, we can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI`'s, and then simply returning a copy-and-update expression in which we've changed the specifc value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="fdcf2-139">元组析构</span><span class="sxs-lookup"><span data-stu-id="fdcf2-139">Tuple Deconstruction</span></span>

<span data-ttu-id="fdcf2-140">除了分配单个变量外， `let` 和 `mutable` 关键字---或事实上任何其他绑定构造，如 `set` （如下所述）---还允许将[元组类型](xref:microsoft.quantum.guide.types#tuple-types)的内容解包。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-140">In addition to assigning a single variable, the `let` and `mutable` keywords---or in fact any other binding construct, such as `set` (described below)---also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="fdcf2-141">此窗体的赋值被称为*析构*该元组的元素。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="fdcf2-142">如果绑定的右侧是一个元组，则该元组可能在赋值时是析构的。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-142">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="fdcf2-143">此类 deconstructions 可能涉及嵌套元组，只要右侧的元组形状与符号元组的形状兼容，所有完整或部分析构都有效。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-143">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="fdcf2-144">例如：</span><span class="sxs-lookup"><span data-stu-id="fdcf2-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="fdcf2-145">绑定范围</span><span class="sxs-lookup"><span data-stu-id="fdcf2-145">Binding Scopes</span></span>

<span data-ttu-id="fdcf2-146">通常，符号绑定超出范围，并且在中出现的语句块的末尾变为不起作用。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="fdcf2-147">此规则有两种例外情况：</span><span class="sxs-lookup"><span data-stu-id="fdcf2-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="fdcf2-148">循环的循环变量的绑定处于 `for` for 循环的主体的范围内，但不在循环结束后。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="fdcf2-149">循环的所有三个部分 `repeat` / `until` （正文、测试和修正）被视为单个作用域，因此，在主体中绑定的符号在测试中可用，在修正中可用。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="fdcf2-150">对于这两种类型的循环，每次循环都在其自己的作用域中执行，因此更早传递中的绑定在稍后的传递中不可用。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-150">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="fdcf2-151">可以在[控制流](xref:microsoft.quantum.guide.controlflow)中找到有关这些循环的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-151">Details on these loops can be found at [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="fdcf2-152">来自外部块的符号绑定由内部块继承。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-152">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="fdcf2-153">一个符号只能绑定每个块一次;定义与作用域中的另一个符号名称相同（无 "隐藏"）的符号是非法的。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-153">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="fdcf2-154">以下顺序是合法的：</span><span class="sxs-lookup"><span data-stu-id="fdcf2-154">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="fdcf2-155">和</span><span class="sxs-lookup"><span data-stu-id="fdcf2-155">and</span></span>

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

<span data-ttu-id="fdcf2-156">但这是非法的：</span><span class="sxs-lookup"><span data-stu-id="fdcf2-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="fdcf2-157">如下所示：</span><span class="sxs-lookup"><span data-stu-id="fdcf2-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="whats-next"></a><span data-ttu-id="fdcf2-158">下一步是什么？</span><span class="sxs-lookup"><span data-stu-id="fdcf2-158">What's Next?</span></span>
<span data-ttu-id="fdcf2-159">了解如何使用 Q # 中[的 Qubits](xref:microsoft.quantum.guide.qubits) 。</span><span class="sxs-lookup"><span data-stu-id="fdcf2-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>