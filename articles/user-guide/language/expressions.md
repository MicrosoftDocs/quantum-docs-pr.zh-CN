---
title: Q 中的类型表达式#
description: '了解如何指定、引用和组合常量、变量、运算符、操作和函数作为 Q # 中的表达式。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 93432cef9711b6780192cd59e92b09647a264b5c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431200"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="5ef41-103">Q 中的类型表达式#</span><span class="sxs-lookup"><span data-stu-id="5ef41-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="5ef41-104">数值表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-104">Numeric Expressions</span></span>

<span data-ttu-id="5ef41-105">数值表达式是、或类型的表达式 `Int` `BigInt` `Double` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="5ef41-106">也就是说，它们是整数或浮点数。</span><span class="sxs-lookup"><span data-stu-id="5ef41-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="5ef41-107">`Int`Q # 中的文本只编写为一系列数字。</span><span class="sxs-lookup"><span data-stu-id="5ef41-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="5ef41-108">十六进制和二进制整数 `0x` 分别支持和 `0b` 前缀。</span><span class="sxs-lookup"><span data-stu-id="5ef41-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="5ef41-109">`BigInt`用结尾或后缀编写的 Q # 中的文本 `l` `L` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="5ef41-110">支持使用 "0x" 前缀的十六进制大整数。</span><span class="sxs-lookup"><span data-stu-id="5ef41-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="5ef41-111">因此，以下是文本的有效用法 `BigInt` ：</span><span class="sxs-lookup"><span data-stu-id="5ef41-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="5ef41-112">`Double`Q # 中的文本是使用十进制数字编写的浮点数。</span><span class="sxs-lookup"><span data-stu-id="5ef41-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="5ef41-113">它们可以使用小数点、 `.` 和/或用 "e" 或 "e" 指示的指数部分来编写（在这种情况下，只有可能的负号和十进制数字有效）。</span><span class="sxs-lookup"><span data-stu-id="5ef41-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="5ef41-114">下面是有效的 `Double` 文本： `0.0` 、 `1.2e5` 、 `1e-5` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="5ef41-115">给定任意元素类型的数组表达式， `Int` 可以使用 [`Length`](xref:microsoft.quantum.core.length) 内置函数，使用括在括号中的数组表达式和来构造表达式 `(` `)` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="5ef41-116">例如，如果 `a` 绑定到数组，则 `Length(a)` 是整数表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="5ef41-117">如果 `b` 是整数数组的数组，则 `Int[][]` `Length(b)` 为中的子数组的数目 `b` ， `Length(b[1])` 是中第二个子数组 `b` 中的整数的数目。</span><span class="sxs-lookup"><span data-stu-id="5ef41-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="5ef41-118">假设两个数值表达式具有相同的类型，则可以 `+` 使用二元运算符、、 `-` `*` 和 `/` 形成新的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="5ef41-119">新表达式的类型将与构成表达式的类型相同。</span><span class="sxs-lookup"><span data-stu-id="5ef41-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="5ef41-120">假设有两个整数表达式，二元运算符 `^` （power）可用于构成新的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="5ef41-121">同样， `^` 可以使用两个双表达式来形成新的双精度表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="5ef41-122">最后，可 `^` 与左侧的大整数一起使用，并在右侧使用一个整数来形成新的大整数表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="5ef41-123">在这种情况下，第二个参数必须适合32位;否则，将引发运行时错误。</span><span class="sxs-lookup"><span data-stu-id="5ef41-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="5ef41-124">假设有两个整数或大整数表达式，可以使用 `%` （取模）、 `&&&` （位与）、 `|||` （位或）或 `^^^` （位 XOR）运算符来形成新的整数或大整数表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="5ef41-125">给定左侧的整数或大整数表达式，并在右侧输入整数表达式，则 `<<<` 可以使用（算术左移位）或 `>>>` （算术右移位）运算符来创建与左侧表达式具有相同类型的新表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="5ef41-126">转换操作的第二个参数（移位量）必须大于或等于零;负移位量的行为是不确定的。</span><span class="sxs-lookup"><span data-stu-id="5ef41-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="5ef41-127">移位运算的移位量还必须适合32位;否则，将引发运行时错误。</span><span class="sxs-lookup"><span data-stu-id="5ef41-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="5ef41-128">如果要移位的数字是整数，则移位量将被解释 `mod 64` ; 也就是说，1的移位和65的移位都具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="5ef41-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="5ef41-129">对于整数和大整数值，移位均为算术运算。</span><span class="sxs-lookup"><span data-stu-id="5ef41-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="5ef41-130">向左或向右移位负值将导致负数。</span><span class="sxs-lookup"><span data-stu-id="5ef41-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="5ef41-131">也就是说，向左或向右移动一个步骤的方式与2的乘法或除法完全相同。</span><span class="sxs-lookup"><span data-stu-id="5ef41-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="5ef41-132">对于负数，整数除法和整数取模的行为与 c # 的行为相同。</span><span class="sxs-lookup"><span data-stu-id="5ef41-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="5ef41-133">也就是说， `a % b` 将始终具有相同的符号 `a` ，并 `b * (a / b) + a % b` 始终相等 `a` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="5ef41-134">例如：</span><span class="sxs-lookup"><span data-stu-id="5ef41-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="5ef41-135">5</span><span class="sxs-lookup"><span data-stu-id="5ef41-135">5</span></span> | <span data-ttu-id="5ef41-136">2</span><span class="sxs-lookup"><span data-stu-id="5ef41-136">2</span></span> | <span data-ttu-id="5ef41-137">2</span><span class="sxs-lookup"><span data-stu-id="5ef41-137">2</span></span> | <span data-ttu-id="5ef41-138">1</span><span class="sxs-lookup"><span data-stu-id="5ef41-138">1</span></span>
 <span data-ttu-id="5ef41-139">5</span><span class="sxs-lookup"><span data-stu-id="5ef41-139">5</span></span> | <span data-ttu-id="5ef41-140">-2</span><span class="sxs-lookup"><span data-stu-id="5ef41-140">-2</span></span> | <span data-ttu-id="5ef41-141">-2</span><span class="sxs-lookup"><span data-stu-id="5ef41-141">-2</span></span> | <span data-ttu-id="5ef41-142">1</span><span class="sxs-lookup"><span data-stu-id="5ef41-142">1</span></span>
 <span data-ttu-id="5ef41-143">-5</span><span class="sxs-lookup"><span data-stu-id="5ef41-143">-5</span></span> | <span data-ttu-id="5ef41-144">2</span><span class="sxs-lookup"><span data-stu-id="5ef41-144">2</span></span> | <span data-ttu-id="5ef41-145">-2</span><span class="sxs-lookup"><span data-stu-id="5ef41-145">-2</span></span> | <span data-ttu-id="5ef41-146">-1</span><span class="sxs-lookup"><span data-stu-id="5ef41-146">-1</span></span>
 <span data-ttu-id="5ef41-147">-5</span><span class="sxs-lookup"><span data-stu-id="5ef41-147">-5</span></span> | <span data-ttu-id="5ef41-148">-2</span><span class="sxs-lookup"><span data-stu-id="5ef41-148">-2</span></span> | <span data-ttu-id="5ef41-149">2</span><span class="sxs-lookup"><span data-stu-id="5ef41-149">2</span></span> | <span data-ttu-id="5ef41-150">-1</span><span class="sxs-lookup"><span data-stu-id="5ef41-150">-1</span></span>

