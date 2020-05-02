---
title: 'Q # 表达式'
description: '了解如何指定、引用和组合常量、变量、运算符、操作和函数作为 Q # 中的表达式。'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683927"
---
# <a name="expressions"></a><span data-ttu-id="6f0c5-103">表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="6f0c5-104">分组</span><span class="sxs-lookup"><span data-stu-id="6f0c5-104">Grouping</span></span>

<span data-ttu-id="6f0c5-105">给定任意表达式，括在括号中的同一表达式是同一类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="6f0c5-106">例如`(7)` ，是一个`Int`表达式， `([1,2,3])`是类型为的数组的表达式， `Int` `((1,2))`是类型`(Int, Int)`为的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="6f0c5-107">[类型模型](xref:microsoft.quantum.language.type-model#tuple-types)中所述的简单值和单元素元组之间的等效性会消除`(6)`作为组和`(6)`作为单元素元组之间的多义性。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="6f0c5-108">符号</span><span class="sxs-lookup"><span data-stu-id="6f0c5-108">Symbols</span></span>

<span data-ttu-id="6f0c5-109">绑定的符号或赋给类型`'T`的值的名称是类型`'T`的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="6f0c5-110">例如，如果符号`count`绑定到整数值`5`，则`count`是整数表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="6f0c5-111">数值表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-111">Numeric Expressions</span></span>

<span data-ttu-id="6f0c5-112">数值表达式是、 `Int` `BigInt`或`Double`类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="6f0c5-113">也就是说，它们是整数或浮点数。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="6f0c5-114">`Int`Q # 中的文本与 c # 中的整数文本相同，不同之处在于不需要尾随 "l" 或 "L" （或允许）。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="6f0c5-115">十六进制和二进制整数分别支持 "0x" 和 "0b" 前缀。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="6f0c5-116">`BigInt`Q # 中的文本与 .NET 中的大整数字符串相同，尾随 "l" 或 "L"。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="6f0c5-117">支持使用 "0x" 前缀的十六进制大整数。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="6f0c5-118">因此，以下是`BigInt`文本的有效用法：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="6f0c5-119">`Double`Q # 中的文本与 c # 中的 double 文本相同，只不过不需要尾随 "d" 或 "D" （或允许）。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="6f0c5-120">给定任意元素类型的数组表达式，可以使用`Int` `Length`内置函数，使用括在括号中的数组表达式`(`和`)`来构造表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="6f0c5-121">例如，如果`a`绑定到数组，则`Length(a)`是整数表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="6f0c5-122">如果`b`是`Int[][]`整数数组的数组， `Length(b)`则为中`b`的子数组的数目， `Length(b[1])`是中`b`第二个子数组中的整数的数目。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="6f0c5-123">假设两个数值表达式具有相同的类型，则可以`+`使用`-`二元`*`运算符、 `/` 、和形成新的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="6f0c5-124">新表达式的类型将与构成表达式的类型相同。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="6f0c5-125">假设有两个整数表达式，二元`^`运算符（power）可用于构成新的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="6f0c5-126">同样， `^`可以使用两个双表达式来形成新的双精度表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="6f0c5-127">最后， `^`可与左侧的大整数一起使用，并在右侧使用一个整数来形成新的大整数表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="6f0c5-128">在这种情况下，第二个参数必须适合32位;否则，将引发运行时错误。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="6f0c5-129">假设有`%`两个整数或大整数表达式，可以使用（取模）、 `&&&` （位与）、 `|||` （位或）或`^^^` （位 XOR）运算符来形成新的整数或大整数表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="6f0c5-130">给定左侧的整数或大整数表达式，并在右侧输入整数表达式，则`<<<`可以使用（算术左移位）或`>>>` （算术右移位）运算符来创建与左侧表达式具有相同类型的新表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="6f0c5-131">转换操作的第二个参数（移位量）必须大于或等于零;负移位量的行为是不确定的。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="6f0c5-132">移位运算的移位量还必须适合32位;否则，将引发运行时错误。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="6f0c5-133">如果要移位的数字是整数，则会解释`mod 64`移位量;也就是说，1和65的移位都具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="6f0c5-134">对于整数和大整数值，移位均为算术运算。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="6f0c5-135">向左或向右移位负值将导致负数。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="6f0c5-136">也就是说，向左或向右移动一个步骤的方式与2的乘法或除法完全相同。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="6f0c5-137">对于负数，整数除法和整数取模的行为与 c # 的行为相同。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="6f0c5-138">也就是说， `a % b`将始终具有相同的符号`a`，并`b * (a / b) + a % b`始终相等。 `a`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="6f0c5-139">例如：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="6f0c5-140">5</span><span class="sxs-lookup"><span data-stu-id="6f0c5-140">5</span></span> | <span data-ttu-id="6f0c5-141">2</span><span class="sxs-lookup"><span data-stu-id="6f0c5-141">2</span></span> | <span data-ttu-id="6f0c5-142">2</span><span class="sxs-lookup"><span data-stu-id="6f0c5-142">2</span></span> | <span data-ttu-id="6f0c5-143">1</span><span class="sxs-lookup"><span data-stu-id="6f0c5-143">1</span></span>
 <span data-ttu-id="6f0c5-144">5</span><span class="sxs-lookup"><span data-stu-id="6f0c5-144">5</span></span> | <span data-ttu-id="6f0c5-145">-2</span><span class="sxs-lookup"><span data-stu-id="6f0c5-145">-2</span></span> | <span data-ttu-id="6f0c5-146">-2</span><span class="sxs-lookup"><span data-stu-id="6f0c5-146">-2</span></span> | <span data-ttu-id="6f0c5-147">1</span><span class="sxs-lookup"><span data-stu-id="6f0c5-147">1</span></span>
 <span data-ttu-id="6f0c5-148">-5</span><span class="sxs-lookup"><span data-stu-id="6f0c5-148">-5</span></span> | <span data-ttu-id="6f0c5-149">2</span><span class="sxs-lookup"><span data-stu-id="6f0c5-149">2</span></span> | <span data-ttu-id="6f0c5-150">-2</span><span class="sxs-lookup"><span data-stu-id="6f0c5-150">-2</span></span> | <span data-ttu-id="6f0c5-151">-1</span><span class="sxs-lookup"><span data-stu-id="6f0c5-151">-1</span></span>
 <span data-ttu-id="6f0c5-152">-5</span><span class="sxs-lookup"><span data-stu-id="6f0c5-152">-5</span></span> | <span data-ttu-id="6f0c5-153">-2</span><span class="sxs-lookup"><span data-stu-id="6f0c5-153">-2</span></span> | <span data-ttu-id="6f0c5-154">2</span><span class="sxs-lookup"><span data-stu-id="6f0c5-154">2</span></span> | <span data-ttu-id="6f0c5-155">-1</span><span class="sxs-lookup"><span data-stu-id="6f0c5-155">-1</span></span>

<span data-ttu-id="6f0c5-156">大整数除法和取模的工作方式相同。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="6f0c5-157">如果给定了数值表达式，则可以使用`-`一元运算符构造新的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="6f0c5-158">新表达式将与构成表达式的类型相同。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="6f0c5-159">给定任意整数或大整数表达式时，可以使用`~~~` （按位求补）一元运算符来构造相同类型的新表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="6f0c5-160">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-160">Boolean Expressions</span></span>

<span data-ttu-id="6f0c5-161">这两`Bool`个文本值`true`为`false`和。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="6f0c5-162">给定任意两个具有相同基元类型的表达式， `==`和`!=`二元运算符可用于构造`Bool`表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="6f0c5-163">如果两个表达式相等，则表达式将为 true; 否则为 false。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="6f0c5-164">不能比较用户定义类型的值，只能比较它们的解包值。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="6f0c5-165">例如，使用 "解包" 运算符`!` （在 " [Q # 类型模型" 页](xref:microsoft.quantum.language.type-model#user-defined-types)中介绍），</span><span class="sxs-lookup"><span data-stu-id="6f0c5-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="6f0c5-166">值的`Qubit`相等比较是恒等的;也就是说，这两个表达式是否标识同一 qubit。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="6f0c5-167">这两个 qubits 的状态不会进行比较、访问、度量或修改。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="6f0c5-168">由于舍入`Double`效果，值的相等比较可能会产生误导。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="6f0c5-169">例如， `49.0 * (1.0/49.0) != 1.0`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="6f0c5-170">给定任意两个数值表达式，二元运算符`>`、 `<` `>=`、和`<=`可用于构造新的布尔表达式，如果第一个表达式分别大于、小于、大于或等于，或者小于或等于第二个表达式，则该值为 true。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="6f0c5-171">给定任意两个布尔表达式， `and`和`or`二元运算符可用于构造新的布尔表达式，如果这两个表达式都为 true，则这两个表达式均为 true。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="6f0c5-172">给定任何布尔表达式， `not`一元运算符可用于构造新的布尔表达式，如果构成表达式为 false，则为 true。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="6f0c5-173">字符串表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-173">String Expressions</span></span>

<span data-ttu-id="6f0c5-174">Q # 允许在`fail`语句和`Log`标准函数中使用字符串。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="6f0c5-175">Q # 中的字符串是文本或内插字符串。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="6f0c5-176">字符串文本类似于大多数语言中的简单字符串文本：括在双引号中的 Unicode 字符序列`"`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="6f0c5-177">在字符串中， `\`反斜杠字符可用于转义双引号字符，还可以将新行作为`\n`、回车符`\r`和制表符插入到中。 `\t`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="6f0c5-178">例如：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="6f0c5-179">字符串内插的 Q # 语法是 c # 7.0 语法的子集;Q # 不支持逐字（多行）内插字符串。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="6f0c5-180">请参阅 c # 语法的内[*插字符串*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="6f0c5-181">内插字符串中的表达式遵循 Q # 语法，而不是 c # 语法。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="6f0c5-182">任何有效的 Q # 表达式都可以出现在内插字符串中。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="6f0c5-183">Qubit 表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-183">Qubit Expressions</span></span>

<span data-ttu-id="6f0c5-184">唯一`Qubit`的表达式是绑定到`Qubit`数组的`Qubit`值或数组元素的符号。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="6f0c5-185">没有`Qubit`文本。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="6f0c5-186">Pauli 表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-186">Pauli Expressions</span></span>

<span data-ttu-id="6f0c5-187">四个`Pauli`值（ `PauliI`、 `PauliX` `PauliY`、和`PauliZ`）都是有效`Pauli`的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="6f0c5-188">除了这样，唯一`Pauli`的表达式是绑定到`Pauli`数组的`Pauli`值或数组元素的符号。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="6f0c5-189">结果表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-189">Result Expressions</span></span>

<span data-ttu-id="6f0c5-190">和都是有效`Result`的表达式。 `Zero` `Result` `One`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="6f0c5-191">除了这样，唯一`Result`的表达式是绑定到`Result`数组的`Result`值或数组元素的符号。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="6f0c5-192">特别要注意的`One`是，与整数`1`不同，它们之间没有直接转换。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="6f0c5-193">对于`Zero`和`0`也是如此。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="6f0c5-194">范围表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-194">Range Expressions</span></span>

<span data-ttu-id="6f0c5-195">给定任意三`Int`个`start`表达式`step`，和`stop` `start .. step .. stop`是一个范围表达式，其第一个元素`start`是，第二`start+step`个元素是， `start+step+step`第三个元素为`stop` ，依此类推，直到传递。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="6f0c5-196">例如， `step`如果为正值，则范围可能为空`stop < start`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="6f0c5-197">如果`stop`与之间`start`的差异是的`stop` `step`整数倍数，则范围的最后一个元素将为;也就是说，范围两端都包含。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="6f0c5-198">给定任意两`Int`个`start`表达式`stop`和`start .. stop` ，是等于的范围表达式`start .. 1 .. stop`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="6f0c5-199">请注意，即使`step`小于`stop` ，隐含也是 + 1 `start`;在这种情况下，该范围为空。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="6f0c5-200">一些示例范围如下：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-200">Some example ranges are:</span></span>

- <span data-ttu-id="6f0c5-201">`1..3`的范围为1、2、3。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="6f0c5-202">`2..2..5`范围为2、4。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="6f0c5-203">`2..2..6`范围为2、4、6。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="6f0c5-204">`6..-2..2`范围为6、4、2。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="6f0c5-205">`2..1`为空范围。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="6f0c5-206">`2..6..7`范围为2。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="6f0c5-207">`2..2..1`为空范围。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="6f0c5-208">`1..-1..2`为空范围。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="6f0c5-209">可调用表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-209">Callable Expressions</span></span>

<span data-ttu-id="6f0c5-210">可调用的文本是编译范围中定义的操作或函数的名称。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="6f0c5-211">例如， `X`是引用标准库`X`操作的操作文本， `Message`是引用标准库`Message`函数的函数文本。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="6f0c5-212">如果操作支持`Adjoint`函子，则`Adjoint op`是操作表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="6f0c5-213">同样，如果操作支持`Controlled`函子，则`Controlled op`是操作表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="6f0c5-214">这些表达式的类型在[函子](xref:microsoft.quantum.language.type-model#functors)中指定。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="6f0c5-215">除解`Adjoint`包`Controlled`运算符`!`和数组索引外，函子（和）与`[]`其他所有运算符更紧密地绑定。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="6f0c5-216">因此，以下各项均为合法，前提是这些操作支持使用的函子：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="6f0c5-217">可调用的文本可用作值，假设要分配给变量或传递给其他可调用的。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="6f0c5-218">在这种情况下，如果可调用的具有类型参数，则必须将它们作为可调用值的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="6f0c5-219">可调用的值不能具有任何未指定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="6f0c5-220">例如，如果`Fun`是具有签名`'T1->Unit`的函数：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="6f0c5-221">可调用调用表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="6f0c5-222">给定可调用（操作或函数）表达式和可调用签名的输入类型的元组表达式时，可以通过将元组表达式追加到可调用表达式来形成调用表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="6f0c5-223">调用表达式的类型是可调用的签名的输出类型。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="6f0c5-224">例如， `Op`如果是具有`((Int, Qubit) => Double)`签名的操作， `Op(3, qubit1)`则为类型`Double`的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6f0c5-225">同样，如果`Sin`是具有签名`(Double -> Double)`的函数， `Sin(0.1)`则是类型`Double`的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6f0c5-226">最后，如果`Builder`是具有签名`(Int -> (Int -> Int))`的函数，则`Builder(3)`是从到 Int 的函数。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="6f0c5-227">若要调用可调用值表达式的结果，需要在可调用的表达式前后使用一对括号。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="6f0c5-228">因此，若要调用上一段落`Builder`中调用的结果，正确的语法为：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="6f0c5-229">调用类型参数化的可调用时，可以在尖括号`<`和`>`可调用表达式之后指定实际的类型参数。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="6f0c5-230">这通常是不必要的，因为 Q # 编译器将推断实际类型。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="6f0c5-231">如果未指定类型参数化的参数，则此参数对于部分应用程序是必需的（见下文）。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="6f0c5-232">在将具有不同函子支持的操作传递给可调用时，有时也很有用。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="6f0c5-233">`Func`例如，如果具有签名`('T1, 'T2, 'T1) -> 'T2`， `Op1`并`Op2` `(Qubit[] => Unit is Adj)`具有签名，并`Op3`具有签名`(Qubit[] => Unit)`，则将使用`Func` `Op1`作为第一个参数进行调用`Op2` ，并`Op3`将作为第二个参数，第三个参数为：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="6f0c5-234">类型规范是必需的， `Op3`因为`Op1`和具有不同的类型，因此，如果没有规范，编译器会将此视为不明确的。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="6f0c5-235">部分应用程序</span><span class="sxs-lookup"><span data-stu-id="6f0c5-235">Partial Application</span></span>

<span data-ttu-id="6f0c5-236">给定可调用的表达式，可以通过向可调用的参数提供一个子集来创建新的可调用的。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="6f0c5-237">这称为_部分应用程序_。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-237">This is called _partial application_.</span></span>

<span data-ttu-id="6f0c5-238">在 Q # 中，部分应用的可调用通过编写常规调用表达式来表示，但对于未指定`_`的参数使用下划线。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="6f0c5-239">生成的可调用与基可调用的结果类型相同，并且具有相同的操作专用化。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="6f0c5-240">部分应用程序的输入类型只是删除了指定参数的原始类型。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="6f0c5-241">如果在创建部分应用程序时将可变变量作为指定参数传递，则使用该变量的当前值。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="6f0c5-242">此后更改变量的值不会影响部分应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="6f0c5-243">例如，如果`Op`具有类型`((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="6f0c5-244">`Op(5,(_,_))`具有类型`(((Qubit,Qubit), Double) => Unit is Adj)`，因此具有`Op(5,_)`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="6f0c5-245">`Op(_,(_,1.0))` 的类型为 `((Int, (Qubit,Qubit)) => Unit is Adj)`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="6f0c5-246">`Op(_,((q1,q2),_))` 的类型为 `((Int,Double) => Unit is Adj)`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="6f0c5-247">请注意，我们已在此处应用了单一元组等效性。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="6f0c5-248">如果部分应用的可调用具有编译器无法推断的类型参数，则这些参数必须在调用站点提供。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="6f0c5-249">部分应用程序不能具有任何未指定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="6f0c5-250">例如，如果`Op`具有类型`(('T1, Qubit, 'T1) => Unit : Adjoint)`：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="6f0c5-251">递归</span><span class="sxs-lookup"><span data-stu-id="6f0c5-251">Recursion</span></span>

<span data-ttu-id="6f0c5-252">Q # callables 允许直接或间接递归。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="6f0c5-253">也就是说，操作或函数可能调用自身，或者它可能调用直接或间接调用可调用操作的另一个可调用的。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="6f0c5-254">不过，有两个关于递归使用的重要说明：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="6f0c5-255">在操作中使用递归可能会干扰某些优化。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="6f0c5-256">这可能会对算法的执行时间产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="6f0c5-257">在实际的量程设备上执行时，堆栈空间可能会受到限制，因此深度递归可能导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="6f0c5-258">特别是，Q # 编译器和运行时不标识和优化尾递归。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="6f0c5-259">元组表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-259">Tuple Expressions</span></span>

<span data-ttu-id="6f0c5-260">元组文本是一系列以逗号分隔的合适类型的元素表达式，括在和`(` `)`中。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="6f0c5-261">例如， `(1, One)`是一个`(Int, Result)`表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="6f0c5-262">除了文本以外，唯一的元组表达式是绑定到元组值、元组数组的数组元素和返回元组的可调用调用的符号。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="6f0c5-263">用户定义的类型表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="6f0c5-264">用户定义类型的文本包含类型名称，后跟类型的基元组类型的元组文本。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="6f0c5-265">例如，如果`IntPair`是基于的用户定义类型`(Int, Int)`，则`IntPair(2,3)`是该类型的有效文本。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="6f0c5-266">除了文本以外，用户定义类型的唯一表达式是绑定到该类型的值、该类型的数组元素和返回该类型的可调用调用的符号。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="6f0c5-267">解包表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-267">Unwrap Expressions</span></span>

<span data-ttu-id="6f0c5-268">在 Q # 中，解包运算符是一个尾随引号`!`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="6f0c5-269">例如，如果`IntPair`是具有`(Int, Int)`基础类型的用户定义类型，并且`s`是具有值`IntPair(2,3)`的变量，则`s!`将为。 `(2,3)`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="6f0c5-270">对于根据其他用户定义类型定义的用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="6f0c5-271">可以重复解包运算符;例如， `s!!`指示的双重解包值`s`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="6f0c5-272">因此，如果`WrappedPair`是具有基础类型`IntPair` `t`的用户定义类型，并且是具有值`WrappedPair(IntPair(1,2))`的变量，则`t!!`将为。 `(1,2)`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="6f0c5-273">`!`运算符的优先级高于除数组索引和切片以外`[]`的其他所有运算符。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="6f0c5-274">`!`并`[]`绑定按位置;也就是说， `a[i]![3]`应如下所示`((a[i])!)[3]`：取`i`的第一个`a`元素，将其解包，然后获取解包值（必须是数组）的第3个元素。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="6f0c5-275">`!`运算符的优先级有一个可能不明显的影响。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="6f0c5-276">如果函数或操作返回一个值，则该函数或操作调用必须括在括号中，以便参数元组绑定到该调用，而不是绑定到解包。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="6f0c5-277">例如：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="6f0c5-278">数组表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-278">Array Expressions</span></span>

<span data-ttu-id="6f0c5-279">数组文字是由`[`和`]`括起来的由逗号分隔的一个或多个元素表达式的序列。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="6f0c5-280">所有元素都必须兼容同一类型。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="6f0c5-281">如果公共元素类型是运算或函数类型，则所有元素必须具有相同的输入和输出类型。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="6f0c5-282">数组的元素类型将支持所有元素支持的任何函子。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="6f0c5-283">`Op1`例如，如果、 `Op2`和`Op3`都是`Qubit[] => Unit`， `Op1` `Adjoint` `Op2` `Controlled`则支持、支持和`Op3`均支持：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6f0c5-284">`[Op1, Op2]`是一组`(Qubit[] => Unit)`操作。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="6f0c5-285">`[Op1, Op3]`是一组`(Qubit[] => Unit is Adj)`操作。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="6f0c5-286">`[Op2, Op3]`是一组`(Qubit[] => Unit is Ctl)`操作。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="6f0c5-287">不允许空数组`[]`文本。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="6f0c5-288">而是`new ★[0]`使用， `★`其中作为适当类型的占位符，允许创建长度为零的所需数组。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="6f0c5-289">如果给定两个相同类型的数组，则`+`可以使用二元运算符形成一个新数组，该数组是两个数组的串联。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="6f0c5-290">例如， `[1,2,3] + [4,5,6]`为`[1,2,3,4,5,6]`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="6f0c5-291">数组创建</span><span class="sxs-lookup"><span data-stu-id="6f0c5-291">Array Creation</span></span>

<span data-ttu-id="6f0c5-292">给定类型和`Int`表达式后， `new`运算符可用于分配给定大小的新数组。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="6f0c5-293">例如， `new Int[i+1]`将使用`Int` `i+1`元素分配新数组。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="6f0c5-294">新数组的元素被初始化为依赖于类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="6f0c5-295">在大多数情况下，这是零的一些变体。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="6f0c5-296">对于引用实体的 qubits 和 callables，没有合理的默认值。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="6f0c5-297">因此，对于这些类型，默认值是无效的引用，不能使用而不会导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="6f0c5-298">这类似于 c # 或 Java 等语言的空引用。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="6f0c5-299">必须使用非默认值正确地初始化包含 qubits 或 callables 的数组，才能安全地使用其元素。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="6f0c5-300">可在中找到合适的<xref:microsoft.quantum.arrays>初始化例程。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="6f0c5-301">每种类型的默认值为：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-301">The default values for each type are:</span></span>

<span data-ttu-id="6f0c5-302">类型</span><span class="sxs-lookup"><span data-stu-id="6f0c5-302">Type</span></span> | <span data-ttu-id="6f0c5-303">默认</span><span class="sxs-lookup"><span data-stu-id="6f0c5-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="6f0c5-304">_无效的 qubit_</span><span class="sxs-lookup"><span data-stu-id="6f0c5-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="6f0c5-305">空范围，`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="6f0c5-306">_调用无效_</span><span class="sxs-lookup"><span data-stu-id="6f0c5-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="6f0c5-307">元组类型是逐个元素初始化的。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="6f0c5-308">交错数组</span><span class="sxs-lookup"><span data-stu-id="6f0c5-308">Jagged Arrays</span></span>

<span data-ttu-id="6f0c5-309">交错数组，有时称为 "数组数组"，是元素为数组的数组。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="6f0c5-310">交错数组的元素的大小可以不同。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="6f0c5-311">下面的示例演示如何声明和初始化表示乘法表的交错数组。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {

    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```


### <a name="array-slices"></a><span data-ttu-id="6f0c5-312">数组切片</span><span class="sxs-lookup"><span data-stu-id="6f0c5-312">Array Slices</span></span>

<span data-ttu-id="6f0c5-313">给定数组表达式和`Range`表达式时，可以使用`[`和`]`数组切片运算符构造一个新的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="6f0c5-314">新表达式将与数组的类型相同，并将包含由的`Range`元素编制索引的数组项（按定义的顺序）。 `Range`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="6f0c5-315">例如， `a`如果绑定到的`Double`数组，则`a[3..-1..0]`是一个`Double[]`表达式，该表达式包含的`a`前四个元素，但其显示顺序与中的顺序相反。 `a`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="6f0c5-316">如果`Range`为空，则生成的数组切片长度为零。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="6f0c5-317">如果数组表达式不是简单的标识符，则必须将其括在括号中，以便进行切片。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="6f0c5-318">例如，如果`a`和`b`都是的`Int`数组，则串联的切片将表示为：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="6f0c5-319">Q # 中的所有数组都是从零开始的。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="6f0c5-320">也就是说，数组`a`的第一个元素始终`a[0]`为。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="6f0c5-321">从0.8 版本开始，我们支持范围切片的上下文表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="6f0c5-322">具体而言，范围切片表达式的上下文中可能会省略范围起始值和结束值。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="6f0c5-323">在这种情况下，编译器将应用以下规则来推导范围的预期分隔符。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="6f0c5-324">例如，如果省略范围起始值，则推断出的起始值</span><span class="sxs-lookup"><span data-stu-id="6f0c5-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="6f0c5-325">如果未指定步骤或指定步骤为正值，则为零;</span><span class="sxs-lookup"><span data-stu-id="6f0c5-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6f0c5-326">如果指定的步骤为负，则为切片的数组的长度减去1。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="6f0c5-327">如果省略范围结束值，则推断出的结束值</span><span class="sxs-lookup"><span data-stu-id="6f0c5-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="6f0c5-328">如果未指定步骤或指定步骤为正值，则切片数组的长度减1</span><span class="sxs-lookup"><span data-stu-id="6f0c5-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6f0c5-329">如果指定的步骤为负数，则为零。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-329">is zero if the specified step is negative.</span></span> 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

## <a name="array-element-expressions"></a><span data-ttu-id="6f0c5-330">数组元素表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-330">Array Element Expressions</span></span>

<span data-ttu-id="6f0c5-331">给定数组表达式和`Int`表达式时，可以使用`[`和`]`数组元素运算符构造一个新的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="6f0c5-332">新表达式将与数组的元素类型相同。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="6f0c5-333">例如， `a`如果绑定到`Double`的数组，则`a[4]`是一个`Double`表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="6f0c5-334">如果数组表达式不是简单的标识符，则必须将其括在括号中，以便选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="6f0c5-335">例如，如果`a`和`b`都是的`Int`数组，则连接中的元素将表示为：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="6f0c5-336">Q # 中的所有数组都是从零开始的。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="6f0c5-337">也就是说，数组`a`的第一个元素始终`a[0]`为。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="6f0c5-338">复制和更新表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="6f0c5-339">可以通过复制和更新表达式从现有阵列创建新的阵列。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="6f0c5-340">复制和更新表达式是窗`expression1 w/ expression2 <- expression3`体的表达式，其中`expression1`必须是某种类型`T[]` `T`的类型。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="6f0c5-341">第二`expression2`个定义要修改的元素的索引，该索引与中`expression1`的数组进行比较，并且必须是类型的`Int`类型或`Range`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="6f0c5-342">如果`expression2`的类型`Int`为， `expression3`则必须为类型`T`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="6f0c5-343">如果`expression2`的类型`Range`为， `expression3`则必须为类型`T[]`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="6f0c5-344">复制`arr w/ idx <- value`和更新表达式构造一个新数组，其中所有元素都设置为中`arr`的相应元素，但中的元素除外`idx`，后者设置为中`value`的一个。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="6f0c5-345">例如，如果`arr`包含一个数组`[0,1,2,3]`，则</span><span class="sxs-lookup"><span data-stu-id="6f0c5-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="6f0c5-346">`arr w/ 0 <- 10`是数组`[10,1,2,3]`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="6f0c5-347">`arr w/ 2 <- 10`是数组`[0,1,10,3]`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="6f0c5-348">`arr w/ 0..2..3 <- [10,12]`是数组`[10,1,12,3]`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="6f0c5-349">对于用户定义类型中的命名项，存在类似的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="6f0c5-350">例如，请考虑类型</span><span class="sxs-lookup"><span data-stu-id="6f0c5-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="6f0c5-351">如果`c`包含类型`Complex(1.,-1.)`的值，则`c w/ Re <- 0.`是类型`Complex`的表达式，其计算结果为`Complex(0.,-1.)`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="6f0c5-352">条件表达式</span><span class="sxs-lookup"><span data-stu-id="6f0c5-352">Conditional Expressions</span></span>

<span data-ttu-id="6f0c5-353">假设有两个具有相同类型和布尔表达式的其他表达式，则可以使用问号`?`和竖线构造条件表达式。 `|`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="6f0c5-354">例如， `a==b ? c | d`。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="6f0c5-355">在此示例中，如果`c` `a==b`为 true， `d`则条件表达式的值为; 如果为 false，则为。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="6f0c5-356">这两个表达式的计算结果可能为具有相同输入和输出但支持不同函子的操作。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="6f0c5-357">在这种情况下，条件表达式的类型是一个操作，其中包含支持两个表达式支持的任何函子的输入和输出。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="6f0c5-358">`Op1`例如，如果、 `Op2`和`Op3`都是`Qubit[]=>Unit`， `Op1` `Adjoint` `Op2` `Controlled`则支持、支持和`Op3`均支持：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6f0c5-359">`flag ? Op1 | Op2`为`(Qubit[] => Unit)`操作。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="6f0c5-360">`flag ? Op1 | Op3`为`(Qubit[] => Unit is Adj)`操作。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="6f0c5-361">`flag ? Op2 | Op3`为`(Qubit[] => Unit is Ctl)`操作。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="6f0c5-362">如果两个可能的结果表达式中有一个包含函数或操作调用，则只会在该结果是调用的值时进行调用。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="6f0c5-363">例如，在这种情况`a==b ? C(qs) | D(qs)`下， `a==b`如果为 true， `C`则将调用操作，如果为 false，则只`D`调用。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="6f0c5-364">这类似于其他语言的短路。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="6f0c5-365">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="6f0c5-365">Operator Precedence</span></span>

<span data-ttu-id="6f0c5-366">除了之外，所有二元运算符都是右结合`^`运算符。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="6f0c5-367">`[`对于数组切片和索引，请在任何运算符之前`]`绑定。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="6f0c5-368">数组索引`Adjoint`后`Controlled` ，但在所有其他运算符之前，函子和绑定。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="6f0c5-369">用于运算和函数调用的括号也绑定在任何运算符之前，但在数组索引和函子之后。</span><span class="sxs-lookup"><span data-stu-id="6f0c5-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="6f0c5-370">按优先顺序排列的运算符，从高到低：</span><span class="sxs-lookup"><span data-stu-id="6f0c5-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="6f0c5-371">操作员</span><span class="sxs-lookup"><span data-stu-id="6f0c5-371">Operator</span></span> | <span data-ttu-id="6f0c5-372">元</span><span class="sxs-lookup"><span data-stu-id="6f0c5-372">Arity</span></span> | <span data-ttu-id="6f0c5-373">说明</span><span class="sxs-lookup"><span data-stu-id="6f0c5-373">Description</span></span> | <span data-ttu-id="6f0c5-374">操作数类型</span><span class="sxs-lookup"><span data-stu-id="6f0c5-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="6f0c5-375">加`!`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-375">trailing `!`</span></span> | <span data-ttu-id="6f0c5-376">一元</span><span class="sxs-lookup"><span data-stu-id="6f0c5-376">Unary</span></span> | <span data-ttu-id="6f0c5-377">解包</span><span class="sxs-lookup"><span data-stu-id="6f0c5-377">Unwrap</span></span> | <span data-ttu-id="6f0c5-378">任何用户定义类型</span><span class="sxs-lookup"><span data-stu-id="6f0c5-378">Any user-defined type</span></span>
 <span data-ttu-id="6f0c5-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="6f0c5-380">一元</span><span class="sxs-lookup"><span data-stu-id="6f0c5-380">Unary</span></span> | <span data-ttu-id="6f0c5-381">数值负，按位求补，逻辑求反</span><span class="sxs-lookup"><span data-stu-id="6f0c5-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="6f0c5-382">`Int`对于`BigInt` ， `Double`为`-`或`Int` `BigInt` `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="6f0c5-383">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-383">Binary</span></span> | <span data-ttu-id="6f0c5-384">整数幂</span><span class="sxs-lookup"><span data-stu-id="6f0c5-384">Integer power</span></span> | <span data-ttu-id="6f0c5-385">`Int`对于`BigInt`指数， `Int`为或</span><span class="sxs-lookup"><span data-stu-id="6f0c5-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="6f0c5-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="6f0c5-387">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-387">Binary</span></span> | <span data-ttu-id="6f0c5-388">除法、乘法、integer 模数</span><span class="sxs-lookup"><span data-stu-id="6f0c5-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="6f0c5-389">`Int``Double` `BigInt` `*`对于`Int`或为`/` `BigInt``%`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="6f0c5-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-390">`+`, `-`</span></span> | <span data-ttu-id="6f0c5-391">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-391">Binary</span></span> | <span data-ttu-id="6f0c5-392">加法或 string 和 array 串联，减法</span><span class="sxs-lookup"><span data-stu-id="6f0c5-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="6f0c5-393">`Int`、 `BigInt`或`Double`，另外`String`或任何类型的数组类型`+`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="6f0c5-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="6f0c5-395">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-395">Binary</span></span> | <span data-ttu-id="6f0c5-396">左移、右移</span><span class="sxs-lookup"><span data-stu-id="6f0c5-396">Left shift, right shift</span></span> | <span data-ttu-id="6f0c5-397">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="6f0c5-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="6f0c5-399">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-399">Binary</span></span> | <span data-ttu-id="6f0c5-400">小于、小于或等于、大于、大于等于或等于比较的比较</span><span class="sxs-lookup"><span data-stu-id="6f0c5-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="6f0c5-401">`Int`， `BigInt`或`Double`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="6f0c5-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-402">`==`, `!=`</span></span> | <span data-ttu-id="6f0c5-403">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-403">Binary</span></span> | <span data-ttu-id="6f0c5-404">相等，不等于比较</span><span class="sxs-lookup"><span data-stu-id="6f0c5-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="6f0c5-405">任何基元类型</span><span class="sxs-lookup"><span data-stu-id="6f0c5-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="6f0c5-406">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-406">Binary</span></span> | <span data-ttu-id="6f0c5-407">位与</span><span class="sxs-lookup"><span data-stu-id="6f0c5-407">Bitwise AND</span></span> | <span data-ttu-id="6f0c5-408">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="6f0c5-409">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-409">Binary</span></span> | <span data-ttu-id="6f0c5-410">按位“异或”</span><span class="sxs-lookup"><span data-stu-id="6f0c5-410">Bitwise XOR</span></span> | <span data-ttu-id="6f0c5-411">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="6f0c5-412">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-412">Binary</span></span> | <span data-ttu-id="6f0c5-413">按位“或”</span><span class="sxs-lookup"><span data-stu-id="6f0c5-413">Bitwise OR</span></span> | <span data-ttu-id="6f0c5-414">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="6f0c5-415">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-415">Binary</span></span> | <span data-ttu-id="6f0c5-416">逻辑与</span><span class="sxs-lookup"><span data-stu-id="6f0c5-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="6f0c5-417">Binary</span><span class="sxs-lookup"><span data-stu-id="6f0c5-417">Binary</span></span> | <span data-ttu-id="6f0c5-418">逻辑或</span><span class="sxs-lookup"><span data-stu-id="6f0c5-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="6f0c5-419">二进制/三元</span><span class="sxs-lookup"><span data-stu-id="6f0c5-419">Binary/Ternary</span></span> | <span data-ttu-id="6f0c5-420">范围运算符</span><span class="sxs-lookup"><span data-stu-id="6f0c5-420">Range operator</span></span> | `Int`
 <span data-ttu-id="6f0c5-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-421">`?` `|`</span></span> | <span data-ttu-id="6f0c5-422">三元</span><span class="sxs-lookup"><span data-stu-id="6f0c5-422">Ternary</span></span> | <span data-ttu-id="6f0c5-423">条件逻辑</span><span class="sxs-lookup"><span data-stu-id="6f0c5-423">Conditional</span></span> | <span data-ttu-id="6f0c5-424">`Bool`对于左侧</span><span class="sxs-lookup"><span data-stu-id="6f0c5-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="6f0c5-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="6f0c5-425">`w/` `<-`</span></span> | <span data-ttu-id="6f0c5-426">三元</span><span class="sxs-lookup"><span data-stu-id="6f0c5-426">Ternary</span></span> | <span data-ttu-id="6f0c5-427">复制和更新</span><span class="sxs-lookup"><span data-stu-id="6f0c5-427">Copy-and-update</span></span> | <span data-ttu-id="6f0c5-428">请参阅[复制和更新表达式](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="6f0c5-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
