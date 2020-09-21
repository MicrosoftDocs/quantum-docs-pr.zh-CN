---
title: 控制流 Q#
description: 循环、条件等。
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: 547c57cab67443e8b487bf817eb79fc922b43cdc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833509"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="c8c6d-103">控制流 Q#</span><span class="sxs-lookup"><span data-stu-id="c8c6d-103">Control flow in Q#</span></span>

<span data-ttu-id="c8c6d-104">在操作或函数中，每个语句都按顺序运行，类似于其他常见的命令性传统语言。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="c8c6d-105">但是，可以通过三种不同的方式修改控制流：</span><span class="sxs-lookup"><span data-stu-id="c8c6d-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="c8c6d-106">`if` 前瞻性</span><span class="sxs-lookup"><span data-stu-id="c8c6d-106">`if` statements</span></span>
* <span data-ttu-id="c8c6d-107">`for` 循环</span><span class="sxs-lookup"><span data-stu-id="c8c6d-107">`for` loops</span></span>
* <span data-ttu-id="c8c6d-108">`repeat-until-success` 循环</span><span class="sxs-lookup"><span data-stu-id="c8c6d-108">`repeat-until-success` loops</span></span>
* <span data-ttu-id="c8c6d-109">语态 (`apply-within` 语句) </span><span class="sxs-lookup"><span data-stu-id="c8c6d-109">conjugations (`apply-within` statements)</span></span>

