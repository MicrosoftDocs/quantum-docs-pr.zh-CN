---
title: Q 中的控制流#
description: 循环、条件等。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430945"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="d98b0-103">Q 中的控制流#</span><span class="sxs-lookup"><span data-stu-id="d98b0-103">Control Flow in Q#</span></span>

<span data-ttu-id="d98b0-104">在操作或函数中，每个语句都按顺序执行，类似于最常见的命令性传统语言。</span><span class="sxs-lookup"><span data-stu-id="d98b0-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="d98b0-105">不过，可以通过三种不同的方式来修改这种控制流：</span><span class="sxs-lookup"><span data-stu-id="d98b0-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="d98b0-106">`if`前瞻性</span><span class="sxs-lookup"><span data-stu-id="d98b0-106">`if` statements</span></span>
- <span data-ttu-id="d98b0-107">`for`循环</span><span class="sxs-lookup"><span data-stu-id="d98b0-107">`for` loops</span></span>
- <span data-ttu-id="d98b0-108">`repeat`-`until`循环</span><span class="sxs-lookup"><span data-stu-id="d98b0-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="d98b0-109">接[下来，我们](#repeat-until-success-loop)将讨论后者。</span><span class="sxs-lookup"><span data-stu-id="d98b0-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="d98b0-110">`if` `for` 不过，和控制流构造在熟悉大多数传统编程语言的情况下继续进行。</span><span class="sxs-lookup"><span data-stu-id="d98b0-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="d98b0-111">重要的 `for` 是，循环和 `if` 语句甚至可用于自动生成专用化的操作。</span><span class="sxs-lookup"><span data-stu-id="d98b0-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="d98b0-112">在这种情况下，循环的 adjoint `for` 会反转方向，并 adjoint 每次迭代。</span><span class="sxs-lookup"><span data-stu-id="d98b0-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="d98b0-113">这遵循了 "鞋和 socks" 原则：如果你想要撤消对 socks 和鞋的投入，则必须撤消鞋，然后撤消放置在 socks 上。</span><span class="sxs-lookup"><span data-stu-id="d98b0-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="d98b0-114">在您仍戴鞋的同时，小猫的工作效率更小，并使您的 socks 保持不变！</span><span class="sxs-lookup"><span data-stu-id="d98b0-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="d98b0-115">如果为，则为; 否则为</span><span class="sxs-lookup"><span data-stu-id="d98b0-115">If, Else-if, Else</span></span>

<span data-ttu-id="d98b0-116">`if`语句支持条件执行。</span><span class="sxs-lookup"><span data-stu-id="d98b0-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="d98b0-117">它包含关键字 `if` 、左括号 `(` 、布尔表达式、右括号 `)` 和语句块（ _then_块）。</span><span class="sxs-lookup"><span data-stu-id="d98b0-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="d98b0-118">这可能后跟任意数量的 else if 子句，每个子句包含关键字 `elif` 、左括号 `(` 、布尔表达式、右括号 `)` 和语句块（ _else-if_块）。</span><span class="sxs-lookup"><span data-stu-id="d98b0-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="d98b0-119">最后，语句可以选择使用 else 子句完成，后者由关键字 `else` 后跟另一个语句块（ _else_块）组成。</span><span class="sxs-lookup"><span data-stu-id="d98b0-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="d98b0-120">`if`计算条件，如果该条件为 true，则执行 then 块。</span><span class="sxs-lookup"><span data-stu-id="d98b0-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="d98b0-121">如果条件为 false，则计算第一个 else if 条件;如果为 true，则执行此 else-if block。</span><span class="sxs-lookup"><span data-stu-id="d98b0-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="d98b0-122">否则，将测试第二个 else-if 块，然后是第三个块，依此类推，直到遇到具有 true 条件的子句或没有其他的 else 子句。</span><span class="sxs-lookup"><span data-stu-id="d98b0-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="d98b0-123">如果原始 if 条件和所有 else-if 子句的计算结果为 false，则在提供时将执行 else 块。</span><span class="sxs-lookup"><span data-stu-id="d98b0-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="d98b0-124">请注意，执行的任何块在其自己的作用域中执行。</span><span class="sxs-lookup"><span data-stu-id="d98b0-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="d98b0-125">在、或块内部所做的绑定在 `if` `elif` `else` 其结束后将不可见。</span><span class="sxs-lookup"><span data-stu-id="d98b0-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="d98b0-126">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="d98b0-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="d98b0-127">或</span><span class="sxs-lookup"><span data-stu-id="d98b0-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="d98b0-128">For 循环</span><span class="sxs-lookup"><span data-stu-id="d98b0-128">For Loop</span></span>

