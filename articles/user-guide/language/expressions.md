---
title: Q 中的类型表达式#
description: '了解如何指定、引用和组合常量、变量、运算符、操作和函数作为 Q # 中的表达式。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 1821df6a3a51a62b44f3ccd96b127577c5db990a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415382"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="87660-103">Q 中的类型表达式#</span><span class="sxs-lookup"><span data-stu-id="87660-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="87660-104">数值表达式</span><span class="sxs-lookup"><span data-stu-id="87660-104">Numeric Expressions</span></span>

<span data-ttu-id="87660-105">数值表达式是、或类型的表达式 `Int` `BigInt` `Double` 。</span><span class="sxs-lookup"><span data-stu-id="87660-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="87660-106">也就是说，它们是整数或浮点数。</span><span class="sxs-lookup"><span data-stu-id="87660-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="87660-107">`Int`Q # 中的文本作为一系列数字写入。</span><span class="sxs-lookup"><span data-stu-id="87660-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="87660-108">支持十六进制和二进制整数 `0x` ，并分别使用和前缀来编写 `0b` 。</span><span class="sxs-lookup"><span data-stu-id="87660-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="87660-109">`BigInt`Q # 中的文本具有尾随 `l` 或 `L` 后缀。</span><span class="sxs-lookup"><span data-stu-id="87660-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="87660-110">支持十六进制大整数，并使用 "0x" 前缀来写入。</span><span class="sxs-lookup"><span data-stu-id="87660-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="87660-111">因此，以下是文本的有效用法 `BigInt` ：</span><span class="sxs-lookup"><span data-stu-id="87660-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="87660-112">`Double`Q # 中的文本是使用十进制数字编写的浮点数。</span><span class="sxs-lookup"><span data-stu-id="87660-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="87660-113">可以使用或不使用小数点、 `.` 或用 "e" 或 "e" 指示的指数部分来编写它们（在这种情况下，只有可能的负号和十进制数字有效）。</span><span class="sxs-lookup"><span data-stu-id="87660-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="87660-114">下面是有效的 `Double` 文本： `0.0` 、 `1.2e5` 、 `1e-5` 。</span><span class="sxs-lookup"><span data-stu-id="87660-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="87660-115">给定任意元素类型的数组表达式，你可以 `Int` 使用 [`Length`](xref:microsoft.quantum.core.length) 内置函数形成表达式，并将数组表达式括在括号中。</span><span class="sxs-lookup"><span data-stu-id="87660-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="87660-116">例如，如果 `a` 绑定到数组，则 `Length(a)` 是整数表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="87660-117">如果 `b` 是整数数组的数组，则 `Int[][]` `Length(b)` 为中的子数组的数目 `b` ， `Length(b[1])` 是中第二个子数组 `b` 中的整数的数目。</span><span class="sxs-lookup"><span data-stu-id="87660-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="87660-118">假设两个数值表达式具有相同的类型，则可以 `+` 使用二元运算符、、 `-` `*` 和 `/` 形成新的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="87660-119">新表达式的类型与构成表达式的类型相同。</span><span class="sxs-lookup"><span data-stu-id="87660-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="87660-120">给定两个整数表达式，使用二元运算符 `^` （power）可形成新的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="87660-121">同样，您还可以使用 `^` with 两个双表达式来形成新的双精度表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="87660-122">最后，可以 `^` 在左侧使用大整数，在右侧使用整数来形成新的大整数表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="87660-123">在这种情况下，第二个参数必须适合32位;如果不是，则引发运行时错误。</span><span class="sxs-lookup"><span data-stu-id="87660-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="87660-124">给定两个整数或大整数表达式，使用 `%` （取模）、 `&&&` （位与）、 `|||` （位或）或 `^^^` （位 XOR）运算符形成一个新整数或大整数表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="87660-125">给定左侧的整数或大整数表达式，并在右侧使用整数表达式，使用 `<<<` （算术左移位）或 `>>>` （算术右移位）运算符来创建与左侧表达式具有相同类型的新表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="87660-126">转换操作的第二个参数（移位量）必须大于或等于零;负移位量的行为是不确定的。</span><span class="sxs-lookup"><span data-stu-id="87660-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="87660-127">移位运算的移位量还必须适合32位;如果不是，则引发运行时错误。</span><span class="sxs-lookup"><span data-stu-id="87660-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="87660-128">如果移动的数字是一个整数，则移位量将被解释 `mod 64` ; 也就是说，1的移位和65的移位具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="87660-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="87660-129">对于整数和大整数值，移位均为算术运算。</span><span class="sxs-lookup"><span data-stu-id="87660-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="87660-130">向左或向右移位负值将导致负数。</span><span class="sxs-lookup"><span data-stu-id="87660-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="87660-131">也就是说，向左或向右移动一个步骤的方式与2的乘法或除法相同。</span><span class="sxs-lookup"><span data-stu-id="87660-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="87660-132">对于负数，整数除法和整数取模的行为与 c # 的行为相同。</span><span class="sxs-lookup"><span data-stu-id="87660-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="87660-133">也就是说， `a % b` 始终具有相同的符号 `a` ， `b * (a / b) + a % b` 始终等于 `a` 。</span><span class="sxs-lookup"><span data-stu-id="87660-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span>
<span data-ttu-id="87660-134">例如：</span><span class="sxs-lookup"><span data-stu-id="87660-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="87660-135">5</span><span class="sxs-lookup"><span data-stu-id="87660-135">5</span></span> | <span data-ttu-id="87660-136">2</span><span class="sxs-lookup"><span data-stu-id="87660-136">2</span></span> | <span data-ttu-id="87660-137">2</span><span class="sxs-lookup"><span data-stu-id="87660-137">2</span></span> | <span data-ttu-id="87660-138">1</span><span class="sxs-lookup"><span data-stu-id="87660-138">1</span></span>
 <span data-ttu-id="87660-139">5</span><span class="sxs-lookup"><span data-stu-id="87660-139">5</span></span> | <span data-ttu-id="87660-140">-2</span><span class="sxs-lookup"><span data-stu-id="87660-140">-2</span></span> | <span data-ttu-id="87660-141">-2</span><span class="sxs-lookup"><span data-stu-id="87660-141">-2</span></span> | <span data-ttu-id="87660-142">1</span><span class="sxs-lookup"><span data-stu-id="87660-142">1</span></span>
 <span data-ttu-id="87660-143">-5</span><span class="sxs-lookup"><span data-stu-id="87660-143">-5</span></span> | <span data-ttu-id="87660-144">2</span><span class="sxs-lookup"><span data-stu-id="87660-144">2</span></span> | <span data-ttu-id="87660-145">-2</span><span class="sxs-lookup"><span data-stu-id="87660-145">-2</span></span> | <span data-ttu-id="87660-146">-1</span><span class="sxs-lookup"><span data-stu-id="87660-146">-1</span></span>
 <span data-ttu-id="87660-147">-5</span><span class="sxs-lookup"><span data-stu-id="87660-147">-5</span></span> | <span data-ttu-id="87660-148">-2</span><span class="sxs-lookup"><span data-stu-id="87660-148">-2</span></span> | <span data-ttu-id="87660-149">2</span><span class="sxs-lookup"><span data-stu-id="87660-149">2</span></span> | <span data-ttu-id="87660-150">-1</span><span class="sxs-lookup"><span data-stu-id="87660-150">-1</span></span>