<span data-ttu-id="c8c6d-110">`if`和 `for` 控制流构造在熟悉大多数传统编程语言的情况下继续进行。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-110">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="c8c6d-111">[`Repeat-until-success`](#repeat-until-success-loop) 循环和 [语态](#conjugations) 将在本文的后面部分进行讨论。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-111">[`Repeat-until-success`](#repeat-until-success-loop) loops and [conjugations](#conjugations) are discussed later in this article.</span></span>

<span data-ttu-id="c8c6d-112">重要的 `for` 是，循环和 `if` 语句可用于自动生成 [专用](xref:microsoft.quantum.guide.operationsfunctions) 化的操作。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-112">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="c8c6d-113">在这种情况下，循环的 adjoint `for` 会反转方向，并 adjoint 每次迭代。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-113">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="c8c6d-114">此操作遵循 "鞋和 socks" 原则：如果想要撤消在 socks 和鞋上进行操作，必须先撤消鞋，然后撤消放置 socks。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-114">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="c8c6d-115">如果为，则为; 否则为</span><span class="sxs-lookup"><span data-stu-id="c8c6d-115">If, Else-if, Else</span></span>

<span data-ttu-id="c8c6d-116">`if`语句支持条件处理。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-116">The `if` statement supports conditional processing.</span></span>
<span data-ttu-id="c8c6d-117">它包含关键字 `if` 、括号中的布尔表达式和语句块 (_then_ 块) 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-117">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="c8c6d-118">根据需要，可以遵循任意数量的 else if 子句，其中每个子句都包含关键字 `elif` 、括号中的布尔表达式和语句块 (_else （if）_ 块) 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-118">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="c8c6d-119">最后，语句可以选择使用 else 子句完成，后者由关键字 `else` 后跟另一个语句块 (_else_ 块) 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-119">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="c8c6d-120">`if`计算条件，如果该条件为*true*，则运行*then*块。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-120">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="c8c6d-121">如果条件为 *false*，则计算第一个 else if 条件;如果为 true，则运行 *其他-if* 块。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-121">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="c8c6d-122">否则，第二个 else-if block 计算，然后是第三个，依此类推，直到遇到具有 true 条件的子句，或者没有其他的 else 子句。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-122">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="c8c6d-123">如果原始 *if* 条件和所有 else if 子句的计算结果为 *false*，则将运行 *else* 块（如果已提供）。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-123">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="c8c6d-124">请注意，不管哪个块运行，它都在它自己的作用域内运行。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-124">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="c8c6d-125">`if`块结束后，在、或块内部所做的绑定 `elif` `else` 将不可见。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="c8c6d-126">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="c8c6d-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="c8c6d-127">或</span><span class="sxs-lookup"><span data-stu-id="c8c6d-127">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="c8c6d-128">For 循环</span><span class="sxs-lookup"><span data-stu-id="c8c6d-128">For loop</span></span>

<span data-ttu-id="c8c6d-129">`for`语句支持对整数范围或数组进行迭代。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-129">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="c8c6d-130">语句包含关键字 `for` ，后跟符号或符号元组、关键字 `in` 、类型 `Range` 或数组的表达式、所有 in 括号和语句块。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-130">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="c8c6d-131">语句块 (循环的主体) 重复运行，定义的符号 (循环变量) 绑定到该范围或数组中的每个值。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-131">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="c8c6d-132">请注意，如果范围表达式的计算结果为空范围或数组，则正文根本不会运行。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-132">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="c8c6d-133">在进入循环之前，将完全计算该表达式，并且循环运行时不会更改。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-133">The expression is fully evaluated before entering the loop, and does not change while the loop is running.</span></span>

<span data-ttu-id="c8c6d-134">循环变量绑定到循环体的每个入口，在主体末尾解除绑定。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-134">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="c8c6d-135">For 循环完成后，循环变量未绑定。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-135">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="c8c6d-136">循环变量的绑定是不可变的，并且与其他变量绑定遵循相同的规则。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-136">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="c8c6d-137">在这些示例中， `qubits` 是 qubits 的寄存器 (即) 类型的 `Qubit[]` ，</span><span class="sxs-lookup"><span data-stu-id="c8c6d-137">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="c8c6d-138">请注意，在结束时，我们使用了算术左移的二进制运算符 `<<<` 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-138">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="c8c6d-139">有关详细信息，请参阅 [数值表达式](xref:microsoft.quantum.guide.expressions#numeric-expressions)。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-139">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="c8c6d-140">重复执行-成功循环</span><span class="sxs-lookup"><span data-stu-id="c8c6d-140">Repeat-until-success loop</span></span>

<span data-ttu-id="c8c6d-141">此 Q# 语言允许经典控制流依赖于测量 qubits 的结果。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-141">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="c8c6d-142">此功能进而实现了实现功能强大的概率小工具，从而降低了实现 unitaries 的计算成本。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-142">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="c8c6d-143">这种情况的示例如下所示 *-成功* (ru) 模式 Q# 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-143">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="c8c6d-144">这些 RUS 模式是概率的程序，这些程序在基本入口方面具有 *预期* 的低成本;产生的费用取决于多个可能 branchings 的实际运行和交叉交叉。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-144">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="c8c6d-145">为了便于重复-成功 (ru) 模式， Q# 支持构造</span><span class="sxs-lookup"><span data-stu-id="c8c6d-145">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="c8c6d-146">其中 `expression` ，是任何计算结果为类型的值的有效表达式 `Bool` 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-146">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="c8c6d-147">循环体运行，然后计算条件。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-147">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="c8c6d-148">如果条件为 true，则语句已完成;否则，修正将运行，并且语句将再次运行（从循环体开始）。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-148">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="c8c6d-149"> (正文、测试和修正) 的所有三个部分都被视为 *每个重复*的单个作用域，因此，在正文中绑定的符号可用于测试和修复。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-149">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="c8c6d-150">但是，完成修正的运行将结束语句的范围，以便在正文或修正期间所进行的符号绑定在后续的重复中不可用。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-150">However, completing the run of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="c8c6d-151">而且， `fixup` 语句通常非常有用，但并非总是必需的。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-151">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="c8c6d-152">如果不需要，构造</span><span class="sxs-lookup"><span data-stu-id="c8c6d-152">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="c8c6d-153">也是有效的 RUS 模式。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-153">is also a valid RUS pattern.</span></span>

<span data-ttu-id="c8c6d-154">有关更多示例和详细信息，请参阅本文中的 [重复-截止到成功示例](#repeat-until-success-examples) 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-154">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="c8c6d-155">避免在函数内使用重复-until 循环。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-155">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="c8c6d-156">使用 *while* 循环来提供函数内的相应功能。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-156">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="c8c6d-157">While 循环</span><span class="sxs-lookup"><span data-stu-id="c8c6d-157">While loop</span></span>

<span data-ttu-id="c8c6d-158">重复-直到成功模式有一个非常特定于量程的内涵。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-158">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="c8c6d-159">它们广泛用于特定的量程算法类，因此是中的专用语言构造 Q# 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-159">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="c8c6d-160">但是，在编译时，中断的循环会根据特定的时刻处理中断，并且在编译时是未知的。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-160">However, loops that break based on a condition and whose run length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="c8c6d-161">但是，它们在函数中的使用是 unproblematic 的，因为这些循环只包含在常规 (非量程) 硬件上运行的代码。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-161">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="c8c6d-162">Q#因此，仅支持在函数内使用 while 循环。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-162">Q#, therefore, supports to use of while loops within functions only.</span></span>
<span data-ttu-id="c8c6d-163">`while`语句由关键字 `while` 、括号中的布尔表达式和语句块组成。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-163">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="c8c6d-164">只要条件的计算结果为，语句块 (循环的主体) 运行 `true` 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-164">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a><span data-ttu-id="c8c6d-165">语态</span><span class="sxs-lookup"><span data-stu-id="c8c6d-165">Conjugations</span></span>

<span data-ttu-id="c8c6d-166">与传统位相比，释放量程内存会稍微增加一点，因为在 qubits 仍放大时，盲目重置 qubits 可能会对剩余计算产生意外影响。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-166">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="c8c6d-167">在释放内存之前，可以通过适当的方式 "撤消" 已执行的计算来避免这些效果。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-167">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="c8c6d-168">量程计算的常见模式如下：</span><span class="sxs-lookup"><span data-stu-id="c8c6d-168">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="c8c6d-169">Q# 支持语态语句，该语句实现前面的转换。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-169">Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="c8c6d-170">使用该语句，可以通过 `ApplyWith` 以下方式实现操作：</span><span class="sxs-lookup"><span data-stu-id="c8c6d-170">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="c8c6d-171">如果外部和内部转换不能作为运算随时使用，则此类语态语句将非常有用，但通过多个语句组成的块可以更方便地进行描述。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-171">Such a conjugation statement becomes useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="c8c6d-172">在内块中定义的语句的反转换是由编译器自动生成的，并在应用块完成后运行。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-172">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="c8c6d-173">由于不能在 apply 块中重新绑定用作内部块的一部分的任何可变变量，因此，生成的转换将保证为内块中计算的 adjoint。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-173">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="return-statement"></a><span data-ttu-id="c8c6d-174">Return 语句</span><span class="sxs-lookup"><span data-stu-id="c8c6d-174">Return Statement</span></span>

<span data-ttu-id="c8c6d-175">Return 语句结束操作或函数的运行，并将值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-175">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="c8c6d-176">它包含关键字 `return` ，后跟适当类型的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-176">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="c8c6d-177">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="c8c6d-177">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="c8c6d-178">或</span><span class="sxs-lookup"><span data-stu-id="c8c6d-178">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="c8c6d-179">返回空元组的可调用 `()` 不需要 return 语句。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-179">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="c8c6d-180">若要指定操作或函数的早期退出，请使用 `return ();` 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-180">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="c8c6d-181">返回任何其他类型的 Callables 需要最终的 return 语句。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-181">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="c8c6d-182">操作中不存在最大返回语句数。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-182">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="c8c6d-183">如果语句在块内跟随 return 语句，则编译器可能会发出警告。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-183">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="c8c6d-184">Fail 语句</span><span class="sxs-lookup"><span data-stu-id="c8c6d-184">Fail statement</span></span>

<span data-ttu-id="c8c6d-185">Fail 语句结束操作的运行，并将错误值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-185">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="c8c6d-186">它包含关键字 `fail` ，后跟一个字符串和一个终止分号。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-186">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="c8c6d-187">语句将字符串返回到传统驱动程序作为错误消息。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-187">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="c8c6d-188">操作中的 fail 语句数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-188">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="c8c6d-189">如果语句在块中跟随 fail 语句，则编译器可能会发出警告。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-189">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="c8c6d-190">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="c8c6d-190">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="c8c6d-191">或者，使用内[插字符串](xref:microsoft.quantum.guide.expressions#interpolated-strings)</span><span class="sxs-lookup"><span data-stu-id="c8c6d-191">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="c8c6d-192">重复执行-直到成功示例</span><span class="sxs-lookup"><span data-stu-id="c8c6d-192">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="c8c6d-193">针对无理数轴的单 qubit 旋转的 RUS 模式</span><span class="sxs-lookup"><span data-stu-id="c8c6d-193">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="c8c6d-194">在典型用例中，以下 Q# 操作实现绕 {5} Bloch 球上的无理数轴（$ (I + 2i Z) /\sqrt $）的旋转。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-194">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="c8c6d-195">实现使用已知的 RUS 模式：</span><span class="sxs-lookup"><span data-stu-id="c8c6d-195">The implementation uses a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="c8c6d-196">作用域中具有可变变量的 ru 循环</span><span class="sxs-lookup"><span data-stu-id="c8c6d-196">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="c8c6d-197">此示例演示如何使用可变变量，该变量在 `finished` 整个重复截止到延迟的循环范围内，并在循环之前进行初始化并在修正步骤中更新。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-197">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="c8c6d-198">不带 `fixup`</span><span class="sxs-lookup"><span data-stu-id="c8c6d-198">RUS without `fixup`</span></span>

<span data-ttu-id="c8c6d-199">此示例显示了不带修正步骤的 ru 循环。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-199">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="c8c6d-200">此代码是一种概率线路，它使用和入口实现重要的旋转门 $V _3 = ( \boldone + 2 i Z) /\sqrt {5} $ `H` `T` 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-200">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="c8c6d-201">该循环平均终止 $ \frac {8} {5} $ 重复。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-201">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="c8c6d-202">有关更多详细信息，请参阅 qubit unitaries (Paetznick 和 Svore，2014) 的 [*非确定性分解*](https://arxiv.org/abs/1311.1074) 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-202">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="c8c6d-203">用于准备量子状态的 ru</span><span class="sxs-lookup"><span data-stu-id="c8c6d-203">RUS to prepare a quantum state</span></span>

<span data-ttu-id="c8c6d-204">最后，下面是一个用于准备量子状态 $ \frac {1} {\sqrt {3} } \left ( \sqrt {2} \ket {0} + \ket {1} \right) $，从 $ \ket{+} $ 状态开始的 ru 模式的示例。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-204">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="c8c6d-205">此操作中所示的明显编程功能包括：</span><span class="sxs-lookup"><span data-stu-id="c8c6d-205">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="c8c6d-206">`fixup`循环中涉及量程操作的更为复杂的部分。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-206">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="c8c6d-207">使用 `AssertMeasurementProbability` 语句来确定在程序中的某些指定点测量量程状态的概率。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-207">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="c8c6d-208">有关和操作的详细 [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) 信息 [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) ，请参阅 [测试和调试](xref:microsoft.quantum.guide.testingdebugging)。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-208">For more information about the [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="c8c6d-209">有关详细信息，请参阅 [随标准库提供的单元测试示例](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：</span><span class="sxs-lookup"><span data-stu-id="c8c6d-209">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8c6d-210">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8c6d-210">Next steps</span></span>

<span data-ttu-id="c8c6d-211">了解中的 [测试和调试](xref:microsoft.quantum.guide.testingdebugging) Q# 。</span><span class="sxs-lookup"><span data-stu-id="c8c6d-211">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
