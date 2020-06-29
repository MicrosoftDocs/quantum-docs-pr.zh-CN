---
title: Q 中的控制流#
description: 循环、条件等。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 0cf62a128170bd0c28ff77f00fc23414567b1ea4
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415297"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="2886c-103">Q 中的控制流#</span><span class="sxs-lookup"><span data-stu-id="2886c-103">Control flow in Q#</span></span>

<span data-ttu-id="2886c-104">在操作或函数中，每个语句都按顺序运行，类似于其他常见的命令性传统语言。</span><span class="sxs-lookup"><span data-stu-id="2886c-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="2886c-105">但是，可以通过三种不同的方式修改控制流：</span><span class="sxs-lookup"><span data-stu-id="2886c-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="2886c-106">`if`前瞻性</span><span class="sxs-lookup"><span data-stu-id="2886c-106">`if` statements</span></span>
* <span data-ttu-id="2886c-107">`for`循环</span><span class="sxs-lookup"><span data-stu-id="2886c-107">`for` loops</span></span>
* <span data-ttu-id="2886c-108">`repeat-until-success`循环</span><span class="sxs-lookup"><span data-stu-id="2886c-108">`repeat-until-success` loops</span></span>

<span data-ttu-id="2886c-109">`if`和 `for` 控制流构造在熟悉大多数传统编程语言的情况下继续进行。</span><span class="sxs-lookup"><span data-stu-id="2886c-109">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="2886c-110">[`Repeat-until-success`](#repeat-until-success-loop)循环将在本文的后面部分进行讨论。</span><span class="sxs-lookup"><span data-stu-id="2886c-110">[`Repeat-until-success`](#repeat-until-success-loop) loops are discussed later in this article.</span></span>

<span data-ttu-id="2886c-111">重要的 `for` 是，循环和 `if` 语句可用于自动生成[专用](xref:microsoft.quantum.guide.operationsfunctions)化的操作。</span><span class="sxs-lookup"><span data-stu-id="2886c-111">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="2886c-112">在这种情况下，循环的 adjoint `for` 会反转方向，并 adjoint 每次迭代。</span><span class="sxs-lookup"><span data-stu-id="2886c-112">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="2886c-113">此操作遵循 "鞋和 socks" 原则：如果想要撤消在 socks 和鞋上进行操作，必须先撤消鞋，然后撤消放置 socks。</span><span class="sxs-lookup"><span data-stu-id="2886c-113">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="2886c-114">如果为，则为; 否则为</span><span class="sxs-lookup"><span data-stu-id="2886c-114">If, Else-if, Else</span></span>

<span data-ttu-id="2886c-115">`if`语句支持条件执行。</span><span class="sxs-lookup"><span data-stu-id="2886c-115">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="2886c-116">它包含关键字 `if` 、括号中的布尔表达式和语句块（ _then_块）。</span><span class="sxs-lookup"><span data-stu-id="2886c-116">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="2886c-117">根据需要，可以遵循任意数量的 else if 子句，其中每个子句都包含关键字 `elif` 、括号中的布尔表达式和语句块（ _else-if_块）。</span><span class="sxs-lookup"><span data-stu-id="2886c-117">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="2886c-118">最后，语句可以选择使用 else 子句完成，后者由关键字 `else` 后跟另一个语句块（ _else_块）组成。</span><span class="sxs-lookup"><span data-stu-id="2886c-118">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="2886c-119">`if`计算条件，如果该条件为*true*，则运行*then*块。</span><span class="sxs-lookup"><span data-stu-id="2886c-119">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="2886c-120">如果条件为*false*，则计算第一个 else if 条件;如果为 true，则运行*其他-if*块。</span><span class="sxs-lookup"><span data-stu-id="2886c-120">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="2886c-121">否则，第二个 else-if block 计算，然后是第三个，依此类推，直到遇到具有 true 条件的子句，或者没有其他的 else 子句。</span><span class="sxs-lookup"><span data-stu-id="2886c-121">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="2886c-122">如果原始*if*条件和所有 else if 子句的计算结果为*false*，则将运行*else*块（如果已提供）。</span><span class="sxs-lookup"><span data-stu-id="2886c-122">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="2886c-123">请注意，不管哪个块运行，它都在它自己的作用域内运行。</span><span class="sxs-lookup"><span data-stu-id="2886c-123">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="2886c-124">`if`块结束后，在、或块内部所做的绑定 `elif` `else` 将不可见。</span><span class="sxs-lookup"><span data-stu-id="2886c-124">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="2886c-125">例如，</span><span class="sxs-lookup"><span data-stu-id="2886c-125">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="2886c-126">或</span><span class="sxs-lookup"><span data-stu-id="2886c-126">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="2886c-127">For 循环</span><span class="sxs-lookup"><span data-stu-id="2886c-127">For loop</span></span>

<span data-ttu-id="2886c-128">`for`语句支持对整数范围或数组进行迭代。</span><span class="sxs-lookup"><span data-stu-id="2886c-128">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="2886c-129">语句包含关键字 `for` ，后跟符号或符号元组、关键字 `in` 、类型 `Range` 或数组的表达式、所有 in 括号和语句块。</span><span class="sxs-lookup"><span data-stu-id="2886c-129">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="2886c-130">语句块（循环的主体）将重复运行，其中定义的符号（循环变量）绑定到范围或数组中的每个值。</span><span class="sxs-lookup"><span data-stu-id="2886c-130">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="2886c-131">请注意，如果范围表达式的计算结果为空范围或数组，则正文根本不会运行。</span><span class="sxs-lookup"><span data-stu-id="2886c-131">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="2886c-132">在进入循环之前，将完全计算该表达式，并且在执行循环时不会更改。</span><span class="sxs-lookup"><span data-stu-id="2886c-132">The expression is fully evaluated before entering the loop, and does not change while the loop is executing.</span></span>

<span data-ttu-id="2886c-133">循环变量绑定到循环体的每个入口，在主体末尾解除绑定。</span><span class="sxs-lookup"><span data-stu-id="2886c-133">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="2886c-134">For 循环完成后，循环变量未绑定。</span><span class="sxs-lookup"><span data-stu-id="2886c-134">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="2886c-135">循环变量的绑定是不可变的，并且与其他变量绑定遵循相同的规则。</span><span class="sxs-lookup"><span data-stu-id="2886c-135">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="2886c-136">在这些示例中， `qubits` 是 qubits （即类型）的寄存器 `Qubit[]` ，</span><span class="sxs-lookup"><span data-stu-id="2886c-136">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="2886c-137">请注意，在结束时，我们使用了算术左移的二进制运算符 `<<<` 。</span><span class="sxs-lookup"><span data-stu-id="2886c-137">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="2886c-138">有关详细信息，请参阅[数值表达式](xref:microsoft.quantum.guide.expressions#numeric-expressions)。</span><span class="sxs-lookup"><span data-stu-id="2886c-138">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="2886c-139">重复执行-成功循环</span><span class="sxs-lookup"><span data-stu-id="2886c-139">Repeat-until-success loop</span></span>

<span data-ttu-id="2886c-140">Q # 语言允许经典控制流依赖于测量 qubits 的结果。</span><span class="sxs-lookup"><span data-stu-id="2886c-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="2886c-141">此功能进而实现了实现功能强大的概率小工具，从而降低了实现 unitaries 的计算成本。</span><span class="sxs-lookup"><span data-stu-id="2886c-141">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="2886c-142">这种情况的示例如下所示： Q # 中的 "*重复-成功*" （ru）模式。</span><span class="sxs-lookup"><span data-stu-id="2886c-142">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="2886c-143">这些 RUS 模式是概率的程序，这些程序在基本入口方面具有*预期*的低成本;产生的费用取决于多个可能 branchings 的实际运行和交叉交叉。</span><span class="sxs-lookup"><span data-stu-id="2886c-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="2886c-144">为了便于重复到成功（ru）模式，Q # 支持构造</span><span class="sxs-lookup"><span data-stu-id="2886c-144">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="2886c-145">其中 `expression` ，是任何计算结果为类型的值的有效表达式 `Bool` 。</span><span class="sxs-lookup"><span data-stu-id="2886c-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="2886c-146">循环体运行，然后计算条件。</span><span class="sxs-lookup"><span data-stu-id="2886c-146">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="2886c-147">如果条件为 true，则语句已完成;否则，修正将运行，并且语句将再次运行（从循环体开始）。</span><span class="sxs-lookup"><span data-stu-id="2886c-147">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="2886c-148">*每个重复*项的所有三个部分（正文、测试和修正）被视为单个作用域，因此，在正文中绑定的符号可用于测试和修复。</span><span class="sxs-lookup"><span data-stu-id="2886c-148">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="2886c-149">但是，完成修正的执行将结束语句的范围，以便在正文或修正期间所进行的符号绑定在后续的重复中不可用。</span><span class="sxs-lookup"><span data-stu-id="2886c-149">However, completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="2886c-150">而且， `fixup` 语句通常非常有用，但并非总是必需的。</span><span class="sxs-lookup"><span data-stu-id="2886c-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="2886c-151">如果不需要，构造</span><span class="sxs-lookup"><span data-stu-id="2886c-151">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="2886c-152">也是有效的 RUS 模式。</span><span class="sxs-lookup"><span data-stu-id="2886c-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="2886c-153">有关更多示例和详细信息，请参阅本文中的[重复-截止到成功示例](#repeat-until-success-examples)。</span><span class="sxs-lookup"><span data-stu-id="2886c-153">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="2886c-154">避免在函数内使用重复-until 循环。</span><span class="sxs-lookup"><span data-stu-id="2886c-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="2886c-155">使用*while*循环来提供函数内的相应功能。</span><span class="sxs-lookup"><span data-stu-id="2886c-155">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="2886c-156">While 循环</span><span class="sxs-lookup"><span data-stu-id="2886c-156">While loop</span></span>

<span data-ttu-id="2886c-157">重复-直到成功模式有一个非常特定于量程的内涵。</span><span class="sxs-lookup"><span data-stu-id="2886c-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="2886c-158">它们广泛用于特定的量程算法类，因此，它是 Q # 中的专用语言构造。</span><span class="sxs-lookup"><span data-stu-id="2886c-158">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="2886c-159">但是，在编译时，中断的循环会在量程运行时中按特定的小心处理，这种情况下，会在编译时进行中断。</span><span class="sxs-lookup"><span data-stu-id="2886c-159">However, loops that break based on a condition and whose execution length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="2886c-160">但是，它们在函数中的使用是 unproblematic 的，因为这些循环只包含在传统（非量程）硬件上运行的代码。</span><span class="sxs-lookup"><span data-stu-id="2886c-160">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="2886c-161">因此，Q # 支持仅在函数内使用 while 循环。</span><span class="sxs-lookup"><span data-stu-id="2886c-161">Q#, therefore, supports to use of while loops within functions only.</span></span> <span data-ttu-id="2886c-162">`while`语句由关键字 `while` 、括号中的布尔表达式和语句块组成。</span><span class="sxs-lookup"><span data-stu-id="2886c-162">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="2886c-163">只要条件的计算结果为，语句块（循环的主体）将运行 `true` 。</span><span class="sxs-lookup"><span data-stu-id="2886c-163">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a><span data-ttu-id="2886c-164">Return 语句</span><span class="sxs-lookup"><span data-stu-id="2886c-164">Return Statement</span></span>

<span data-ttu-id="2886c-165">Return 语句结束操作或函数的运行，并将值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="2886c-165">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="2886c-166">它包含关键字 `return` ，后跟适当类型的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="2886c-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="2886c-167">例如，</span><span class="sxs-lookup"><span data-stu-id="2886c-167">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="2886c-168">或</span><span class="sxs-lookup"><span data-stu-id="2886c-168">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="2886c-169">返回空元组的可调用 `()` 不需要 return 语句。</span><span class="sxs-lookup"><span data-stu-id="2886c-169">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="2886c-170">若要指定操作或函数的早期退出，请使用 `return ();` 。</span><span class="sxs-lookup"><span data-stu-id="2886c-170">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="2886c-171">返回任何其他类型的 Callables 需要最终的 return 语句。</span><span class="sxs-lookup"><span data-stu-id="2886c-171">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="2886c-172">操作中不存在最大返回语句数。</span><span class="sxs-lookup"><span data-stu-id="2886c-172">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="2886c-173">如果语句在块内跟随 return 语句，则编译器可能会发出警告。</span><span class="sxs-lookup"><span data-stu-id="2886c-173">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="2886c-174">Fail 语句</span><span class="sxs-lookup"><span data-stu-id="2886c-174">Fail statement</span></span>

<span data-ttu-id="2886c-175">Fail 语句结束操作的运行，并将错误值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="2886c-175">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="2886c-176">它包含关键字 `fail` ，后跟一个字符串和一个终止分号。</span><span class="sxs-lookup"><span data-stu-id="2886c-176">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="2886c-177">语句将字符串返回到传统驱动程序作为错误消息。</span><span class="sxs-lookup"><span data-stu-id="2886c-177">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="2886c-178">操作中的 fail 语句数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="2886c-178">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="2886c-179">如果语句在块中跟随 fail 语句，则编译器可能会发出警告。</span><span class="sxs-lookup"><span data-stu-id="2886c-179">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="2886c-180">例如，</span><span class="sxs-lookup"><span data-stu-id="2886c-180">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="2886c-181">或者，使用内[插字符串](xref:microsoft.quantum.guide.expressions#interpolated-strings)</span><span class="sxs-lookup"><span data-stu-id="2886c-181">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="2886c-182">重复执行-直到成功示例</span><span class="sxs-lookup"><span data-stu-id="2886c-182">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="2886c-183">针对无理数轴的单 qubit 旋转的 RUS 模式</span><span class="sxs-lookup"><span data-stu-id="2886c-183">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="2886c-184">在典型用例中，以下 Q # 操作实现绕 Bloch 球上的无理数轴（I + 2i Z）/\sqrt $ 围绕 {5} 的旋转。</span><span class="sxs-lookup"><span data-stu-id="2886c-184">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="2886c-185">实现使用已知的 RUS 模式：</span><span class="sxs-lookup"><span data-stu-id="2886c-185">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="2886c-186">作用域中具有可变变量的 ru 循环</span><span class="sxs-lookup"><span data-stu-id="2886c-186">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="2886c-187">此示例演示如何使用可变变量，该变量在 `finished` 整个重复截止到延迟的循环范围内，并在循环之前进行初始化并在修正步骤中更新。</span><span class="sxs-lookup"><span data-stu-id="2886c-187">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="2886c-188">不带`fixup`</span><span class="sxs-lookup"><span data-stu-id="2886c-188">RUS without `fixup`</span></span>

<span data-ttu-id="2886c-189">此示例显示了不带修正步骤的 ru 循环。</span><span class="sxs-lookup"><span data-stu-id="2886c-189">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="2886c-190">此代码是一种概率线路，它使用和入口实现重要的旋转门 $V _3 = （\boldone + 2 i Z）/\sqrt {5} $ `H` `T` 。</span><span class="sxs-lookup"><span data-stu-id="2886c-190">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="2886c-191">该循环平均终止 $ \frac {8} {5} $ 重复。</span><span class="sxs-lookup"><span data-stu-id="2886c-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="2886c-192">有关更多详细信息，请参阅[*qubit unitaries 的非确定性分解*](https://arxiv.org/abs/1311.1074)（Paetznick 和 Svore，2014）。</span><span class="sxs-lookup"><span data-stu-id="2886c-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="2886c-193">用于准备量子状态的 ru</span><span class="sxs-lookup"><span data-stu-id="2886c-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="2886c-194">最后，下面是一个用于 {1} {3} {2} {0} {1} 从 $ \ket +} $ 状态中获取量程状态 $ \frac {\sqrt} \left （\sqrt \ket + \right \ket{） $ 的 ru 模式的示例。</span><span class="sxs-lookup"><span data-stu-id="2886c-194">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="2886c-195">此操作中所示的明显编程功能包括：</span><span class="sxs-lookup"><span data-stu-id="2886c-195">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="2886c-196">`fixup`循环中涉及量程操作的更为复杂的部分。</span><span class="sxs-lookup"><span data-stu-id="2886c-196">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="2886c-197">使用 `AssertProb` 语句来确定在程序中的某些指定点测量量程状态的概率。</span><span class="sxs-lookup"><span data-stu-id="2886c-197">The use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="2886c-198">有关和操作的详细 [`Assert`](xref:microsoft.quantum.intrinsic.assert) 信息 [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) ，请参阅[测试和调试](xref:microsoft.quantum.guide.testingdebugging)。</span><span class="sxs-lookup"><span data-stu-id="2886c-198">For more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

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

<span data-ttu-id="2886c-199">有关详细信息，请参阅[随标准库提供的单元测试示例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：</span><span class="sxs-lookup"><span data-stu-id="2886c-199">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="2886c-200">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2886c-200">Next steps</span></span>

<span data-ttu-id="2886c-201">了解问题解答 # 中的[测试和调试](xref:microsoft.quantum.guide.testingdebugging)。</span><span class="sxs-lookup"><span data-stu-id="2886c-201">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