<span data-ttu-id="87660-151">大整数除法和取模运算的工作方式相同。</span><span class="sxs-lookup"><span data-stu-id="87660-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="87660-152">如果给定了数值表达式，则可以使用一元运算符建立新的表达式 `-` 。</span><span class="sxs-lookup"><span data-stu-id="87660-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="87660-153">新表达式与构成表达式的类型相同。</span><span class="sxs-lookup"><span data-stu-id="87660-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="87660-154">给定任何整数或大整数表达式，都可以使用 `~~~` （按位求补）一元运算符形成同一类型的新表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="87660-155">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="87660-155">Boolean Expressions</span></span>

<span data-ttu-id="87660-156">这两个 `Bool` 文本值为 `true` 和 `false` 。</span><span class="sxs-lookup"><span data-stu-id="87660-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="87660-157">给定任意两个具有相同基元类型的表达式， `==` 和 `!=` 二元运算符可用于构造 `Bool` 表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="87660-158">如果两个表达式相等，则表达式为 true; 否则为 false。</span><span class="sxs-lookup"><span data-stu-id="87660-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="87660-159">不能比较用户定义类型的值，只能比较它们的解包值。</span><span class="sxs-lookup"><span data-stu-id="87660-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="87660-160">例如，使用 "解包" 运算符 `!` （在[Q # 中的类型](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)详细说明），</span><span class="sxs-lookup"><span data-stu-id="87660-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="87660-161">值的相等比较 `Qubit` 是恒等的; 即，两个表达式是否标识同一 qubit。</span><span class="sxs-lookup"><span data-stu-id="87660-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="87660-162">这两个 qubits 的状态不会进行比较、访问、度量或修改。</span><span class="sxs-lookup"><span data-stu-id="87660-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="87660-163">`Double`由于舍入效果，值的相等比较可能会产生误导。</span><span class="sxs-lookup"><span data-stu-id="87660-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="87660-164">例如 `49.0 * (1.0/49.0) != 1.0`。</span><span class="sxs-lookup"><span data-stu-id="87660-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="87660-165">给定任意两个数值表达式，二元运算符 `>` 、 `<` 、 `>=` 和可 `<=` 用于构造新的布尔表达式，如果第一个表达式分别大于、小于、大于或等于，或者小于或等于第二个表达式，则该值为 true。</span><span class="sxs-lookup"><span data-stu-id="87660-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="87660-166">给定任意两个布尔表达式，使用 `and` 二元运算符来构造新的布尔表达式，如果两个表达式都为 true，则该值为 true。</span><span class="sxs-lookup"><span data-stu-id="87660-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="87660-167">同样， `or` 如果两个表达式都为 true，则使用运算符会创建一个 true 表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="87660-168">给定任何布尔表达式， `not` 一元运算符可用于构造新的布尔表达式，如果构成表达式为 false，则为 true。</span><span class="sxs-lookup"><span data-stu-id="87660-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="87660-169">字符串表达式</span><span class="sxs-lookup"><span data-stu-id="87660-169">String expressions</span></span>

<span data-ttu-id="87660-170">Q # 允许在语句中使用字符串 `fail` （在[控制流](xref:microsoft.quantum.guide.controlflow#fail-statement)中说明）和标准函数中的字符串 [`Message`](xref:microsoft.quantum.intrinsic.message) 。</span><span class="sxs-lookup"><span data-stu-id="87660-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span> <span data-ttu-id="87660-171">后者的特定行为取决于所使用的模拟器，但当在 Q # 程序中调用时，通常会将消息写入主机控制台。</span><span class="sxs-lookup"><span data-stu-id="87660-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="87660-172">Q # 中的字符串是文本或内插字符串。</span><span class="sxs-lookup"><span data-stu-id="87660-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="87660-173">字符串文本类似于大多数语言中的简单字符串文本：用双引号引起来的 Unicode 字符序列 `" "` 。</span><span class="sxs-lookup"><span data-stu-id="87660-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="87660-174">在字符串内，使用反斜杠字符 `\` 来转义双引号字符（ `\"` ），或插入新行（ `\n` ）、回车符（ `\r` ）或制表符（ `\t` ）。</span><span class="sxs-lookup"><span data-stu-id="87660-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="87660-175">例如：</span><span class="sxs-lookup"><span data-stu-id="87660-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="87660-176">内插字符串</span><span class="sxs-lookup"><span data-stu-id="87660-176">Interpolated strings</span></span>