<span data-ttu-id="5ef41-151">大整数除法和取模的工作方式相同。</span><span class="sxs-lookup"><span data-stu-id="5ef41-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="5ef41-152">如果给定了数值表达式，则可以使用一元运算符构造新的表达式 `-` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="5ef41-153">新表达式将与构成表达式的类型相同。</span><span class="sxs-lookup"><span data-stu-id="5ef41-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="5ef41-154">给定任意整数或大整数表达式时，可以使用 `~~~` （按位求补）一元运算符来构造相同类型的新表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="5ef41-155">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-155">Boolean Expressions</span></span>

<span data-ttu-id="5ef41-156">这两个 `Bool` 文本值为 `true` 和 `false` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="5ef41-157">给定任意两个具有相同基元类型的表达式， `==` 和 `!=` 二元运算符可用于构造 `Bool` 表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="5ef41-158">如果两个表达式相等，则表达式将为 true; 否则为 false。</span><span class="sxs-lookup"><span data-stu-id="5ef41-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="5ef41-159">不能比较用户定义类型的值，只能比较它们的解包值。</span><span class="sxs-lookup"><span data-stu-id="5ef41-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="5ef41-160">例如，使用 "解包" 运算符 `!` （在[Q # 中的类型](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)详细说明），</span><span class="sxs-lookup"><span data-stu-id="5ef41-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="5ef41-161">值的相等比较 `Qubit` 是恒等的; 即，两个表达式是否标识同一 qubit。</span><span class="sxs-lookup"><span data-stu-id="5ef41-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="5ef41-162">这两个 qubits 的状态不会进行比较、访问、度量或修改。</span><span class="sxs-lookup"><span data-stu-id="5ef41-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="5ef41-163">`Double`由于舍入效果，值的相等比较可能会产生误导。</span><span class="sxs-lookup"><span data-stu-id="5ef41-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="5ef41-164">例如， `49.0 * (1.0/49.0) != 1.0` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="5ef41-165">给定任意两个数值表达式，二元运算符 `>` 、 `<` 、 `>=` 和可 `<=` 用于构造新的布尔表达式，如果第一个表达式分别大于、小于、大于或等于，或者小于或等于第二个表达式，则该值为 true。</span><span class="sxs-lookup"><span data-stu-id="5ef41-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="5ef41-166">给定任意两个布尔表达式， `and` 和 `or` 二元运算符可用于构造新的布尔表达式，如果这两个表达式都为 true，则这两个表达式均为 true。</span><span class="sxs-lookup"><span data-stu-id="5ef41-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="5ef41-167">给定任何布尔表达式， `not` 一元运算符可用于构造新的布尔表达式，如果构成表达式为 false，则为 true。</span><span class="sxs-lookup"><span data-stu-id="5ef41-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="5ef41-168">字符串表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-168">String Expressions</span></span>

<span data-ttu-id="5ef41-169">Q # 允许在语句中使用字符串 `fail` （在[控制流](xref:microsoft.quantum.guide.controlflow#fail-statement)中说明）和标准函数中的字符串 [`Message`](xref:microsoft.quantum.intrinsic.message) 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="5ef41-170">后者的特定行为取决于所使用的模拟器，但当在 Q # 程序中调用时，通常会将消息写入主机控制台。</span><span class="sxs-lookup"><span data-stu-id="5ef41-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="5ef41-171">Q # 中的字符串是文本或内插字符串。</span><span class="sxs-lookup"><span data-stu-id="5ef41-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="5ef41-172">字符串文本类似于大多数语言中的简单字符串文本：括在双引号中的 Unicode 字符序列 `"` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="5ef41-173">在字符串中，反斜杠字符可 `\` 用于转义双引号字符，还可以将新行作为 `\n` 、回车符和制表符插入到中 `\r` `\t` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="5ef41-174">例如：</span><span class="sxs-lookup"><span data-stu-id="5ef41-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="5ef41-175">内插字符串</span><span class="sxs-lookup"><span data-stu-id="5ef41-175">Interpolated strings</span></span>

<span data-ttu-id="5ef41-176">String 内插的 Q # 语法是 c # 语法的子集，但我们在此处汇总了与 Q # 相关的要点。</span><span class="sxs-lookup"><span data-stu-id="5ef41-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="5ef41-177">下面讨论了主要区别。</span><span class="sxs-lookup"><span data-stu-id="5ef41-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="5ef41-178">若要将字符串标识为内插字符串，可在该字符串前面加上 `$` 符号。</span><span class="sxs-lookup"><span data-stu-id="5ef41-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="5ef41-179">和之间不能有任何空格 `$` `"` 开始一个字符串文本。</span><span class="sxs-lookup"><span data-stu-id="5ef41-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="5ef41-180">下面是一个基本示例，它使用 [`Message`](xref:microsoft.quantum.intrinsic.message) 函数将度量结果写入控制台，并将其写入其他 Q # 表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="5ef41-181">任何有效的 Q # 表达式都可以出现在内插字符串中。</span><span class="sxs-lookup"><span data-stu-id="5ef41-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="5ef41-182">有关 c # 语法的更多详细信息，请参阅内[*插字符串*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。</span><span class="sxs-lookup"><span data-stu-id="5ef41-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="5ef41-183">最明显的区别在于，Q # 不支持逐字（多行）内插字符串。</span><span class="sxs-lookup"><span data-stu-id="5ef41-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="5ef41-184">内插字符串中的表达式遵循 Q # 语法，而不是 c # 语法。</span><span class="sxs-lookup"><span data-stu-id="5ef41-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="5ef41-185">范围表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-185">Range Expressions</span></span>

<span data-ttu-id="5ef41-186">给定任意三个 `Int` 表达式 `start` ， `step` 和 `stop` `start .. step .. stop` 是一个范围表达式，其第一个元素是 `start` ，第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `stop` 传递。</span><span class="sxs-lookup"><span data-stu-id="5ef41-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="5ef41-187">例如，如果为正值，则范围可能为空 `step` `stop < start` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="5ef41-188">如果和之间的差异是的整数倍数，则范围的最后一个元素将为 `stop` `start` `stop` `step` ; 也就是说，范围在两端都包含。</span><span class="sxs-lookup"><span data-stu-id="5ef41-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="5ef41-189">给定任意两个 `Int` 表达式 `start` 和 `stop` ， `start .. stop` 是等于的范围表达式 `start .. 1 .. stop` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="5ef41-190">请注意， `step` 即使小于，隐含也是 + 1 `stop` `start` ，范围为空。</span><span class="sxs-lookup"><span data-stu-id="5ef41-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="5ef41-191">一些示例范围如下：</span><span class="sxs-lookup"><span data-stu-id="5ef41-191">Some example ranges are:</span></span>

- <span data-ttu-id="5ef41-192">`1..3`的范围为1、2、3。</span><span class="sxs-lookup"><span data-stu-id="5ef41-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="5ef41-193">`2..2..5`范围为2、4。</span><span class="sxs-lookup"><span data-stu-id="5ef41-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="5ef41-194">`2..2..6`范围为2、4、6。</span><span class="sxs-lookup"><span data-stu-id="5ef41-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="5ef41-195">`6..-2..2`范围为6、4、2。</span><span class="sxs-lookup"><span data-stu-id="5ef41-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="5ef41-196">`2..1`为空范围。</span><span class="sxs-lookup"><span data-stu-id="5ef41-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="5ef41-197">`2..6..7`范围为2。</span><span class="sxs-lookup"><span data-stu-id="5ef41-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="5ef41-198">`2..2..1`为空范围。</span><span class="sxs-lookup"><span data-stu-id="5ef41-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="5ef41-199">`1..-1..2`为空范围。</span><span class="sxs-lookup"><span data-stu-id="5ef41-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="5ef41-200">Qubit 表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-200">Qubit Expressions</span></span>

<span data-ttu-id="5ef41-201">唯一的 `Qubit` 表达式是绑定到 `Qubit` 数组的值或数组元素的符号 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="5ef41-202">没有 `Qubit` 文本。</span><span class="sxs-lookup"><span data-stu-id="5ef41-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="5ef41-203">Pauli 表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-203">Pauli Expressions</span></span>

<span data-ttu-id="5ef41-204">四个 `Pauli` 值（ `PauliI` 、 `PauliX` 、 `PauliY` 和 `PauliZ` ）都是有效的 `Pauli` 表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="5ef41-205">除了这样，唯一的 `Pauli` 表达式是绑定到 `Pauli` 数组的值或数组元素的符号 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="5ef41-206">结果表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-206">Result Expressions</span></span>

<span data-ttu-id="5ef41-207">`Result` `One` 和 `Zero` 都是有效的 `Result` 表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="5ef41-208">除了这样，唯一的 `Result` 表达式是绑定到 `Result` 数组的值或数组元素的符号 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="5ef41-209">特别要注意的是，与 `One` 整数不同 `1` ，它们之间没有直接转换。</span><span class="sxs-lookup"><span data-stu-id="5ef41-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="5ef41-210">对于和也是如此 `Zero` `0` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="5ef41-211">元组表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-211">Tuple Expressions</span></span>

<span data-ttu-id="5ef41-212">元组文本是一系列以逗号分隔的合适类型的元素表达式，括在和中 `(` `)` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="5ef41-213">例如， `(1, One)` 是一个 `(Int, Result)` 表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="5ef41-214">除了文本以外，唯一的元组表达式是绑定到元组值、元组数组的数组元素和返回元组的可调用调用的符号。</span><span class="sxs-lookup"><span data-stu-id="5ef41-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="5ef41-215">用户定义的类型表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="5ef41-216">用户定义类型的文本包含类型名称，后跟类型的基元组类型的元组文本。</span><span class="sxs-lookup"><span data-stu-id="5ef41-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="5ef41-217">例如，如果 `IntPair` 是基于的用户定义类型 `(Int, Int)` ，则是 `IntPair(2, 3)` 该类型的有效文本。</span><span class="sxs-lookup"><span data-stu-id="5ef41-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="5ef41-218">除了文本以外，用户定义类型的唯一表达式是绑定到该类型的值、该类型的数组元素和返回该类型的可调用调用的符号。</span><span class="sxs-lookup"><span data-stu-id="5ef41-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="5ef41-219">解包表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-219">Unwrap Expressions</span></span>

<span data-ttu-id="5ef41-220">在 Q # 中，解包运算符是一个尾随引号 `!` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="5ef41-221">例如，如果 `IntPair` 是具有基础类型的用户定义类型 `(Int, Int)` ，并且是 `s` 具有值的变量 `IntPair(2, 3)` ，则将 `s!` 为 `(2, 3)` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="5ef41-222">对于根据其他用户定义类型定义的用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="5ef41-222">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="5ef41-223">可以重复解包运算符;例如， `s!!` 指示的双重解包值 `s` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-223">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="5ef41-224">因此，如果 `WrappedPair` 是具有基础类型的用户定义类型 `IntPair` ，并且 `t` 是具有值的变量 `WrappedPair(IntPair(1,2))` ，则将 `t!!` 为 `(1,2)` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-224">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="5ef41-225">运算符的优先级高于除 `!` `[]` 数组索引和切片以外的其他所有运算符。</span><span class="sxs-lookup"><span data-stu-id="5ef41-225">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="5ef41-226">`!`和 `[]` bind 按位置; 即 `a[i]![3]` 应读取为 `((a[i])!)[3]` ：取的 `i` 第一个元素 `a` ，将其解包，然后获取解包值（必须是数组）的第3个元素。</span><span class="sxs-lookup"><span data-stu-id="5ef41-226">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="5ef41-227">运算符的优先级 `!` 有一个可能不明显的影响。</span><span class="sxs-lookup"><span data-stu-id="5ef41-227">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="5ef41-228">如果函数或操作返回一个值，则该函数或操作调用必须括在括号中，以便参数元组绑定到该调用，而不是绑定到解包。</span><span class="sxs-lookup"><span data-stu-id="5ef41-228">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="5ef41-229">例如：</span><span class="sxs-lookup"><span data-stu-id="5ef41-229">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="5ef41-230">数组表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-230">Array Expressions</span></span>

<span data-ttu-id="5ef41-231">数组文字是由和括起来的由逗号分隔的一个或多个元素表达式的 `[` 序列 `]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-231">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="5ef41-232">所有元素都必须兼容同一类型。</span><span class="sxs-lookup"><span data-stu-id="5ef41-232">All elements must be compatible with the same type.</span></span>


<span data-ttu-id="5ef41-233">如果给定两个相同类型的数组，则 `+` 可以使用二元运算符形成一个新数组，该数组是两个数组的串联。</span><span class="sxs-lookup"><span data-stu-id="5ef41-233">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="5ef41-234">例如， `[1,2,3] + [4,5,6]` 为 `[1,2,3,4,5,6]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-234">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="5ef41-235">数组创建</span><span class="sxs-lookup"><span data-stu-id="5ef41-235">Array Creation</span></span>

<span data-ttu-id="5ef41-236">给定类型和表达式后 `Int` ，运算符可 `new` 用于分配给定大小的新数组。</span><span class="sxs-lookup"><span data-stu-id="5ef41-236">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="5ef41-237">例如， `new Int[i + 1]` 将使用元素分配新 `Int` 数组 `i + 1` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-237">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="5ef41-238">新数组的元素被初始化为依赖于类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="5ef41-238">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="5ef41-239">在大多数情况下，这是零的一些变体。</span><span class="sxs-lookup"><span data-stu-id="5ef41-239">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="5ef41-240">对于引用实体的 qubits 和 callables，没有合理的默认值。</span><span class="sxs-lookup"><span data-stu-id="5ef41-240">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="5ef41-241">因此，对于这些类型，默认值是无效的引用，不能使用而不会导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="5ef41-241">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="5ef41-242">这类似于 c # 或 Java 等语言的空引用。</span><span class="sxs-lookup"><span data-stu-id="5ef41-242">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="5ef41-243">必须使用非默认值正确地初始化包含 qubits 或 callables 的数组，才能安全地使用其元素。</span><span class="sxs-lookup"><span data-stu-id="5ef41-243">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="5ef41-244">可在中找到合适的初始化例程 <xref:microsoft.quantum.arrays> 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-244">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="5ef41-245">每种类型的默认值为：</span><span class="sxs-lookup"><span data-stu-id="5ef41-245">The default values for each type are:</span></span>

<span data-ttu-id="5ef41-246">类型</span><span class="sxs-lookup"><span data-stu-id="5ef41-246">Type</span></span> | <span data-ttu-id="5ef41-247">默认</span><span class="sxs-lookup"><span data-stu-id="5ef41-247">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="5ef41-248">_无效的 qubit_</span><span class="sxs-lookup"><span data-stu-id="5ef41-248">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="5ef41-249">空范围，`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="5ef41-249">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="5ef41-250">_调用无效_</span><span class="sxs-lookup"><span data-stu-id="5ef41-250">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="5ef41-251">元组类型是逐个元素初始化的。</span><span class="sxs-lookup"><span data-stu-id="5ef41-251">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="5ef41-252">数组元素</span><span class="sxs-lookup"><span data-stu-id="5ef41-252">Array Elements</span></span>

<span data-ttu-id="5ef41-253">给定数组表达式和表达式时 `Int` ，可以使用 `[` 和数组元素运算符构造一个新的表达式 `]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-253">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="5ef41-254">新表达式将与数组的元素类型相同。</span><span class="sxs-lookup"><span data-stu-id="5ef41-254">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="5ef41-255">例如，如果 `a` 绑定到的数组 `Double` ，则 `a[4]` 是一个 `Double` 表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-255">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="5ef41-256">如果数组表达式不是简单的标识符，则必须将其括在括号中，以便选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="5ef41-256">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="5ef41-257">例如，如果 `a` 和 `b` 都是的数组 `Int` ，则连接中的元素将表示为：</span><span class="sxs-lookup"><span data-stu-id="5ef41-257">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="5ef41-258">Q # 中的所有数组都是从零开始的。</span><span class="sxs-lookup"><span data-stu-id="5ef41-258">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="5ef41-259">也就是说，数组的第一个元素 `a` 始终为 `a[0]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-259">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="5ef41-260">数组切片</span><span class="sxs-lookup"><span data-stu-id="5ef41-260">Array Slices</span></span>

<span data-ttu-id="5ef41-261">给定数组表达式和表达式时 `Range` ，可以使用 `[` 和数组切片运算符构造一个新的表达式 `]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-261">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="5ef41-262">新表达式将与数组的类型相同，并将包含由的元素编制索引的数组项 `Range` （按定义的顺序） `Range` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-262">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="5ef41-263">例如，如果 `a` 绑定到的数组 `Double` ，则 `a[3..-1..0]` 是一个 `Double[]` 表达式，该表达式包含的前四个元素， `a` 但其显示顺序与中的顺序相反 `a` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-263">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="5ef41-264">如果 `Range` 为空，则生成的数组切片长度为零。</span><span class="sxs-lookup"><span data-stu-id="5ef41-264">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="5ef41-265">就像引用数组元素一样，如果数组表达式不是简单的标识符，则必须将其括在括号中，以便进行切片。</span><span class="sxs-lookup"><span data-stu-id="5ef41-265">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="5ef41-266">如果 `a` 和 `b` 都是的数组 `Int` ，则串联的切片将表示为：</span><span class="sxs-lookup"><span data-stu-id="5ef41-266">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="5ef41-267">推断的开始/结束值</span><span class="sxs-lookup"><span data-stu-id="5ef41-267">Inferred start/end values</span></span>

<span data-ttu-id="5ef41-268">从0.8 版本开始，我们支持范围切片的上下文表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-268">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="5ef41-269">具体而言，范围切片表达式的上下文中可能会省略范围起始值和结束值。</span><span class="sxs-lookup"><span data-stu-id="5ef41-269">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="5ef41-270">在这种情况下，编译器将应用以下规则来推导范围的预期分隔符。</span><span class="sxs-lookup"><span data-stu-id="5ef41-270">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="5ef41-271">例如，如果省略范围起始值，则推断出的起始值</span><span class="sxs-lookup"><span data-stu-id="5ef41-271">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="5ef41-272">如果未指定步骤或指定步骤为正值，则为零;</span><span class="sxs-lookup"><span data-stu-id="5ef41-272">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="5ef41-273">如果指定的步骤为负，则为切片的数组的长度减去1。</span><span class="sxs-lookup"><span data-stu-id="5ef41-273">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="5ef41-274">如果省略范围结束值，则推断出的结束值</span><span class="sxs-lookup"><span data-stu-id="5ef41-274">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="5ef41-275">如果未指定步骤或指定步骤为正值，则切片数组的长度减1</span><span class="sxs-lookup"><span data-stu-id="5ef41-275">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="5ef41-276">如果指定的步骤为负数，则为零。</span><span class="sxs-lookup"><span data-stu-id="5ef41-276">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="5ef41-277">复制和更新表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-277">Copy-and-Update Expressions</span></span>

<span data-ttu-id="5ef41-278">由于所有 Q # 类型都是值类型（qubits 采用一个特殊的角色），因此在值绑定到符号或重新绑定符号时，会创建 "复制"。</span><span class="sxs-lookup"><span data-stu-id="5ef41-278">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="5ef41-279">也就是说，Q # 的行为与在分配时创建副本的行为相同。</span><span class="sxs-lookup"><span data-stu-id="5ef41-279">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="5ef41-280">当然，实际上只需根据需要重新创建相关的部分。</span><span class="sxs-lookup"><span data-stu-id="5ef41-280">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="5ef41-281">这特别包括数组。</span><span class="sxs-lookup"><span data-stu-id="5ef41-281">This in particular also includes arrays.</span></span>
<span data-ttu-id="5ef41-282">具体而言，不能更新数组项。</span><span class="sxs-lookup"><span data-stu-id="5ef41-282">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="5ef41-283">若要修改现有阵列，需要利用*复制和更新*机制。</span><span class="sxs-lookup"><span data-stu-id="5ef41-283">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="5ef41-284">可以通过*复制和更新*表达式从现有阵列创建新的阵列。</span><span class="sxs-lookup"><span data-stu-id="5ef41-284">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="5ef41-285">复制和更新表达式是窗体的表达式 `expression1 w/ expression2 <- expression3` ，其中必须 `expression1` 是 `T[]` 某种类型的类型 `T` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-285">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="5ef41-286">第二个 `expression2` 定义要修改的元素的索引，该索引与中的数组进行比较 `expression1` ，并且必须是类型的类型 `Int` 或 `Range` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-286">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="5ef41-287">如果 `expression2` 的类型为，则必须为 `Int` `expression3` 类型 `T` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-287">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="5ef41-288">如果 `expression2` 的类型为，则必须为 `Range` `expression3` 类型 `T[]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-288">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="5ef41-289">复制和更新表达式 `arr w/ idx <- value` 构造一个新数组，其中所有元素都设置为中的相应元素 `arr` ，但中的元素除外 `idx` ，后者设置为中的一个 `value` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-289">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="5ef41-290">例如，如果 `arr` 包含一个数组 `[0,1,2,3]` ，则</span><span class="sxs-lookup"><span data-stu-id="5ef41-290">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="5ef41-291">`arr w/ 0 <- 10`是数组 `[10,1,2,3]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-291">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="5ef41-292">`arr w/ 2 <- 10`是数组 `[0,1,10,3]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-292">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="5ef41-293">`arr w/ 0..2..3 <- [10,12]`是数组 `[10,1,12,3]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-293">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="5ef41-294">已命名项的复制和更新表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-294">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="5ef41-295">对于用户定义类型中的命名项，存在类似的表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-295">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="5ef41-296">例如，请考虑类型</span><span class="sxs-lookup"><span data-stu-id="5ef41-296">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="5ef41-297">如果 `c` 包含类型的值 `Complex(1., -1.)` ，则 `c w/ Re <- 0.` 是类型的表达式， `Complex` 其计算结果为 `Complex(0., -1.)` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-297">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="5ef41-298">交错数组</span><span class="sxs-lookup"><span data-stu-id="5ef41-298">Jagged Arrays</span></span>

<span data-ttu-id="5ef41-299">交错数组（有时称为 "数组的数组"）是一个其元素为数组的数组。</span><span class="sxs-lookup"><span data-stu-id="5ef41-299">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="5ef41-300">交错数组的元素的大小可以不同。</span><span class="sxs-lookup"><span data-stu-id="5ef41-300">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="5ef41-301">下面的示例演示如何声明和初始化表示乘法表的交错数组。</span><span class="sxs-lookup"><span data-stu-id="5ef41-301">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="5ef41-302">Callables 的数组</span><span class="sxs-lookup"><span data-stu-id="5ef41-302">Arrays of callables</span></span> 

<span data-ttu-id="5ef41-303">请注意，可在下面找到有关可调用类型的更多详细信息，还可在下一页的 "[问答" 中找到操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="5ef41-303">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="5ef41-304">如果公共元素类型是运算或函数类型，则所有元素必须具有相同的输入和输出类型。</span><span class="sxs-lookup"><span data-stu-id="5ef41-304">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="5ef41-305">数组的元素类型将支持所有元素支持的任何函子。</span><span class="sxs-lookup"><span data-stu-id="5ef41-305">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="5ef41-306">例如，如果、和都是，则支持、支持 `Op1` `Op2` `Op3` `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` 和 `Op3` 均支持：</span><span class="sxs-lookup"><span data-stu-id="5ef41-306">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="5ef41-307">`[Op1, Op2]`是一组 `(Qubit[] => Unit)` 操作。</span><span class="sxs-lookup"><span data-stu-id="5ef41-307">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="5ef41-308">`[Op1, Op3]`是一组 `(Qubit[] => Unit is Adj)` 操作。</span><span class="sxs-lookup"><span data-stu-id="5ef41-308">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="5ef41-309">`[Op2, Op3]`是一组 `(Qubit[] => Unit is Ctl)` 操作。</span><span class="sxs-lookup"><span data-stu-id="5ef41-309">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="5ef41-310">不允许空数组文本 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-310">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="5ef41-311">而是使用 `new ★[0]` ，其中 `★` 作为适当类型的占位符，允许创建长度为零的所需数组。</span><span class="sxs-lookup"><span data-stu-id="5ef41-311">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="5ef41-312">条件表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-312">Conditional Expressions</span></span>

<span data-ttu-id="5ef41-313">假设有两个具有相同类型和布尔表达式的其他表达式，则可以使用问号和竖线构造条件表达式 `?` `|` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-313">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="5ef41-314">例如， `a==b ? c | d` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-314">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="5ef41-315">在此示例中， `c` 如果为 true，则条件表达式的值为 `a==b` ; 如果为 false，则为 `d` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-315">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="5ef41-316">带 callables 的条件表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-316">Conditional expressions with callables</span></span>

<span data-ttu-id="5ef41-317">这两个表达式的计算结果可能为具有相同输入和输出但支持不同函子的操作。</span><span class="sxs-lookup"><span data-stu-id="5ef41-317">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="5ef41-318">在这种情况下，条件表达式的类型是一个操作，其中包含支持两个表达式支持的任何函子的输入和输出。</span><span class="sxs-lookup"><span data-stu-id="5ef41-318">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="5ef41-319">例如，如果、和都是，则支持、支持 `Op1` `Op2` `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` 和 `Op3` 均支持：</span><span class="sxs-lookup"><span data-stu-id="5ef41-319">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="5ef41-320">`flag ? Op1 | Op2`为 `(Qubit[] => Unit)` 操作。</span><span class="sxs-lookup"><span data-stu-id="5ef41-320">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="5ef41-321">`flag ? Op1 | Op3`为 `(Qubit[] => Unit is Adj)` 操作。</span><span class="sxs-lookup"><span data-stu-id="5ef41-321">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="5ef41-322">`flag ? Op2 | Op3`为 `(Qubit[] => Unit is Ctl)` 操作。</span><span class="sxs-lookup"><span data-stu-id="5ef41-322">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="5ef41-323">如果两个可能的结果表达式中有一个包含函数或操作调用，则只会在该结果是调用的值时进行调用。</span><span class="sxs-lookup"><span data-stu-id="5ef41-323">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="5ef41-324">例如，在这种情况下 `a==b ? C(qs) | D(qs)` ，如果 `a==b` 为 true，则 `C` 将调用操作，如果为 false，则只 `D` 调用。</span><span class="sxs-lookup"><span data-stu-id="5ef41-324">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="5ef41-325">这类似于其他语言的短路。</span><span class="sxs-lookup"><span data-stu-id="5ef41-325">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="5ef41-326">可调用表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-326">Callable Expressions</span></span>

<span data-ttu-id="5ef41-327">可调用的文本是编译范围中定义的操作或函数的名称。</span><span class="sxs-lookup"><span data-stu-id="5ef41-327">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="5ef41-328">例如， `X` 是引用标准库操作的操作文本 `X` ， `Message` 是引用标准库函数的函数文本 `Message` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-328">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="5ef41-329">如果操作支持 `Adjoint` 函子，则 `Adjoint op` 是操作表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-329">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="5ef41-330">同样，如果操作支持 `Controlled` 函子，则 `Controlled op` 是操作表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-330">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="5ef41-331">这些表达式的类型在[调用专用](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)化时指定。</span><span class="sxs-lookup"><span data-stu-id="5ef41-331">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="5ef41-332">`Adjoint` `Controlled` 除了 `!` 带有 [] "的解包运算符和数组索引外，函子（和）与其他所有运算符更密切地绑定。</span><span class="sxs-lookup"><span data-stu-id="5ef41-332">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="5ef41-333">因此，以下各项均为合法，前提是这些操作支持使用的函子：</span><span class="sxs-lookup"><span data-stu-id="5ef41-333">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="5ef41-334">类型参数化的可调用表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-334">Type-parameterized callable expressions</span></span>

<span data-ttu-id="5ef41-335">可调用的文本可用作值，假设要分配给变量或传递给其他可调用的。</span><span class="sxs-lookup"><span data-stu-id="5ef41-335">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="5ef41-336">在这种情况下，如果可调用的具有[类型参数](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)，则必须将它们作为可调用值的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="5ef41-336">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="5ef41-337">可调用的值不能具有任何未指定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="5ef41-337">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="5ef41-338">例如，如果 `Fun` 是具有签名的函数 `'T1->Unit` ：</span><span class="sxs-lookup"><span data-stu-id="5ef41-338">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="5ef41-339">可调用调用表达式</span><span class="sxs-lookup"><span data-stu-id="5ef41-339">Callable Invocation Expressions</span></span>

<span data-ttu-id="5ef41-340">给定可调用（操作或函数）表达式和可调用签名的输入类型的元组表达式时，可以通过将元组表达式追加到可调用表达式来形成调用表达式。</span><span class="sxs-lookup"><span data-stu-id="5ef41-340">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="5ef41-341">调用表达式的类型是可调用的签名的输出类型。</span><span class="sxs-lookup"><span data-stu-id="5ef41-341">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="5ef41-342">例如，如果 `Op` 是具有签名的操作 `((Int, Qubit) => Double)` ， `Op(3, qubit1)` 则为类型的表达式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-342">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="5ef41-343">同样，如果 `Sin` 是具有签名的函数 `(Double -> Double)` ， `Sin(0.1)` 则是类型的表达式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-343">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="5ef41-344">最后，如果 `Builder` 是具有签名的函数 `(Int -> (Int -> Int))` ，则 `Builder(3)` 是从到 Int 的函数。</span><span class="sxs-lookup"><span data-stu-id="5ef41-344">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="5ef41-345">若要调用可调用值表达式的结果，需要在可调用的表达式前后使用一对括号。</span><span class="sxs-lookup"><span data-stu-id="5ef41-345">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="5ef41-346">因此，若要调用 `Builder` 上一段落中调用的结果，正确的语法为：</span><span class="sxs-lookup"><span data-stu-id="5ef41-346">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="5ef41-347">调用[类型参数化](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)的可调用时，可以在尖括号 `<` 和可调用表达式之后指定实际的类型参数 `>` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-347">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="5ef41-348">这通常是不必要的，因为 Q # 编译器将推断实际类型。</span><span class="sxs-lookup"><span data-stu-id="5ef41-348">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="5ef41-349">但是，如果*未指定*类型参数化的参数，则此[部分应用程序](xref:microsoft.quantum.guide.operationsfunctions#partial-application)需要它。</span><span class="sxs-lookup"><span data-stu-id="5ef41-349">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="5ef41-350">在将具有不同函子支持的操作传递给可调用时，有时也很有用。</span><span class="sxs-lookup"><span data-stu-id="5ef41-350">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="5ef41-351">例如，如果具有签名，并具有签名， `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` 并具有签名，则 `Op3` `(Qubit[] => Unit)` 将 `Func` 使用 `Op1` 作为第一个参数进行调用，并 `Op2` `Op3` 将作为第二个参数，第三个参数为：</span><span class="sxs-lookup"><span data-stu-id="5ef41-351">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="5ef41-352">类型规范是必需的 `Op3` ，因为和 `Op1` 具有不同的类型，因此，如果没有规范，编译器会将此视为不明确的。</span><span class="sxs-lookup"><span data-stu-id="5ef41-352">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="5ef41-353">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="5ef41-353">Operator Precedence</span></span>

<span data-ttu-id="5ef41-354">除了之外，所有二元运算符都是右结合运算符 `^` 。</span><span class="sxs-lookup"><span data-stu-id="5ef41-354">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="5ef41-355">`[` `]` 对于数组切片和索引，请在任何运算符之前绑定。</span><span class="sxs-lookup"><span data-stu-id="5ef41-355">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="5ef41-356">`Adjoint` `Controlled` 数组索引后，但在所有其他运算符之前，函子和绑定。</span><span class="sxs-lookup"><span data-stu-id="5ef41-356">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="5ef41-357">用于运算和函数调用的括号也绑定在任何运算符之前，但在数组索引和函子之后。</span><span class="sxs-lookup"><span data-stu-id="5ef41-357">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="5ef41-358">按优先顺序排列的运算符，从高到低：</span><span class="sxs-lookup"><span data-stu-id="5ef41-358">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="5ef41-359">操作员</span><span class="sxs-lookup"><span data-stu-id="5ef41-359">Operator</span></span> | <span data-ttu-id="5ef41-360">元</span><span class="sxs-lookup"><span data-stu-id="5ef41-360">Arity</span></span> | <span data-ttu-id="5ef41-361">说明</span><span class="sxs-lookup"><span data-stu-id="5ef41-361">Description</span></span> | <span data-ttu-id="5ef41-362">操作数类型</span><span class="sxs-lookup"><span data-stu-id="5ef41-362">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="5ef41-363">加`!`</span><span class="sxs-lookup"><span data-stu-id="5ef41-363">trailing `!`</span></span> | <span data-ttu-id="5ef41-364">一元</span><span class="sxs-lookup"><span data-stu-id="5ef41-364">Unary</span></span> | <span data-ttu-id="5ef41-365">解包</span><span class="sxs-lookup"><span data-stu-id="5ef41-365">Unwrap</span></span> | <span data-ttu-id="5ef41-366">任何用户定义类型</span><span class="sxs-lookup"><span data-stu-id="5ef41-366">Any user-defined type</span></span>
 <span data-ttu-id="5ef41-367">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="5ef41-367">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="5ef41-368">一元</span><span class="sxs-lookup"><span data-stu-id="5ef41-368">Unary</span></span> | <span data-ttu-id="5ef41-369">数值负，按位求补，逻辑求反</span><span class="sxs-lookup"><span data-stu-id="5ef41-369">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="5ef41-370">`Int`对于，为 `BigInt` 或 `Double` `-` `Int` `BigInt` `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="5ef41-370">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="5ef41-371">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-371">Binary</span></span> | <span data-ttu-id="5ef41-372">整数幂</span><span class="sxs-lookup"><span data-stu-id="5ef41-372">Integer power</span></span> | <span data-ttu-id="5ef41-373">`Int`对于 `BigInt` 指数，为或 `Int`</span><span class="sxs-lookup"><span data-stu-id="5ef41-373">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="5ef41-374">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="5ef41-374">`/`, `*`, `%`</span></span> | <span data-ttu-id="5ef41-375">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-375">Binary</span></span> | <span data-ttu-id="5ef41-376">除法、乘法、integer 模数</span><span class="sxs-lookup"><span data-stu-id="5ef41-376">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="5ef41-377">`Int`对于 `BigInt` 、或 `Double` 为 `/` `*` `Int` `BigInt``%`</span><span class="sxs-lookup"><span data-stu-id="5ef41-377">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="5ef41-378">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="5ef41-378">`+`, `-`</span></span> | <span data-ttu-id="5ef41-379">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-379">Binary</span></span> | <span data-ttu-id="5ef41-380">加法或 string 和 array 串联，减法</span><span class="sxs-lookup"><span data-stu-id="5ef41-380">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="5ef41-381">`Int`、 `BigInt` 或 `Double` ，另外 `String` 或任何类型的数组类型`+`</span><span class="sxs-lookup"><span data-stu-id="5ef41-381">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="5ef41-382">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="5ef41-382">`<<<`, `>>>`</span></span> | <span data-ttu-id="5ef41-383">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-383">Binary</span></span> | <span data-ttu-id="5ef41-384">左移、右移</span><span class="sxs-lookup"><span data-stu-id="5ef41-384">Left shift, right shift</span></span> | <span data-ttu-id="5ef41-385">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5ef41-385">`Int` or `BigInt`</span></span>
 <span data-ttu-id="5ef41-386">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="5ef41-386">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="5ef41-387">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-387">Binary</span></span> | <span data-ttu-id="5ef41-388">小于、小于或等于、大于、大于等于或等于比较的比较</span><span class="sxs-lookup"><span data-stu-id="5ef41-388">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="5ef41-389">`Int`， `BigInt` 或`Double`</span><span class="sxs-lookup"><span data-stu-id="5ef41-389">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="5ef41-390">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="5ef41-390">`==`, `!=`</span></span> | <span data-ttu-id="5ef41-391">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-391">Binary</span></span> | <span data-ttu-id="5ef41-392">相等，不等于比较</span><span class="sxs-lookup"><span data-stu-id="5ef41-392">equal, not-equal comparisons</span></span> | <span data-ttu-id="5ef41-393">任何基元类型</span><span class="sxs-lookup"><span data-stu-id="5ef41-393">any primitive type</span></span>
 `&&&` | <span data-ttu-id="5ef41-394">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-394">Binary</span></span> | <span data-ttu-id="5ef41-395">位与</span><span class="sxs-lookup"><span data-stu-id="5ef41-395">Bitwise AND</span></span> | <span data-ttu-id="5ef41-396">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5ef41-396">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="5ef41-397">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-397">Binary</span></span> | <span data-ttu-id="5ef41-398">按位“异或”</span><span class="sxs-lookup"><span data-stu-id="5ef41-398">Bitwise XOR</span></span> | <span data-ttu-id="5ef41-399">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5ef41-399">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="5ef41-400">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-400">Binary</span></span> | <span data-ttu-id="5ef41-401">按位“或”</span><span class="sxs-lookup"><span data-stu-id="5ef41-401">Bitwise OR</span></span> | <span data-ttu-id="5ef41-402">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5ef41-402">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="5ef41-403">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-403">Binary</span></span> | <span data-ttu-id="5ef41-404">逻辑与</span><span class="sxs-lookup"><span data-stu-id="5ef41-404">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="5ef41-405">二进制</span><span class="sxs-lookup"><span data-stu-id="5ef41-405">Binary</span></span> | <span data-ttu-id="5ef41-406">逻辑或</span><span class="sxs-lookup"><span data-stu-id="5ef41-406">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="5ef41-407">二进制/三元</span><span class="sxs-lookup"><span data-stu-id="5ef41-407">Binary/Ternary</span></span> | <span data-ttu-id="5ef41-408">范围运算符</span><span class="sxs-lookup"><span data-stu-id="5ef41-408">Range operator</span></span> | `Int`
 <span data-ttu-id="5ef41-409">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="5ef41-409">`?` `|`</span></span> | <span data-ttu-id="5ef41-410">三元</span><span class="sxs-lookup"><span data-stu-id="5ef41-410">Ternary</span></span> | <span data-ttu-id="5ef41-411">条件逻辑</span><span class="sxs-lookup"><span data-stu-id="5ef41-411">Conditional</span></span> | <span data-ttu-id="5ef41-412">`Bool`对于左侧</span><span class="sxs-lookup"><span data-stu-id="5ef41-412">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="5ef41-413">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="5ef41-413">`w/` `<-`</span></span> | <span data-ttu-id="5ef41-414">三元</span><span class="sxs-lookup"><span data-stu-id="5ef41-414">Ternary</span></span> | <span data-ttu-id="5ef41-415">复制和更新</span><span class="sxs-lookup"><span data-stu-id="5ef41-415">Copy-and-update</span></span> | <span data-ttu-id="5ef41-416">请参阅[复制和更新表达式](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="5ef41-416">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="whats-next"></a><span data-ttu-id="5ef41-417">下一步是什么？</span><span class="sxs-lookup"><span data-stu-id="5ef41-417">What's Next?</span></span>
<span data-ttu-id="5ef41-418">现在你可以使用 Q # 中的表达式，你可以转到[q # 中的操作和函数](xref:microsoft.quantum.guide.operationsfunctions)来了解如何定义和调用操作和函数。</span><span class="sxs-lookup"><span data-stu-id="5ef41-418">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