<span data-ttu-id="d98b0-129">`for`语句支持对整数范围或数组进行迭代。</span><span class="sxs-lookup"><span data-stu-id="d98b0-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="d98b0-130">语句包含关键字 `for` 、左括号 `(` 、符号或符号元组、关键字 `in` 、类型 `Range` 或数组的表达式、右括号 `)` 和语句块。</span><span class="sxs-lookup"><span data-stu-id="d98b0-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="d98b0-131">语句块（循环的主体）将重复执行，其中定义的符号（即循环变量）绑定到范围或数组中的每个值。</span><span class="sxs-lookup"><span data-stu-id="d98b0-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="d98b0-132">请注意，如果范围表达式的计算结果为空范围或数组，则不会执行主体。</span><span class="sxs-lookup"><span data-stu-id="d98b0-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="d98b0-133">在进入循环之前，将完全计算该表达式，并且在执行循环时不会更改。</span><span class="sxs-lookup"><span data-stu-id="d98b0-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="d98b0-134">循环变量绑定到循环体的每个入口，并在主体末尾解除绑定。</span><span class="sxs-lookup"><span data-stu-id="d98b0-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="d98b0-135">具体而言，for 循环完成后不会绑定循环变量。</span><span class="sxs-lookup"><span data-stu-id="d98b0-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="d98b0-136">声明的符号的绑定是不可变的，并且与其他变量绑定遵循相同的规则。</span><span class="sxs-lookup"><span data-stu-id="d98b0-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="d98b0-137">对于某些示例，supposing `qubits` 是 qubits （即类型）的寄存器 `Qubit[]` ，</span><span class="sxs-lookup"><span data-stu-id="d98b0-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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
<span data-ttu-id="d98b0-138">请注意，在结束时，我们使用了算术左移的二进制运算符， `<<<` 详细信息可在[数值表达式](xref:microsoft.quantum.guide.expressions#numeric-expressions)中找到</span><span class="sxs-lookup"><span data-stu-id="d98b0-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="d98b0-139">重复执行-成功循环</span><span class="sxs-lookup"><span data-stu-id="d98b0-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="d98b0-140">Q # 语言允许经典控制流依赖于测量 qubits 的结果。</span><span class="sxs-lookup"><span data-stu-id="d98b0-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="d98b0-141">此功能反过来允许实现功能强大的概率小工具，从而降低实现 unitaries 的计算成本。</span><span class="sxs-lookup"><span data-stu-id="d98b0-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="d98b0-142">例如，可以轻松地在 Q # 中实现所谓的 "*重复到-成功*" （ru）模式。</span><span class="sxs-lookup"><span data-stu-id="d98b0-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="d98b0-143">这些 ru 模式是概率的程序，这些程序在基本入口方面具有*预期*的低成本，但真正的成本取决于实际运行以及各种可能的 branchings 的实际交错。</span><span class="sxs-lookup"><span data-stu-id="d98b0-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="d98b0-144">为了便于重复到成功（ru）模式，Q # 支持构造</span><span class="sxs-lookup"><span data-stu-id="d98b0-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="d98b0-145">其中 `expression` ，是任何计算结果为类型的值的有效表达式 `Bool` 。</span><span class="sxs-lookup"><span data-stu-id="d98b0-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="d98b0-146">执行循环体，然后计算条件。</span><span class="sxs-lookup"><span data-stu-id="d98b0-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="d98b0-147">如果条件为 true，则语句已完成;否则，将执行修正，并从循环体开始重新执行该语句。</span><span class="sxs-lookup"><span data-stu-id="d98b0-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="d98b0-148">重复/等待循环的所有三个部分（正文、测试和修正）被视为*每个重复*的单个作用域，因此，在正文中绑定的符号可用于测试和修复中。</span><span class="sxs-lookup"><span data-stu-id="d98b0-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="d98b0-149">但是，完成修正的执行将结束语句的范围，以便在正文或修正期间进行的符号绑定在后续的重复中不可用。</span><span class="sxs-lookup"><span data-stu-id="d98b0-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="d98b0-150">而且， `fixup` 语句通常非常有用，但并非总是必需的。</span><span class="sxs-lookup"><span data-stu-id="d98b0-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="d98b0-151">如果不需要，构造</span><span class="sxs-lookup"><span data-stu-id="d98b0-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="d98b0-152">也是有效的 RUS 模式。</span><span class="sxs-lookup"><span data-stu-id="d98b0-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="d98b0-153">在此页的底部，我们提供[了一个 ru 循环的示例](#repeat-until-success-examples)。</span><span class="sxs-lookup"><span data-stu-id="d98b0-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="d98b0-154">避免在函数内使用重复-until 循环。</span><span class="sxs-lookup"><span data-stu-id="d98b0-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="d98b0-155">当函数中的循环时，将提供相应的功能。</span><span class="sxs-lookup"><span data-stu-id="d98b0-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="d98b0-156">While 循环</span><span class="sxs-lookup"><span data-stu-id="d98b0-156">While Loop</span></span>

<span data-ttu-id="d98b0-157">重复-直到成功模式有一个非常特定于量程的内涵。</span><span class="sxs-lookup"><span data-stu-id="d98b0-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="d98b0-158">它们广泛用于特定的量程算法类，因此，它是 Q # 中的专用语言构造。</span><span class="sxs-lookup"><span data-stu-id="d98b0-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="d98b0-159">但是，在编译时，需要在量程运行时中特别小心地处理基于某个条件、其执行长度未知的循环。</span><span class="sxs-lookup"><span data-stu-id="d98b0-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="d98b0-160">另一方面，它们在函数中的使用是 unproblematic 的，因为它们仅包含将在常规（非量程）硬件上执行的代码。</span><span class="sxs-lookup"><span data-stu-id="d98b0-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="d98b0-161">因此，Q # 支持仅在函数内使用 while 循环。</span><span class="sxs-lookup"><span data-stu-id="d98b0-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="d98b0-162">`while`语句由关键字 `while` 、左括号 `(` 、条件（即布尔表达式）、右括号 `)` 和语句块组成。</span><span class="sxs-lookup"><span data-stu-id="d98b0-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="d98b0-163">只要条件的计算结果为，就会执行语句块（循环的主体） `true` 。</span><span class="sxs-lookup"><span data-stu-id="d98b0-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="d98b0-164">Return 语句</span><span class="sxs-lookup"><span data-stu-id="d98b0-164">Return Statement</span></span>

<span data-ttu-id="d98b0-165">Return 语句结束操作或函数的执行，并将值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="d98b0-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="d98b0-166">它包含关键字 `return` ，后跟适当类型的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="d98b0-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="d98b0-167">返回空元组的可调用 `()` 不需要 return 语句。</span><span class="sxs-lookup"><span data-stu-id="d98b0-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="d98b0-168">如果需要提前退出，则可 `return ()` 在此情况下使用。</span><span class="sxs-lookup"><span data-stu-id="d98b0-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="d98b0-169">返回任何其他类型的 Callables 需要最终的 return 语句。</span><span class="sxs-lookup"><span data-stu-id="d98b0-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="d98b0-170">操作中不存在最大返回语句数。</span><span class="sxs-lookup"><span data-stu-id="d98b0-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="d98b0-171">如果语句在块内跟随 return 语句，则编译器可能会发出警告。</span><span class="sxs-lookup"><span data-stu-id="d98b0-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="d98b0-172">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="d98b0-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="d98b0-173">或</span><span class="sxs-lookup"><span data-stu-id="d98b0-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="d98b0-174">或</span><span class="sxs-lookup"><span data-stu-id="d98b0-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="d98b0-175">Fail 语句</span><span class="sxs-lookup"><span data-stu-id="d98b0-175">Fail Statement</span></span>

<span data-ttu-id="d98b0-176">Fail 语句结束操作的执行，并将错误值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="d98b0-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="d98b0-177">它包含关键字 `fail` ，后跟一个字符串和一个终止分号。</span><span class="sxs-lookup"><span data-stu-id="d98b0-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="d98b0-178">该字符串返回到传统驱动程序作为错误消息。</span><span class="sxs-lookup"><span data-stu-id="d98b0-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="d98b0-179">操作中的 fail 语句数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="d98b0-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="d98b0-180">如果语句在块中跟随 fail 语句，则编译器可能会发出警告。</span><span class="sxs-lookup"><span data-stu-id="d98b0-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="d98b0-181">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="d98b0-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="d98b0-182">或者，使用内[插字符串](xref:microsoft.quantum.guide.expressions#interpolated-strings)</span><span class="sxs-lookup"><span data-stu-id="d98b0-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="d98b0-183">重复执行-直到成功示例</span><span class="sxs-lookup"><span data-stu-id="d98b0-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="d98b0-184">针对无理数轴的单个 qubit 旋转的 ru 模式</span><span class="sxs-lookup"><span data-stu-id="d98b0-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="d98b0-185">在典型用例中，以下 Q # 操作实现绕 Bloch 球上的无理数轴（I + 2i Z）/\sqrt $ 围绕 {5} 的旋转。</span><span class="sxs-lookup"><span data-stu-id="d98b0-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="d98b0-186">这是通过使用已知的 RUS 模式来实现的：</span><span class="sxs-lookup"><span data-stu-id="d98b0-186">This is accomplished by using a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="d98b0-187">作用域中具有可变变量的 ru 循环</span><span class="sxs-lookup"><span data-stu-id="d98b0-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="d98b0-188">此示例演示如何使用可变变量，该变量 `finished` 位于整个重复截止到修正循环范围内，并在循环之前进行了初始化并在修正步骤中更新。</span><span class="sxs-lookup"><span data-stu-id="d98b0-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="d98b0-189">不带`fixup`</span><span class="sxs-lookup"><span data-stu-id="d98b0-189">RUS without `fixup`</span></span>

<span data-ttu-id="d98b0-190">例如，下面的代码是一种概率线路，它使用和入口实现重要的旋转门 $V _3 = （\boldone + 2 i Z）/\sqrt {5} $ `H` `T` 。</span><span class="sxs-lookup"><span data-stu-id="d98b0-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="d98b0-191">该循环平均终止 $ \frac {8} {5} $ 重复。</span><span class="sxs-lookup"><span data-stu-id="d98b0-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="d98b0-192">有关更多详细信息，请参阅[*qubit unitaries 的非确定性分解*](https://arxiv.org/abs/1311.1074)（Paetznick 和 Svore，2014）。</span><span class="sxs-lookup"><span data-stu-id="d98b0-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="d98b0-193">用于准备量子状态的 ru</span><span class="sxs-lookup"><span data-stu-id="d98b0-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="d98b0-194">最后，我们将演示一个用于 {1} {3} {2} {0} {1} 从 $ \ket +} $ 状态中开始准备量子状态 $ \frac {\sqrt} \left （\sqrt \ket + \right \ket{） $ 的 ru 模式的示例。</span><span class="sxs-lookup"><span data-stu-id="d98b0-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="d98b0-195">另请参阅[标准库提供的单元测试示例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：</span><span class="sxs-lookup"><span data-stu-id="d98b0-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

<span data-ttu-id="d98b0-196">此操作中所示的明显编程功能是循环中更复杂 `fixup` 的部分，它涉及量程操作，并使用 `AssertProb` 语句来确定在程序中的某些指定点测量量程状态的概率。</span><span class="sxs-lookup"><span data-stu-id="d98b0-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="d98b0-197">有关和操作的详细信息，另请参阅[测试和调试](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) 。</span><span class="sxs-lookup"><span data-stu-id="d98b0-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="whats-next"></a><span data-ttu-id="d98b0-198">下一步是什么？</span><span class="sxs-lookup"><span data-stu-id="d98b0-198">What's Next?</span></span>
<span data-ttu-id="d98b0-199">了解问题解答 # 中的[测试和调试](xref:microsoft.quantum.guide.testingdebugging)。</span><span class="sxs-lookup"><span data-stu-id="d98b0-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>