<span data-ttu-id="87660-177">字符串内插的 Q # 语法是 c # 语法的子集。</span><span class="sxs-lookup"><span data-stu-id="87660-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="87660-178">下面是与 Q # 相关的要点：</span><span class="sxs-lookup"><span data-stu-id="87660-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="87660-179">若要将字符串标识为内插字符串，可在该字符串前面加上 `$` 符号。</span><span class="sxs-lookup"><span data-stu-id="87660-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="87660-180">与之间不能存在空格， `$` `"` 后者用于启动字符串文本。</span><span class="sxs-lookup"><span data-stu-id="87660-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="87660-181">下面是一个基本示例，它使用 [`Message`](xref:microsoft.quantum.intrinsic.message) 函数将度量结果写入控制台，并将其写入其他 Q # 表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-181">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="87660-182">任何有效的 Q # 表达式都可以出现在内插字符串中。</span><span class="sxs-lookup"><span data-stu-id="87660-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="87660-183">内插字符串中的表达式遵循 Q # 语法，而不是 c # 语法。</span><span class="sxs-lookup"><span data-stu-id="87660-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="87660-184">最明显的区别在于，Q # 不支持逐字（多行）内插字符串。</span><span class="sxs-lookup"><span data-stu-id="87660-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="87660-185">有关 c # 语法的更多详细信息，请参阅内[*插字符串*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。</span><span class="sxs-lookup"><span data-stu-id="87660-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="87660-186">范围表达式</span><span class="sxs-lookup"><span data-stu-id="87660-186">Range Expressions</span></span>

<span data-ttu-id="87660-187">给定任意三个 `Int` 表达式 `start` ：和， `step` `stop` 表达式是一个 `start .. step .. stop` 范围表达式，其第一个元素是 `start` ，第二个元素是，第三个元素 `start+step` 为 `start+step+step` ，依此类推，直到您通过 `stop` 。</span><span class="sxs-lookup"><span data-stu-id="87660-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="87660-188">例如，如果为正和，则范围可能为空 `step` `stop < start` 。</span><span class="sxs-lookup"><span data-stu-id="87660-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="87660-189">此范围包含在两端。</span><span class="sxs-lookup"><span data-stu-id="87660-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="87660-190">也就是说，如果和的差 `start` 是的 `stop` 整数倍数，则该 `step` 范围的最后一个元素将为 `stop` 。</span><span class="sxs-lookup"><span data-stu-id="87660-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="87660-191">给定任意两个 `Int` 表达式 `start` 和 `stop` ，表达式 `start .. stop` 是等于的范围表达式 `start .. 1 .. stop` 。</span><span class="sxs-lookup"><span data-stu-id="87660-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="87660-192">请注意， `step` 即使小于，隐含也是 + 1 `stop` `start` ，范围为空。</span><span class="sxs-lookup"><span data-stu-id="87660-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="87660-193">一些示例范围如下：</span><span class="sxs-lookup"><span data-stu-id="87660-193">Some example ranges are:</span></span>

- <span data-ttu-id="87660-194">`1..3`的范围为1、2、3。</span><span class="sxs-lookup"><span data-stu-id="87660-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="87660-195">`2..2..5`范围为2、4。</span><span class="sxs-lookup"><span data-stu-id="87660-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="87660-196">`2..2..6`范围为2、4、6。</span><span class="sxs-lookup"><span data-stu-id="87660-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="87660-197">`6..-2..2`范围为6、4、2。</span><span class="sxs-lookup"><span data-stu-id="87660-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="87660-198">`2..1`为空范围。</span><span class="sxs-lookup"><span data-stu-id="87660-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="87660-199">`2..6..7`范围为2。</span><span class="sxs-lookup"><span data-stu-id="87660-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="87660-200">`2..2..1`为空范围。</span><span class="sxs-lookup"><span data-stu-id="87660-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="87660-201">`1..-1..2`为空范围。</span><span class="sxs-lookup"><span data-stu-id="87660-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="87660-202">Qubit 表达式</span><span class="sxs-lookup"><span data-stu-id="87660-202">Qubit Expressions</span></span>

<span data-ttu-id="87660-203">唯一的 `Qubit` 表达式是绑定到 `Qubit` 数组的值或数组元素的符号 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="87660-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="87660-204">没有 `Qubit` 文本。</span><span class="sxs-lookup"><span data-stu-id="87660-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="87660-205">Pauli 表达式</span><span class="sxs-lookup"><span data-stu-id="87660-205">Pauli Expressions</span></span>

<span data-ttu-id="87660-206">四个 `Pauli` 值（ `PauliI` 、 `PauliX` 、 `PauliY` 和 `PauliZ` ）都是有效的 `Pauli` 表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="87660-207">除了这样，唯一的 `Pauli` 表达式是绑定到 `Pauli` 数组的值或数组元素的符号 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="87660-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="87660-208">结果表达式</span><span class="sxs-lookup"><span data-stu-id="87660-208">Result Expressions</span></span>

<span data-ttu-id="87660-209">`Result` `One` 和 `Zero` 都是有效的 `Result` 表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="87660-210">除了这样，唯一的 `Result` 表达式是绑定到 `Result` 数组的值或数组元素的符号 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="87660-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="87660-211">特别要注意的是，与 `One` 整数不同 `1` ，它们之间没有直接转换。</span><span class="sxs-lookup"><span data-stu-id="87660-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="87660-212">对于和也是如此 `Zero` `0` 。</span><span class="sxs-lookup"><span data-stu-id="87660-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="87660-213">元组表达式</span><span class="sxs-lookup"><span data-stu-id="87660-213">Tuple Expressions</span></span>

<span data-ttu-id="87660-214">元组文本是一系列以逗号分隔的适当类型的元素表达式，括在括号中。</span><span class="sxs-lookup"><span data-stu-id="87660-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="87660-215">例如， `(1, One)` 是一个 `(Int, Result)` 表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="87660-216">除了文本以外，唯一的元组表达式是绑定到元组值、元组数组的数组元素和返回元组的可调用调用的符号。</span><span class="sxs-lookup"><span data-stu-id="87660-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="87660-217">用户定义的类型表达式</span><span class="sxs-lookup"><span data-stu-id="87660-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="87660-218">用户定义类型的文本包含类型名称，后跟类型的基元组类型的元组文本。</span><span class="sxs-lookup"><span data-stu-id="87660-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="87660-219">例如，如果 `IntPair` 是基于的用户定义类型 `(Int, Int)` ，则 `IntPair(2, 3)` 是该类型的有效文本。</span><span class="sxs-lookup"><span data-stu-id="87660-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="87660-220">除了文本以外，用户定义类型的唯一表达式是绑定到该类型的值、该类型的数组元素和返回该类型的可调用调用的符号。</span><span class="sxs-lookup"><span data-stu-id="87660-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="87660-221">解包表达式</span><span class="sxs-lookup"><span data-stu-id="87660-221">Unwrap Expressions</span></span>

