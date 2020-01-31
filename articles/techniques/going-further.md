---
title: '进一步-Q # 技术 |Microsoft Docs'
description: '进一步-Q # 技术'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: bd2b799d4001e280baccb04158247891b9cbb5bc
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820192"
---
# <a name="going-further"></a><span data-ttu-id="31633-103">进一步</span><span class="sxs-lookup"><span data-stu-id="31633-103">Going Further</span></span> #

<span data-ttu-id="31633-104">现在，你已了解如何在 Q # 中编写有趣的量程程序，本部分将进一步介绍一些更高级的主题，这些主题将有助于今后使用。</span><span class="sxs-lookup"><span data-stu-id="31633-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="31633-105">泛型操作和函数</span><span class="sxs-lookup"><span data-stu-id="31633-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="31633-106">本节假定一些基本熟悉[中C#的泛型](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics)、[泛型中F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/)的泛型、 [ C++模板](https://docs.microsoft.com/cpp/cpp/templates-cpp)或类似的方法，以用于其他语言的元编程。</span><span class="sxs-lookup"><span data-stu-id="31633-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="31633-107">我们可能想要定义的许多函数和操作实际上不依赖于其输入类型，而只是通过其他函数或操作隐式使用其类型。</span><span class="sxs-lookup"><span data-stu-id="31633-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="31633-108">例如，请考虑许多功能语言共有的*地图*概念;给定函数 $f （x） $ 和值为 $\{的集合 $ x_1，x_2，\dots ..，x_n\}$，map 返回一个新的集合 $\{f （x_1）、f （x_2）、\dots ..、f （x_n）\}$。</span><span class="sxs-lookup"><span data-stu-id="31633-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="31633-109">若要在 Q # 中实现此功能，我们可以利用该函数作为第一类。</span><span class="sxs-lookup"><span data-stu-id="31633-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="31633-110">接下来，编写 `Map`的快捷示例，使用★作为占位符，同时找出所需的类型。</span><span class="sxs-lookup"><span data-stu-id="31633-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="31633-111">请注意，无论替换的实际类型是什么，此函数的外观都是相同的。</span><span class="sxs-lookup"><span data-stu-id="31633-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="31633-112">例如，从整数到 Paulis 的映射与从浮点数到字符串的映射大致相同：</span><span class="sxs-lookup"><span data-stu-id="31633-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="31633-113">原则上，我们可以编写一对我们遇到的每对类型的 `Map` 版本，但这会带来很多麻烦。</span><span class="sxs-lookup"><span data-stu-id="31633-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="31633-114">例如，如果我们在 `Map`中找到 bug，则必须确保在所有版本的 `Map`中统一应用修补程序。</span><span class="sxs-lookup"><span data-stu-id="31633-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="31633-115">此外，如果我们构造新的元组或 UDT，则现在还必须构造一个新的 `Map` 来与新类型一起工作。</span><span class="sxs-lookup"><span data-stu-id="31633-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="31633-116">虽然这对于少量此类函数是易的，但由于我们收集与 `Map`相同窗体的更多函数，因此引入新类型的成本将以相当短的顺序变为太。</span><span class="sxs-lookup"><span data-stu-id="31633-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="31633-117">但这种情况很难得到，因为我们没有为编译器提供所需的信息，以确定不同版本的 `Map` 是如何相关的。</span><span class="sxs-lookup"><span data-stu-id="31633-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="31633-118">实际上，我们希望编译器将 `Map` 视为从 Q #*类型*到 q # 函数的某种数学函数。</span><span class="sxs-lookup"><span data-stu-id="31633-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="31633-119">此概念的形式为：允许函数和操作具有*类型参数*，以及其普通元组参数。</span><span class="sxs-lookup"><span data-stu-id="31633-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="31633-120">在上述示例中，我们希望在第一种情况下将 `Map` 视为具有类型 `Int, Pauli` 参数，并在第二种情况下 `Double, String`。</span><span class="sxs-lookup"><span data-stu-id="31633-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="31633-121">大多数情况下，可以像使用普通类型一样使用这些类型参数：我们使用类型参数的值来生成数组和元组，调用函数和操作，并将其分配给普通或可变变量。</span><span class="sxs-lookup"><span data-stu-id="31633-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="31633-122">间接依赖关系的最极端情况是 qubits，其中 Q # 程序无法直接依赖于 `Qubit` 类型的结构，但**必须**将此类类型传递给其他操作和函数。</span><span class="sxs-lookup"><span data-stu-id="31633-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="31633-123">返回到上面的示例，我们可以看到，我们需要 `Map` 具有类型参数，一个用于表示 `fn` 的输入，另一个用于表示 `fn`的输出。</span><span class="sxs-lookup"><span data-stu-id="31633-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="31633-124">在 Q # 中，这是通过在其声明中的函数或操作名称后面添加尖括号（即 `<>`，而不是 brakets $ \braket{}$！）来编写的，并列出每个类型参数。</span><span class="sxs-lookup"><span data-stu-id="31633-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="31633-125">每个类型形参的名称必须以刻度 `'`开头，这表示它是一个类型形参，而不是一个普通类型（也称为*具体*类型）。</span><span class="sxs-lookup"><span data-stu-id="31633-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="31633-126">对于 `Map`，我们编写：</span><span class="sxs-lookup"><span data-stu-id="31633-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="31633-127">请注意，`Map<'Input, 'Output>` 的定义似乎与之前编写的版本非常类似。</span><span class="sxs-lookup"><span data-stu-id="31633-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="31633-128">唯一的区别是，我们已明确通知编译器 `Map` 不直接依赖于 `'Input` 和 `'Output`，但可通过 `fn`间接使用这两种类型。</span><span class="sxs-lookup"><span data-stu-id="31633-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="31633-129">通过这种方式定义 `Map<'Input, 'Output>` 后，可以像调用普通函数一样调用它：</span><span class="sxs-lookup"><span data-stu-id="31633-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="31633-130">编写泛型函数和操作是一个位置，其中 "元组即用元组" 是一种非常有用的方法，用于考虑 Q # 函数和操作。</span><span class="sxs-lookup"><span data-stu-id="31633-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="31633-131">由于每个函数只采用一个输入并返回一个输出，因此类型 `'T -> 'U` 的输入与*任何*Q # 函数匹配。</span><span class="sxs-lookup"><span data-stu-id="31633-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="31633-132">同样，可以将任何操作传递到 `'T => 'U`类型的输入。</span><span class="sxs-lookup"><span data-stu-id="31633-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="31633-133">作为第二个示例，请考虑编写一个函数，该函数返回两个其他函数的组合：</span><span class="sxs-lookup"><span data-stu-id="31633-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="31633-134">在此，我们必须准确指定 `A`、`B`和 `C` 的内容，因此会严重限制新 `Compose` 函数的实用工具。</span><span class="sxs-lookup"><span data-stu-id="31633-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="31633-135">毕竟，`Compose` 仅依赖于*通过*`innerFn` 和 `outerFn``A`、`B`和 `C`。</span><span class="sxs-lookup"><span data-stu-id="31633-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="31633-136">作为替代方法，我们可以将类型参数添加到 `Compose`，这表示它适用于*任何*`A`、`B`和 `C`，前提是这些参数与 `innerFn` 和 `outerFn`所需的参数匹配：</span><span class="sxs-lookup"><span data-stu-id="31633-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="31633-137">Q # 标准库提供了多种类型参数化操作和函数，使更高顺序控制流更易于表达。</span><span class="sxs-lookup"><span data-stu-id="31633-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="31633-138">" [Q # 标准库指南](xref:microsoft.quantum.libraries.standard.intro)" 中进一步讨论了这些问题。</span><span class="sxs-lookup"><span data-stu-id="31633-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="31633-139">借贷 Qubits</span><span class="sxs-lookup"><span data-stu-id="31633-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="31633-140">使用借款机制，可以在计算过程中将 qubits 分配为暂存空间。</span><span class="sxs-lookup"><span data-stu-id="31633-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="31633-141">这些 qubits 通常不处于干净状态，也就是说，它们不一定在已知状态（如 $ \ket{0}$）中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="31633-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="31633-142">还有一个 "脏" qubits，因为其状态为未知，甚至可以与量程计算机内存的其他部分放大。</span><span class="sxs-lookup"><span data-stu-id="31633-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="31633-143">在脏 qubits 的已知用例中，是多控制 CNOT-CONTAINS 入口的实现，只需很少的 qubits 和实现 incrementers。</span><span class="sxs-lookup"><span data-stu-id="31633-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="31633-144">在 canon 中，有使用 `borrowing` 关键字的示例，例如函数 `MultiControlledXBorrow` 在下面定义。</span><span class="sxs-lookup"><span data-stu-id="31633-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="31633-145">如果 `controls` 表示应该添加到 `X` 操作的控件 qubits，则此实现将添加 `Length(controls)-2` 许多脏 ancillas 的总体。</span><span class="sxs-lookup"><span data-stu-id="31633-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

<span data-ttu-id="31633-146">请注意，广泛使用 `With` 连结符---其形式适用于支持 adjoint 的操作，即，`WithA`---在此示例中，这是一种很好的编程风格，这是将控件添加到包含 `With` 仅将控制传播到内部操作的结构。</span><span class="sxs-lookup"><span data-stu-id="31633-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="31633-147">另外请注意，除了操作 `body` 外，还显式提供操作的 `controlled` 体实现，而不是采用 `controlled auto` 语句。</span><span class="sxs-lookup"><span data-stu-id="31633-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="31633-148">这样做的原因是，我们从线路的结构中知道如何轻松添加更多的控件，这与将控件添加到 `body`中的每个门和每个单独的门相比，更有利。</span><span class="sxs-lookup"><span data-stu-id="31633-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="31633-149">将此代码与其他 canon 函数进行比较是有益的 `MultiControlledXClean` 该函数实现了执行乘法控制的 `X` 操作的相同目标，然而，这种方法使用了 `using` 机制。</span><span class="sxs-lookup"><span data-stu-id="31633-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