<span data-ttu-id="87660-222">在 Q # 中，解包运算符是一个尾随引号 `!` 。</span><span class="sxs-lookup"><span data-stu-id="87660-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="87660-223">例如，如果 `IntPair` 是具有基础类型的用户定义类型， `(Int, Int)` 并且 `s` 是具有值的变量，则 `IntPair(2, 3)` `s!` 为 `(2, 3)` 。</span><span class="sxs-lookup"><span data-stu-id="87660-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="87660-224">对于根据其他用户定义类型定义的用户定义类型，可以重复解包运算符。</span><span class="sxs-lookup"><span data-stu-id="87660-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="87660-225">例如， `s!!` 指示的双重解包值 `s` 。</span><span class="sxs-lookup"><span data-stu-id="87660-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="87660-226">因此，如果 `WrappedPair` 是具有基础类型的用户定义类型 `IntPair` ，并且 `t` 是具有值的变量 `WrappedPair(IntPair(1,2))` ，则 `t!!` 为 `(1,2)` 。</span><span class="sxs-lookup"><span data-stu-id="87660-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="87660-227">运算符的优先级高于除 `!` `[]` 数组索引和切片以外的其他所有运算符。</span><span class="sxs-lookup"><span data-stu-id="87660-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="87660-228">`!`并 `[]` 绑定按位置; 即， `a[i]![3]` 读取为 `((a[i])!)[3]` ：获取 `i` 的第一个元素，将 `a` 其解包，然后获取解包值（必须是数组）的第3个元素。</span><span class="sxs-lookup"><span data-stu-id="87660-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="87660-229">运算符的优先级 `!` 有一个可能不明显的影响。</span><span class="sxs-lookup"><span data-stu-id="87660-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="87660-230">如果函数或操作返回一个值，则该函数或操作调用必须括在括号中，以便参数元组绑定到该调用，而不是绑定到解包。</span><span class="sxs-lookup"><span data-stu-id="87660-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="87660-231">例如：</span><span class="sxs-lookup"><span data-stu-id="87660-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="87660-232">数组表达式</span><span class="sxs-lookup"><span data-stu-id="87660-232">Array Expressions</span></span>

<span data-ttu-id="87660-233">数组文字是由逗号分隔的一个或多个元素表达式的序列，用方括号括起来 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="87660-234">所有元素都必须兼容同一类型。</span><span class="sxs-lookup"><span data-stu-id="87660-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="87660-235">给定两个类型相同的数组，使用二元 `+` 运算符来构成两个数组串联的新数组。</span><span class="sxs-lookup"><span data-stu-id="87660-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="87660-236">例如，`[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`。</span><span class="sxs-lookup"><span data-stu-id="87660-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="87660-237">数组创建</span><span class="sxs-lookup"><span data-stu-id="87660-237">Array Creation</span></span>

<span data-ttu-id="87660-238">给定一个类型和 `Int` 表达式，使用 `new` 运算符分配一个给定大小的新数组。</span><span class="sxs-lookup"><span data-stu-id="87660-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="87660-239">例如， `new Int[i + 1]` 使用元素分配新 `Int` 数组 `i + 1` 。</span><span class="sxs-lookup"><span data-stu-id="87660-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="87660-240">不允许使用空数组文本（如 `[]` ）。</span><span class="sxs-lookup"><span data-stu-id="87660-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="87660-241">相反，您可以使用创建长度为零的数组 `new T[0]` ，其中 `T` 是适合类型的占位符。</span><span class="sxs-lookup"><span data-stu-id="87660-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="87660-242">新数组的元素初始化为依赖于类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="87660-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="87660-243">在大多数情况下，这是零的一些变体。</span><span class="sxs-lookup"><span data-stu-id="87660-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="87660-244">对于引用实体的 qubits 和 callables，没有合理的默认值。</span><span class="sxs-lookup"><span data-stu-id="87660-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="87660-245">因此，对于这些类型，默认值是无效的引用，不能在不引发运行时错误的情况下使用，这类似于 c # 或 Java 等语言的空引用。</span><span class="sxs-lookup"><span data-stu-id="87660-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="87660-246">必须使用非默认值初始化包含 qubits 或 callables 的数组，才能安全地使用其元素。</span><span class="sxs-lookup"><span data-stu-id="87660-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="87660-247">有关适当的初始化例程，请参见 <xref:microsoft.quantum.arrays> 。</span><span class="sxs-lookup"><span data-stu-id="87660-247">For suitable initialization routines, see <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="87660-248">每种类型的默认值为：</span><span class="sxs-lookup"><span data-stu-id="87660-248">The default values for each type are:</span></span>

<span data-ttu-id="87660-249">类型</span><span class="sxs-lookup"><span data-stu-id="87660-249">Type</span></span> | <span data-ttu-id="87660-250">默认</span><span class="sxs-lookup"><span data-stu-id="87660-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="87660-251">_无效的 qubit_</span><span class="sxs-lookup"><span data-stu-id="87660-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="87660-252">空范围，`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="87660-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="87660-253">_调用无效_</span><span class="sxs-lookup"><span data-stu-id="87660-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="87660-254">元组类型初始化逐个元素元素。</span><span class="sxs-lookup"><span data-stu-id="87660-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="87660-255">数组元素</span><span class="sxs-lookup"><span data-stu-id="87660-255">Array Elements</span></span>

<span data-ttu-id="87660-256">给定数组表达式和 `Int` 表达式，使用数组元素运算符构成一个新表达式 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="87660-257">新表达式的类型与数组的元素类型相同。</span><span class="sxs-lookup"><span data-stu-id="87660-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="87660-258">例如，如果 `a` 绑定到类型的数组 `Double` ，则 `a[4]` 是一个 `Double` 表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="87660-259">如果数组表达式不是简单的标识符，则必须将其括在括号中，以便选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="87660-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="87660-260">例如，如果 `a` 和 `b` 都是类型的数组 `Int` ，则连接中的元素表示为：</span><span class="sxs-lookup"><span data-stu-id="87660-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="87660-261">Q # 中的所有数组都是从零开始的。</span><span class="sxs-lookup"><span data-stu-id="87660-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="87660-262">也就是说，数组的第一个元素 `a` 始终为 `a[0]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="87660-263">数组切片</span><span class="sxs-lookup"><span data-stu-id="87660-263">Array Slices</span></span>

<span data-ttu-id="87660-264">给定数组表达式和 `Range` 表达式，使用数组切片运算符构成一个新表达式 `[ ]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="87660-265">新表达式与数组的类型相同，并包含按定义的顺序由的元素索引的数组项 `Range` `Range` 。</span><span class="sxs-lookup"><span data-stu-id="87660-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="87660-266">例如，如果 `a` 绑定到类型的数组 `Double` ，则 `a[3..-1..0]` 是一个 `Double[]` 表达式，该表达式包含的前四个元素， `a` 但其显示顺序与中的顺序相反 `a` 。</span><span class="sxs-lookup"><span data-stu-id="87660-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="87660-267">如果 `Range` 为空，则生成的数组切片的长度为零。</span><span class="sxs-lookup"><span data-stu-id="87660-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="87660-268">就像引用数组元素一样，如果数组表达式不是简单的标识符，则必须将其括在括号中，以便对其进行切片。</span><span class="sxs-lookup"><span data-stu-id="87660-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="87660-269">例如，如果 `a` 和 `b` 都是类型的数组 `Int` ，则串联的切片表示为：</span><span class="sxs-lookup"><span data-stu-id="87660-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="87660-270">推断的开始/结束值</span><span class="sxs-lookup"><span data-stu-id="87660-270">Inferred start/end values</span></span>

<span data-ttu-id="87660-271">从[0.8 版本](xref:microsoft.quantum.relnotes)开始，我们支持范围切片的上下文表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="87660-272">特别是，在范围切片表达式的上下文中，您可以省略范围起始值和结束值。</span><span class="sxs-lookup"><span data-stu-id="87660-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="87660-273">在这种情况下，编译器会应用以下规则来推断范围的预期分隔符：</span><span class="sxs-lookup"><span data-stu-id="87660-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="87660-274">如果省略范围*起始*值，则推断出的起始值</span><span class="sxs-lookup"><span data-stu-id="87660-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="87660-275">如果未指定步骤或指定步骤为正值，则为零。</span><span class="sxs-lookup"><span data-stu-id="87660-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="87660-276">如果指定的步骤为负，则为切片的数组的长度减一。</span><span class="sxs-lookup"><span data-stu-id="87660-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="87660-277">如果省略范围*结束*值，则推断出的结束值</span><span class="sxs-lookup"><span data-stu-id="87660-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="87660-278">如果未指定步骤或指定步骤为正值，则为切片的数组的长度减一。</span><span class="sxs-lookup"><span data-stu-id="87660-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="87660-279">如果指定的步骤为负数，则为零。</span><span class="sxs-lookup"><span data-stu-id="87660-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="87660-280">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="87660-280">Some examples are:</span></span>

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="87660-281">复制和更新表达式</span><span class="sxs-lookup"><span data-stu-id="87660-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="87660-282">由于所有 Q # 类型都是值类型（qubits 采用一个特殊的角色），因此，在将值绑定到符号或重新绑定符号时，将创建一个 "复制"。</span><span class="sxs-lookup"><span data-stu-id="87660-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="87660-283">也就是说，Q # 的行为与使用赋值运算符创建副本的行为相同。</span><span class="sxs-lookup"><span data-stu-id="87660-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="87660-284">当然，在实际情况下，只会根据需要重新创建相关的部分。</span><span class="sxs-lookup"><span data-stu-id="87660-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="87660-285">这会影响复制数组的方式，因为不能更新数组项。</span><span class="sxs-lookup"><span data-stu-id="87660-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="87660-286">若要修改现有阵列，需要利用*复制和更新*机制。</span><span class="sxs-lookup"><span data-stu-id="87660-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="87660-287">可以通过使用运算符和的*复制和更新*表达式从现有数组创建新数组 `w/` `<-` 。</span><span class="sxs-lookup"><span data-stu-id="87660-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="87660-288">复制和更新表达式是格式为的表达式 `expression1 w/ expression2 <- expression3` ，其中</span><span class="sxs-lookup"><span data-stu-id="87660-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="87660-289">`expression1``T[]`对于某些类型，必须是类型 `T` 。</span><span class="sxs-lookup"><span data-stu-id="87660-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="87660-290">`expression2`定义要修改的数组中指定的索引 `expression1` 。</span><span class="sxs-lookup"><span data-stu-id="87660-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="87660-291">`expression2`必须是类型 `Int` 或类型 `Range` 。</span><span class="sxs-lookup"><span data-stu-id="87660-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="87660-292">`expression3``expression1`基于中指定的索引，用于更新中的元素的值 `expression2` 。</span><span class="sxs-lookup"><span data-stu-id="87660-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="87660-293">如果 `expression2` 为类型 `Int` ，则 `expression3` 必须为类型 `T` 。</span><span class="sxs-lookup"><span data-stu-id="87660-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="87660-294">如果 `expression2` 为类型 `Range` ，则 `expression3` 必须为类型 `T[]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="87660-295">例如，复制和更新表达式 `arr w/ idx <- value` 构造一个新数组，其中所有元素都设置为中的相应元素 `arr` ，但指定的元素除外 `idx` ，该元素设置为中的值 `value` 。</span><span class="sxs-lookup"><span data-stu-id="87660-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="87660-296">给定 `arr` 包含数组 `[0,1,2,3]` ，然后</span><span class="sxs-lookup"><span data-stu-id="87660-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="87660-297">`arr w/ 0 <- 10`是数组 `[10,1,2,3]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="87660-298">`arr w/ 2 <- 10`是数组 `[0,1,10,3]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="87660-299">`arr w/ 0..2..3 <- [10,12]`是数组 `[10,1,12,3]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="87660-300">已命名项的复制和更新表达式</span><span class="sxs-lookup"><span data-stu-id="87660-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="87660-301">对于用户定义类型中的命名项，存在类似的表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="87660-302">例如，请考虑类型</span><span class="sxs-lookup"><span data-stu-id="87660-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="87660-303">如果 `c` 包含类型的值 `Complex(1., -1.)` ，则 `c w/ Re <- 0.` 是类型的表达式， `Complex` 其计算结果为 `Complex(0., -1.)` 。</span><span class="sxs-lookup"><span data-stu-id="87660-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="87660-304">交错数组</span><span class="sxs-lookup"><span data-stu-id="87660-304">Jagged Arrays</span></span>

<span data-ttu-id="87660-305">交错数组（有时称为 "数组的数组"）是一个其元素为数组的数组。</span><span class="sxs-lookup"><span data-stu-id="87660-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="87660-306">交错数组的元素的大小可以不同。</span><span class="sxs-lookup"><span data-stu-id="87660-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="87660-307">下面的示例演示如何声明和初始化表示乘法表的交错数组。</span><span class="sxs-lookup"><span data-stu-id="87660-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="87660-308">Callables 的数组</span><span class="sxs-lookup"><span data-stu-id="87660-308">Arrays of callables</span></span> 

<span data-ttu-id="87660-309">还可以创建 callables 的数组。</span><span class="sxs-lookup"><span data-stu-id="87660-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="87660-310">如果公共元素类型是运算或函数类型，则所有元素必须具有相同的输入和输出类型。</span><span class="sxs-lookup"><span data-stu-id="87660-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="87660-311">数组的元素类型支持所有元素支持的任何[函子](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="87660-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="87660-312">例如，如果 `Op1` 、 `Op2` 和 `Op3` 均为 `Qubit[] => Unit` 操作，但支持、 `Op1` 支持 `Adjoint` `Op2` `Controlled` 和 `Op3` 均支持：</span><span class="sxs-lookup"><span data-stu-id="87660-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="87660-313">`[Op1, Op2]`是一组 `(Qubit[] => Unit)` 操作。</span><span class="sxs-lookup"><span data-stu-id="87660-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="87660-314">`[Op1, Op3]`是一组 `(Qubit[] => Unit is Adj)` 操作。</span><span class="sxs-lookup"><span data-stu-id="87660-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="87660-315">`[Op2, Op3]`是一组 `(Qubit[] => Unit is Ctl)` 操作。</span><span class="sxs-lookup"><span data-stu-id="87660-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="87660-316">但是，尽管操作 `(Qubit[] => Unit is Adj)` 和 `(Qubit[] => Unit is Ctl)` 具有的通用基类型，但 `(Qubit[] => Unit)` 这些操作的*数组*不共享公共基类型。</span><span class="sxs-lookup"><span data-stu-id="87660-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="87660-317">例如， `[[Op1], [Op2]]` 当前将引发错误，因为它会尝试创建两个不兼容的数组类型和的 `(Qubit[] => Unit is Adj)[]` 数组 `(Qubit[] => Unit is Ctl)[]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="87660-318">有关 callables 的详细信息，请参阅此页上的可[调用表达式](#callable-expressions)或[Q # 中的操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="87660-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="87660-319">条件表达式</span><span class="sxs-lookup"><span data-stu-id="87660-319">Conditional Expressions</span></span>

<span data-ttu-id="87660-320">假设有两个具有相同类型和布尔表达式的表达式，则使用问号、和竖线构成一个条件表达式 `?` `|` 。</span><span class="sxs-lookup"><span data-stu-id="87660-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="87660-321">`a==b ? c | d` `c` 如果为 true，则条件表达式的值为; 如果为 false，则为 `a==b` `d` 。</span><span class="sxs-lookup"><span data-stu-id="87660-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="87660-322">带 callables 的条件表达式</span><span class="sxs-lookup"><span data-stu-id="87660-322">Conditional expressions with callables</span></span>

<span data-ttu-id="87660-323">条件表达式的计算结果可能为具有相同输入和输出但支持不同函子的操作。</span><span class="sxs-lookup"><span data-stu-id="87660-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="87660-324">在这种情况下，条件表达式的类型是一个操作，其输入和输出支持两个表达式支持的任何函子。</span><span class="sxs-lookup"><span data-stu-id="87660-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="87660-325">例如，如果、和都是，则支持、支持 `Op1` `Op2` `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` 和 `Op3` 均支持：</span><span class="sxs-lookup"><span data-stu-id="87660-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="87660-326">`flag ? Op1 | Op2`为 `(Qubit[] => Unit)` 操作。</span><span class="sxs-lookup"><span data-stu-id="87660-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="87660-327">`flag ? Op1 | Op3`为 `(Qubit[] => Unit is Adj)` 操作。</span><span class="sxs-lookup"><span data-stu-id="87660-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="87660-328">`flag ? Op2 | Op3`为 `(Qubit[] => Unit is Ctl)` 操作。</span><span class="sxs-lookup"><span data-stu-id="87660-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="87660-329">如果两个可能的结果表达式中有一个包含函数或操作调用，则只会在该结果是调用值的情况下调用。</span><span class="sxs-lookup"><span data-stu-id="87660-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="87660-330">例如，在这种情况下 `a==b ? C(qs) | D(qs)` ，如果 `a==b` 为 true，则 `C` 调用操作，如果为 false，则只 `D` 调用操作。</span><span class="sxs-lookup"><span data-stu-id="87660-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="87660-331">此方法类似于其他语言的*短路*。</span><span class="sxs-lookup"><span data-stu-id="87660-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="87660-332">可调用表达式</span><span class="sxs-lookup"><span data-stu-id="87660-332">Callable Expressions</span></span>

<span data-ttu-id="87660-333">可调用的文本是编译范围中定义的操作或函数的名称。</span><span class="sxs-lookup"><span data-stu-id="87660-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="87660-334">例如， `X` 是引用标准库操作的操作文本 `X` ， `Message` 是引用标准库函数的函数文本 `Message` 。</span><span class="sxs-lookup"><span data-stu-id="87660-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="87660-335">如果操作支持 `Adjoint` 函子，则 `Adjoint op` 是操作表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="87660-336">同样，如果操作支持 `Controlled` 函子，则 `Controlled op` 是操作表达式。</span><span class="sxs-lookup"><span data-stu-id="87660-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="87660-337">有关这些表达式的类型的详细信息，请参阅[调用操作专用](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)化。</span><span class="sxs-lookup"><span data-stu-id="87660-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="87660-338">`Adjoint` `Controlled` 除解包运算符和数组索引外，函子（和）与其他所有运算符更紧密地绑定 `!` `[ ]` 。</span><span class="sxs-lookup"><span data-stu-id="87660-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="87660-339">因此，以下所有操作都是有效的，前提是这些操作支持使用的函子：</span><span class="sxs-lookup"><span data-stu-id="87660-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="87660-340">类型参数化的可调用表达式</span><span class="sxs-lookup"><span data-stu-id="87660-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="87660-341">例如，可以将可调用文本作为值，将其分配给变量或将其传递给其他可调用的。</span><span class="sxs-lookup"><span data-stu-id="87660-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="87660-342">在这种情况下，如果可调用的具有[类型参数](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)，则必须提供作为可调用值一部分的参数。</span><span class="sxs-lookup"><span data-stu-id="87660-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="87660-343">可调用的值不能具有任何未指定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="87660-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="87660-344">例如，如果 `Fun` 是具有签名的函数 `'T1->Unit` ：</span><span class="sxs-lookup"><span data-stu-id="87660-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="87660-345">可调用调用表达式</span><span class="sxs-lookup"><span data-stu-id="87660-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="87660-346">给定可调用的表达式（操作或函数）和可调用签名的输入类型的元组表达式时，可以通过将元组表达式追加到可调用表达式来形成*调用表达式*。</span><span class="sxs-lookup"><span data-stu-id="87660-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="87660-347">调用表达式的类型是可调用的签名的输出类型。</span><span class="sxs-lookup"><span data-stu-id="87660-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="87660-348">例如，如果 `Op` 是具有签名的操作 `((Int, Qubit) => Double)` ， `Op(3, qubit1)` 则为类型的表达式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="87660-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="87660-349">同样，如果 `Sin` 是具有签名的函数 `(Double -> Double)` ， `Sin(0.1)` 则是类型的表达式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="87660-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="87660-350">最后，如果 `Builder` 是具有签名的函数 `(Int -> (Int -> Int))` ，则 `Builder(3)` 是从到的函数 `Int` `Int` 。</span><span class="sxs-lookup"><span data-stu-id="87660-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="87660-351">若要调用可调用值表达式的结果，需要在可调用的表达式前后使用一对括号。</span><span class="sxs-lookup"><span data-stu-id="87660-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="87660-352">因此，若要调用 `Builder` 上一段落中调用的结果，正确的语法为：</span><span class="sxs-lookup"><span data-stu-id="87660-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="87660-353">调用[类型参数化](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)的可调用时，可以在可调用表达式后的尖括号中指定实际的类型参数 `< >` 。</span><span class="sxs-lookup"><span data-stu-id="87660-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="87660-354">此操作通常是不必要的，因为 Q # 编译器会推断实际类型。</span><span class="sxs-lookup"><span data-stu-id="87660-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="87660-355">但是，如果*未指定*类型参数化的参数，则此[部分应用程序](xref:microsoft.quantum.guide.operationsfunctions#partial-application)需要它。</span><span class="sxs-lookup"><span data-stu-id="87660-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="87660-356">在将具有不同函子支持的操作传递给可调用时，此方法也非常有用。</span><span class="sxs-lookup"><span data-stu-id="87660-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="87660-357">例如，如果具有签名，并具有签名， `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` 并 `Op3` 具有签名，则 `(Qubit[] => Unit)` `Func` 使用 `Op1` 作为第一个参数进行调用， `Op2` 并 `Op3` 将作为第二个参数进行调用，第三个参数为：</span><span class="sxs-lookup"><span data-stu-id="87660-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="87660-358">类型规范是必需的 `Op3` ，因为和 `Op1` 具有不同的类型，因此，如果没有规范，编译器会将此视为不明确的。</span><span class="sxs-lookup"><span data-stu-id="87660-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="87660-359">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="87660-359">Operator Precedence</span></span>

* <span data-ttu-id="87660-360">除了之外，所有二元运算符都是右结合运算符 `^` 。</span><span class="sxs-lookup"><span data-stu-id="87660-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="87660-361">`[ ]`用于数组切片和索引的方括号，在任何运算符之前绑定。</span><span class="sxs-lookup"><span data-stu-id="87660-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="87660-362">`Adjoint` `Controlled` 数组索引后，但在所有其他运算符之前，函子和绑定。</span><span class="sxs-lookup"><span data-stu-id="87660-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="87660-363">用于运算和函数调用的括号也绑定在任何运算符之前，但在数组索引和函子之后。</span><span class="sxs-lookup"><span data-stu-id="87660-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="87660-364">Q # 运算符按优先级顺序排列，从高到低：</span><span class="sxs-lookup"><span data-stu-id="87660-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="87660-365">运算符</span><span class="sxs-lookup"><span data-stu-id="87660-365">Operator</span></span> | <span data-ttu-id="87660-366">元</span><span class="sxs-lookup"><span data-stu-id="87660-366">Arity</span></span> | <span data-ttu-id="87660-367">说明</span><span class="sxs-lookup"><span data-stu-id="87660-367">Description</span></span> | <span data-ttu-id="87660-368">操作数类型</span><span class="sxs-lookup"><span data-stu-id="87660-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="87660-369">加`!`</span><span class="sxs-lookup"><span data-stu-id="87660-369">trailing `!`</span></span> | <span data-ttu-id="87660-370">一元</span><span class="sxs-lookup"><span data-stu-id="87660-370">Unary</span></span> | <span data-ttu-id="87660-371">解包</span><span class="sxs-lookup"><span data-stu-id="87660-371">Unwrap</span></span> | <span data-ttu-id="87660-372">任何用户定义类型</span><span class="sxs-lookup"><span data-stu-id="87660-372">Any user-defined type</span></span>
 <span data-ttu-id="87660-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="87660-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="87660-374">一元</span><span class="sxs-lookup"><span data-stu-id="87660-374">Unary</span></span> | <span data-ttu-id="87660-375">数值负，按位求补，逻辑求反</span><span class="sxs-lookup"><span data-stu-id="87660-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="87660-376">`Int`对于，为 `BigInt` 或 `Double` `-` `Int` `BigInt` `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="87660-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="87660-377">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-377">Binary</span></span> | <span data-ttu-id="87660-378">整数幂</span><span class="sxs-lookup"><span data-stu-id="87660-378">Integer power</span></span> | <span data-ttu-id="87660-379">`Int`对于 `BigInt` 指数，为或 `Int`</span><span class="sxs-lookup"><span data-stu-id="87660-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="87660-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="87660-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="87660-381">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-381">Binary</span></span> | <span data-ttu-id="87660-382">除法、乘法、integer 模数</span><span class="sxs-lookup"><span data-stu-id="87660-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="87660-383">`Int`对于 `BigInt` 、或 `Double` 为 `/` `*` `Int` `BigInt``%`</span><span class="sxs-lookup"><span data-stu-id="87660-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="87660-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="87660-384">`+`, `-`</span></span> | <span data-ttu-id="87660-385">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-385">Binary</span></span> | <span data-ttu-id="87660-386">加法或 string 和 array 串联，减法</span><span class="sxs-lookup"><span data-stu-id="87660-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="87660-387">`Int`、 `BigInt` 或 `Double` ，另外 `String` 或任何类型的数组类型`+`</span><span class="sxs-lookup"><span data-stu-id="87660-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="87660-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="87660-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="87660-389">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-389">Binary</span></span> | <span data-ttu-id="87660-390">左移、右移</span><span class="sxs-lookup"><span data-stu-id="87660-390">Left shift, right shift</span></span> | <span data-ttu-id="87660-391">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="87660-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="87660-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="87660-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="87660-393">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-393">Binary</span></span> | <span data-ttu-id="87660-394">小于、小于或等于、大于、大于等于或等于比较的比较</span><span class="sxs-lookup"><span data-stu-id="87660-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="87660-395">`Int`， `BigInt` 或`Double`</span><span class="sxs-lookup"><span data-stu-id="87660-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="87660-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="87660-396">`==`, `!=`</span></span> | <span data-ttu-id="87660-397">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-397">Binary</span></span> | <span data-ttu-id="87660-398">相等，不等于比较</span><span class="sxs-lookup"><span data-stu-id="87660-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="87660-399">任何基元类型</span><span class="sxs-lookup"><span data-stu-id="87660-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="87660-400">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-400">Binary</span></span> | <span data-ttu-id="87660-401">位与</span><span class="sxs-lookup"><span data-stu-id="87660-401">Bitwise AND</span></span> | <span data-ttu-id="87660-402">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="87660-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="87660-403">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-403">Binary</span></span> | <span data-ttu-id="87660-404">按位“异或”</span><span class="sxs-lookup"><span data-stu-id="87660-404">Bitwise XOR</span></span> | <span data-ttu-id="87660-405">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="87660-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="87660-406">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-406">Binary</span></span> | <span data-ttu-id="87660-407">按位“或”</span><span class="sxs-lookup"><span data-stu-id="87660-407">Bitwise OR</span></span> | <span data-ttu-id="87660-408">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="87660-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="87660-409">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-409">Binary</span></span> | <span data-ttu-id="87660-410">逻辑与</span><span class="sxs-lookup"><span data-stu-id="87660-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="87660-411">二进制</span><span class="sxs-lookup"><span data-stu-id="87660-411">Binary</span></span> | <span data-ttu-id="87660-412">逻辑或</span><span class="sxs-lookup"><span data-stu-id="87660-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="87660-413">二进制/三元</span><span class="sxs-lookup"><span data-stu-id="87660-413">Binary/Ternary</span></span> | <span data-ttu-id="87660-414">范围运算符</span><span class="sxs-lookup"><span data-stu-id="87660-414">Range operator</span></span> | `Int`
 <span data-ttu-id="87660-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="87660-415">`?` `|`</span></span> | <span data-ttu-id="87660-416">三元</span><span class="sxs-lookup"><span data-stu-id="87660-416">Ternary</span></span> | <span data-ttu-id="87660-417">条件逻辑</span><span class="sxs-lookup"><span data-stu-id="87660-417">Conditional</span></span> | <span data-ttu-id="87660-418">`Bool`对于左侧</span><span class="sxs-lookup"><span data-stu-id="87660-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="87660-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="87660-419">`w/` `<-`</span></span> | <span data-ttu-id="87660-420">三元</span><span class="sxs-lookup"><span data-stu-id="87660-420">Ternary</span></span> | <span data-ttu-id="87660-421">复制和更新</span><span class="sxs-lookup"><span data-stu-id="87660-421">Copy-and-update</span></span> | <span data-ttu-id="87660-422">请参阅[复制和更新表达式](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="87660-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="87660-423">后续步骤</span><span class="sxs-lookup"><span data-stu-id="87660-423">Next steps</span></span>

<span data-ttu-id="87660-424">现在，你可以使用 Q # 中的表达式，请转到[q # 中的操作和函数](xref:microsoft.quantum.guide.operationsfunctions)以了解如何定义和调用操作和函数。</span><span class="sxs-lookup"><span data-stu-id="87660-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
