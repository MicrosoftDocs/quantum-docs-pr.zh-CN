---
title: 表达式Q#
description: 了解如何在中将常量、变量、运算符、操作和函数作为表达式进行指定、引用和合并 Q# 。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: b6cc97dfee05dc843e213e84f17043714a8a9656
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869607"
---
# <a name="expressions-in-no-locq"></a>表达式Q#

## <a name="numeric-expressions"></a>数值表达式

数值表达式是、或类型的表达式 `Int` `BigInt` `Double` 。
也就是说，它们是整数或浮点数。

`Int`中的文本 Q# 作为一系列数字写入。
支持十六进制和二进制整数 `0x` ，并分别使用和前缀来编写 `0b` 。

`BigInt`中的文本 Q# 具有尾随 `l` 或 `L` 后缀。
支持十六进制大整数，并使用 "0x" 前缀来写入。
因此，以下是文本的有效用法 `BigInt` ：

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`中的文本 Q# 是使用十进制数字编写的浮点数。
可以使用或不使用小数点、 `.` 或使用 "e" 或 "e" 指示的指数部分来编写它们 (之后，只有可能的负号和十进制数字) 有效。
下面是有效的 `Double` 文本： `0.0` 、 `1.2e5` 、 `1e-5` 。

给定任意元素类型的数组表达式，你可以 `Int` 使用 [`Length`](xref:microsoft.quantum.core.length) 内置函数形成表达式，并将数组表达式括在括号中。
例如，如果 `a` 绑定到数组，则 `Length(a)` 是整数表达式。
如果 `b` 是整数数组的数组，则 `Int[][]` `Length(b)` 为中的子数组的数目 `b` ， `Length(b[1])` 是中第二个子数组 `b` 中的整数的数目。

假设两个数值表达式具有相同的类型，则可以 `+` 使用二元运算符、、 `-` `*` 和 `/` 形成新的数值表达式。
新表达式的类型与构成表达式的类型相同。

给定两个整数表达式，使用二元运算符 `^` (power) 构成一个新的整数表达式。
同样，您还可以使用 `^` with 两个双表达式来形成新的双精度表达式。
最后，可以 `^` 在左侧使用大整数，在右侧使用整数来形成新的大整数表达式。
在这种情况下，第二个参数必须适合32位;如果不是，则引发运行时错误。

假设有两个整数或大整数表达式，则使用 `%` (取模) 、 `&&&` (按位 "与") "、" `|||` (位 "或") "或 `^^^` (位 XOR) 运算符来形成一个新整数或大整数表达式。

给定左侧的整数表达式或大整数表达式，并在右侧 (使用整数表达式， `<<<`) 或 `>>>` (算术右移位) 运算符来创建与左侧表达式的类型相同的新表达式。

第二个参数 (移位量) 转换操作必须大于或等于零;负移位量的行为是不确定的。
移位运算的移位量还必须适合32位;如果不是，则引发运行时错误。
如果移动的数字是一个整数，则移位量将被解释 `mod 64` ; 也就是说，1的移位和65的移位具有相同的效果。

对于整数和大整数值，移位均为算术运算。
向左或向右移位负值将导致负数。
也就是说，向左或向右移动一个步骤的方式与2的乘法或除法相同。

对于负数，整数除法和整数取模的行为与 c # 的行为相同。
也就是说， `a % b` 始终具有相同的符号 `a` ， `b * (a / b) + a % b` 始终等于 `a` 。
例如：

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

大整数除法和取模运算的工作方式相同。

如果给定了数值表达式，则可以使用一元运算符建立新的表达式 `-` 。
新表达式与构成表达式的类型相同。

给定任意整数或大整数表达式，可以使用 `~~~` (按位求补) 一元运算符来形成同一类型的新表达式。

## <a name="boolean-expressions"></a>布尔表达式

这两个 `Bool` 文本值为 `true` 和 `false` 。

给定任意两个具有相同基元类型的表达式， `==` 和 `!=` 二元运算符可用于构造 `Bool` 表达式。
如果两个表达式相等，则表达式为 true; 否则为 false。

不能比较用户定义类型的值，只能比较它们的解包值。 例如，使用 "解包" 运算符 `!` () 中的[类型 Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)详细说明，

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

值的相等比较 `Qubit` 是恒等的; 即，两个表达式是否标识同一 qubit。
这两个 qubits 的状态不会进行比较、访问、度量或修改。

`Double`由于舍入效果，值的相等比较可能会产生误导。
例如 `49.0 * (1.0/49.0) != 1.0`。

给定任意两个数值表达式，二元运算符 `>` 、 `<` 、 `>=` 和可 `<=` 用于构造新的布尔表达式，如果第一个表达式分别大于、小于、大于或等于，或者小于或等于第二个表达式，则该值为 true。

给定任意两个布尔表达式，使用 `and` 二元运算符来构造新的布尔表达式，如果两个表达式都为 true，则该值为 true。 同样， `or` 如果两个表达式都为 true，则使用运算符会创建一个 true 表达式。

给定任何布尔表达式， `not` 一元运算符可用于构造新的布尔表达式，如果构成表达式为 false，则为 true。

## <a name="string-expressions"></a>字符串表达式

Q#允许在 " `fail` [控制流](xref:microsoft.quantum.guide.controlflow#fail-statement)") 和标准函数中说明 (语句中使用字符串 [`Message`](xref:microsoft.quantum.intrinsic.message) 。 后者的特定行为取决于所使用的模拟器，但通常会在程序期间调用时将消息写入主机控制台 Q# 。

中的字符串 Q# 是文本或内插字符串。

字符串文本类似于大多数语言中的简单字符串文本：用双引号引起来的 Unicode 字符序列 `" "` 。
在字符串内，使用反斜杠字符将 `\` 双引号字符转义 (`\"`) ，或插入新行 ( `\n` ) 、回车符 (`\r`) 或 () 的选项卡 `\t` 。
例如：

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>内插字符串

Q#字符串内插的语法是 c # 语法的子集。 下面是与以下各项相关的要点 Q# ：

* 若要将字符串标识为内插字符串，可在该字符串前面加上 `$` 符号。 与之间不能存在空格， `$` `"` 后者用于启动字符串文本。

* 下面是一个基本示例，使用 [`Message`](xref:microsoft.quantum.intrinsic.message) 函数将度量结果写入控制台，并将其写入其他 Q# 表达式。

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* 任何有效的 Q# 表达式都可以出现在内插字符串中。

* 内插字符串中的表达式遵循 Q# 语法，而不是 c # 语法。 最明显的区别在于不 Q# 支持逐字 (多行) 内插字符串。

有关 c # 语法的更多详细信息，请参阅内[*插字符串*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。

## <a name="range-expressions"></a>范围表达式

给定任意三个 `Int` 表达式 `start` ：和， `step` `stop` 表达式是一个 `start .. step .. stop` 范围表达式，其第一个元素是 `start` ，第二个元素是，第三个元素 `start+step` 为 `start+step+step` ，依此类推，直到您通过 `stop` 。
例如，如果为正和，则范围可能为空 `step` `stop < start` 。

此范围包含在两端。 也就是说，如果和的差 `start` 是的 `stop` 整数倍数，则该 `step` 范围的最后一个元素将为 `stop` 。

给定任意两个 `Int` 表达式 `start` 和 `stop` ，表达式 `start .. stop` 是等于的范围表达式 `start .. 1 .. stop` 。
请注意， `step` 即使小于，隐含也是 + 1 `stop` `start` ，范围为空。

一些示例范围如下：

- `1..3`的范围为1、2、3。
- `2..2..5`范围为2、4。
- `2..2..6`范围为2、4、6。
- `6..-2..2`范围为6、4、2。
- `2..1`为空范围。
- `2..6..7`范围为2。
- `2..2..1`为空范围。
- `1..-1..2`为空范围。

## <a name="qubit-expressions"></a>Qubit 表达式

唯一的 `Qubit` 表达式是绑定到 `Qubit` 数组的值或数组元素的符号 `Qubit` 。
没有 `Qubit` 文本。

## <a name="pauli-expressions"></a>Pauli 表达式

四个 `Pauli` 值（ `PauliI` 、 `PauliX` 、 `PauliY` 和 `PauliZ` ）都是有效的 `Pauli` 表达式。

除了这样，唯一的 `Pauli` 表达式是绑定到 `Pauli` 数组的值或数组元素的符号 `Pauli` 。

## <a name="result-expressions"></a>结果表达式

`Result` `One` 和 `Zero` 都是有效的 `Result` 表达式。

除了这样，唯一的 `Result` 表达式是绑定到 `Result` 数组的值或数组元素的符号 `Result` 。
特别要注意的是，与 `One` 整数不同 `1` ，它们之间没有直接转换。
对于和也是如此 `Zero` `0` 。

## <a name="tuple-expressions"></a>元组表达式

元组文本是一系列以逗号分隔的适当类型的元素表达式，括在括号中。
例如， `(1, One)` 是一个 `(Int, Result)` 表达式。

除了文本以外，唯一的元组表达式是绑定到元组值、元组数组的数组元素和返回元组的可调用调用的符号。

## <a name="user-defined-type-expressions"></a>用户定义的类型表达式

用户定义类型的文本包含类型名称，后跟类型的基元组类型的元组文本。
例如，如果 `IntPair` 是基于的用户定义类型 `(Int, Int)` ，则 `IntPair(2, 3)` 是该类型的有效文本。

除了文本以外，用户定义类型的唯一表达式是绑定到该类型的值、该类型的数组元素和返回该类型的可调用调用的符号。

## <a name="unwrap-expressions"></a>解包表达式

在中 Q# ，解包运算符是一个尾随引号 `!` 。
例如，如果 `IntPair` 是具有基础类型的用户定义类型， `(Int, Int)` 并且 `s` 是具有值的变量，则 `IntPair(2, 3)` `s!` 为 `(2, 3)` 。

对于根据其他用户定义类型定义的用户定义类型，可以重复解包运算符。 例如， `s!!` 指示的双重解包值 `s` 。
因此，如果 `WrappedPair` 是具有基础类型的用户定义类型 `IntPair` ，并且 `t` 是具有值的变量 `WrappedPair(IntPair(1,2))` ，则 `t!!` 为 `(1,2)` 。

运算符的优先级高于除 `!` `[]` 数组索引和切片以外的其他所有运算符。
`!`并 `[]` 绑定按位置; 即， `a[i]![3]` 读取为 `((a[i])!)[3]` ：取 `i` 的第一个元素，将 `a` 其解包，然后获取解包值 (的第三个元素，该元素必须是) 的数组。

运算符的优先级 `!` 有一个可能不明显的影响。
如果函数或操作返回一个值，则该函数或操作调用必须括在括号中，以便参数元组绑定到该调用，而不是绑定到解包。
例如：

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>数组表达式

数组文字是由逗号分隔的一个或多个元素表达式的序列，用方括号括起来 `[]` 。
所有元素都必须兼容同一类型。

给定两个类型相同的数组，使用二元 `+` 运算符来构成两个数组串联的新数组。
例如，`[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`。

### <a name="array-creation"></a>数组创建

给定一个类型和 `Int` 表达式，使用 `new` 运算符分配一个给定大小的新数组。
例如， `new Int[i + 1]` 使用元素分配新 `Int` 数组 `i + 1` 。

不允许使用空数组文本（如 `[]` ）。
相反，您可以使用创建长度为零的数组 `new T[0]` ，其中 `T` 是适合类型的占位符。

新数组的元素初始化为依赖于类型的默认值。
在大多数情况下，这是零的一些变体。

对于引用实体的 qubits 和 callables，没有合理的默认值。
因此，对于这些类型，默认值是无效的引用，不能在不引发运行时错误的情况下使用，这类似于 c # 或 Java 等语言的空引用。
必须使用非默认值初始化包含 qubits 或 callables 的数组，才能安全地使用其元素。 有关适当的初始化例程，请参见 <xref:microsoft.quantum.arrays> 。

每种类型的默认值为：

类型 | 默认
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _无效的 qubit_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | 空范围，`1..1..0`
 `Callable` | _调用无效_
 `Array['T]` | `'T[0]`

元组类型初始化逐个元素元素。


### <a name="array-elements"></a>数组元素

给定数组表达式和 `Int` 表达式，使用数组元素运算符构成一个新表达式 `[]` 。
新表达式的类型与数组的元素类型相同。
例如，如果 `a` 绑定到类型的数组 `Double` ，则 `a[4]` 是一个 `Double` 表达式。

如果数组表达式不是简单的标识符，则必须将其括在括号中，以便选择一个元素。
例如，如果 `a` 和 `b` 都是类型的数组 `Int` ，则连接中的元素表示为：

```qsharp
(a + b)[13]
```

中的所有数组 Q# 都是从零开始的。
也就是说，数组的第一个元素 `a` 始终为 `a[0]` 。


### <a name="array-slices"></a>数组切片

给定数组表达式和 `Range` 表达式，使用数组切片运算符构成一个新表达式 `[ ]` 。
新表达式与数组的类型相同，并包含按定义的顺序由的元素索引的数组项 `Range` `Range` 。
例如，如果 `a` 绑定到类型的数组 `Double` ，则 `a[3..-1..0]` 是一个 `Double[]` 表达式，该表达式包含的前四个元素， `a` 但其显示顺序与中的顺序相反 `a` 。

如果 `Range` 为空，则生成的数组切片的长度为零。

就像引用数组元素一样，如果数组表达式不是简单的标识符，则必须将其括在括号中，以便对其进行切片。
例如，如果 `a` 和 `b` 都是类型的数组 `Int` ，则串联的切片表示为：

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>推断的开始/结束值

从[0.8 版本](xref:microsoft.quantum.relnotes)开始，我们支持范围切片的上下文表达式。 特别是，在范围切片表达式的上下文中，您可以省略范围起始值和结束值。 在这种情况下，编译器会应用以下规则来推断范围的预期分隔符：

* 如果省略范围*起始*值，则推断出的起始值
  * 如果未指定步骤或指定步骤为正值，则为零。  
  * 如果指定的步骤为负，则为切片的数组的长度减一。

* 如果省略范围*结束*值，则推断出的结束值
  * 如果未指定步骤或指定步骤为正值，则为切片的数组的长度减一。
  * 如果指定的步骤为负数，则为零。

一些示例如下：

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

### <a name="copy-and-update-expressions"></a>复制和更新表达式

由于所有 Q# 类型都是值类型 (，而 qubits 采用某种特殊的角色) ，所以当值绑定到某个符号或重新绑定符号时，将创建一个 "复制"。 也就是说，的行为与 Q# 使用赋值运算符创建副本的行为相同。 

当然，在实际情况下，只会根据需要重新创建相关的部分。 这会影响复制数组的方式，因为不能更新数组项。 若要修改现有阵列，需要利用*复制和更新*机制。

可以通过使用运算符和的*复制和更新*表达式从现有数组创建新数组 `w/` `<-` 。
复制和更新表达式是格式为的表达式 `expression1 w/ expression2 <- expression3` ，其中

* `expression1``T[]`对于某些类型，必须是类型 `T` 。
* `expression2`定义要修改的数组中指定的索引 `expression1` 。 `expression2`必须是类型 `Int` 或类型 `Range` 。
* `expression3``expression1`基于中指定的索引， (s) 用于更新中的元素的值 `expression2` 。 如果 `expression2` 为类型 `Int` ，则 `expression3` 必须为类型 `T` 。 如果 `expression2` 为类型 `Range` ，则 `expression3` 必须为类型 `T[]` 。

例如，复制和更新表达式将 `arr w/ idx <- value` 构造一个新数组，其中所有元素都设置为中的相应元素 `arr` ，但指定的元素 () `idx` ，该元素设置为中) 的值 (`value` 。 

给定 `arr` 包含数组 `[0,1,2,3]` ，然后 

- `arr w/ 0 <- 10`是数组 `[10,1,2,3]` 。
- `arr w/ 2 <- 10`是数组 `[0,1,10,3]` 。
- `arr w/ 0..2..3 <- [10,12]`是数组 `[10,1,12,3]` 。

#### <a name="copy-and-update-expressions-for-named-items"></a>已命名项的复制和更新表达式

对于用户定义类型中的命名项，存在类似的表达式。 

例如，请考虑类型 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
如果 `c` 包含类型的值 `Complex(1., -1.)` ，则 `c w/ Re <- 0.` 是类型的表达式， `Complex` 其计算结果为 `Complex(0., -1.)` 。

### <a name="jagged-arrays"></a>交错数组

交错数组（有时称为 "数组的数组"）是一个其元素为数组的数组。
交错数组的元素的大小可以不同。
下面的示例演示如何声明和初始化表示乘法表的交错数组。

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

### <a name="arrays-of-callables"></a>Callables 的数组 

还可以创建 callables 的数组。

* 如果公共元素类型是运算或函数类型，则所有元素必须具有相同的输入和输出类型。
* 数组的元素类型支持所有元素支持的任何[函子](xref:microsoft.quantum.guide.operationsfunctions)。
例如，如果 `Op1` 、 `Op2` 和 `Op3` 均为 `Qubit[] => Unit` 操作，但支持、 `Op1` 支持 `Adjoint` `Op2` `Controlled` 和 `Op3` 均支持：
  * `[Op1, Op2]`是一组 `(Qubit[] => Unit)` 操作。
  * `[Op1, Op3]`是一组 `(Qubit[] => Unit is Adj)` 操作。
  * `[Op2, Op3]`是一组 `(Qubit[] => Unit is Ctl)` 操作。

但是，尽管操作 `(Qubit[] => Unit is Adj)` 和 `(Qubit[] => Unit is Ctl)` 具有的通用基类型，但 `(Qubit[] => Unit)` 这些操作的*数组*不共享公共基类型。

例如， `[[Op1], [Op2]]` 当前将引发错误，因为它会尝试创建两个不兼容的数组类型和的 `(Qubit[] => Unit is Adj)[]` 数组 `(Qubit[] => Unit is Ctl)[]` 。

有关 callables 的详细信息，请参阅此页上的可[调用表达式](#callable-expressions)或[中 Q# 的操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="conditional-expressions"></a>条件表达式

假设有两个具有相同类型和布尔表达式的表达式，则使用问号、和竖线构成一个条件表达式 `?` `|` 。 `a==b ? c | d` `c` 如果为 true，则条件表达式的值为; 如果为 false，则为 `a==b` `d` 。

### <a name="conditional-expressions-with-callables"></a>带 callables 的条件表达式

条件表达式的计算结果可能为具有相同输入和输出但支持不同函子的操作。 在这种情况下，条件表达式的类型是一个操作，其输入和输出支持两个表达式支持的任何函子。
例如，如果、和都是，则支持、支持 `Op1` `Op2` `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` 和 `Op3` 均支持：

- `flag ? Op1 | Op2`为 `(Qubit[] => Unit)` 操作。
- `flag ? Op1 | Op3`为 `(Qubit[] => Unit is Adj)` 操作。
- `flag ? Op2 | Op3`为 `(Qubit[] => Unit is Ctl)` 操作。

如果两个可能的结果表达式中有一个包含函数或操作调用，则只会在该结果是调用值的情况下调用。 例如，在这种情况下 `a==b ? C(qs) | D(qs)` ，如果 `a==b` 为 true，则 `C` 调用操作，如果为 false，则只 `D` 调用操作。 此方法类似于其他语言的*短路*。

## <a name="callable-expressions"></a>可调用表达式

可调用的文本是编译范围中定义的操作或函数的名称。 例如， `X` 是引用标准库操作的操作文本 `X` ， `Message` 是引用标准库函数的函数文本 `Message` 。

如果操作支持 `Adjoint` 函子，则 `Adjoint op` 是操作表达式。
同样，如果操作支持 `Controlled` 函子，则 `Controlled op` 是操作表达式。
有关这些表达式的类型的详细信息，请参阅[调用操作专用](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)化。

`Adjoint` `Controlled` 除解包运算符和数组索引外，函子 (和) 绑定更严格于其他所有运算符 `!` `[ ]` 。
因此，以下所有操作都是有效的，前提是这些操作支持使用的函子：

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>类型参数化的可调用表达式

例如，可以将可调用文本作为值，将其分配给变量或将其传递给其他可调用的。 在这种情况下，如果可调用的具有[类型参数](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)，则必须提供作为可调用值一部分的参数。

可调用的值不能具有任何未指定的类型参数。 例如，如果 `Fun` 是具有签名的函数 `'T1->Unit` ：

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>可调用调用表达式

给定可调用的表达式 (操作或函数) 以及可调用的签名的输入类型的元组表达式，可以通过将元组表达式追加到可调用表达式来形成*调用表达式*。
调用表达式的类型是可调用的签名的输出类型。

例如，如果 `Op` 是具有签名的操作 `((Int, Qubit) => Double)` ， `Op(3, qubit1)` 则为类型的表达式 `Double` 。
同样，如果 `Sin` 是具有签名的函数 `(Double -> Double)` ， `Sin(0.1)` 则是类型的表达式 `Double` 。
最后，如果 `Builder` 是具有签名的函数 `(Int -> (Int -> Int))` ，则 `Builder(3)` 是从到的函数 `Int` `Int` 。

若要调用可调用值表达式的结果，需要在可调用的表达式前后使用一对括号。
因此，若要调用 `Builder` 上一段落中调用的结果，正确的语法为：

```qsharp
(Builder(3))(2)
```

调用[类型参数化](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)的可调用时，可以在可调用表达式后的尖括号中指定实际的类型参数 `< >` 。
此操作通常是不必要的，因为 Q# 编译器会推断实际类型。
但是，如果*未指定*类型参数化的参数，则此[部分应用程序](xref:microsoft.quantum.guide.operationsfunctions#partial-application)需要它。
在将具有不同函子支持的操作传递给可调用时，此方法也非常有用。

例如，如果具有签名，并具有签名， `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` 并 `Op3` 具有签名，则 `(Qubit[] => Unit)` `Func` 使用 `Op1` 作为第一个参数进行调用， `Op2` 并 `Op3` 将作为第二个参数进行调用，第三个参数为：

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

类型规范是必需的 `Op3` ，因为和 `Op1` 具有不同的类型，因此，如果没有规范，编译器会将此视为不明确的。


## <a name="operator-precedence"></a>运算符优先级

* 除了之外，所有二元运算符都是右结合运算符 `^` 。

* `[ ]`用于数组切片和索引的方括号，在任何运算符之前绑定。

* `Adjoint` `Controlled` 数组索引后，但在所有其他运算符之前，函子和绑定。

* 用于运算和函数调用的括号也绑定在任何运算符之前，但在数组索引和函子之后。

Q#按优先顺序排列的运算符，从高到低：

运算符 | 元 | 描述 | 操作数类型
---------|----------|---------|---------------
 加`!` | 一元 | 解包 | 任何用户定义类型
 `-`, `~~~`, `not` | 一元 | 数值负，按位求补，逻辑求反 | `Int`对于，为 `BigInt` 或 `Double` `-` `Int` `BigInt` `~~~` `Bool``not`
 `^` | 二进制 | 整数幂 | `Int`对于 `BigInt` 指数，为或 `Int`
 `/`, `*`, `%` | 二进制 | 除法、乘法、integer 模数 | `Int`对于 `BigInt` 、或 `Double` 为 `/` `*` `Int` `BigInt``%`
 `+`, `-` | 二进制 | 加法或 string 和 array 串联，减法 | `Int`、 `BigInt` 或 `Double` ，另外 `String` 或任何类型的数组类型`+`
 `<<<`, `>>>` | 二进制 | 左移、右移 | `Int` 或 `BigInt`
 `<`, `<=`, `>`, `>=` | 二进制 | 小于、小于或等于、大于、大于等于或等于比较的比较 | `Int`， `BigInt` 或`Double`
 `==`, `!=` | 二进制 | 相等，不等于比较 | 任何基元类型
 `&&&` | 二进制 | 位与 | `Int` 或 `BigInt`
 `^^^` | 二进制 | 按位“异或” | `Int` 或 `BigInt`
 <code>\|\|\|</code> | 二进制 | 按位“或” | `Int` 或 `BigInt`
 `and` | 二进制 | 逻辑与 | `Bool`
 `or` | 二进制 | 逻辑或 | `Bool`
 `..` | 二进制/三元 | 范围运算符 | `Int`
 `?` `|` | 三元 | 条件逻辑 | `Bool`对于左侧
`w/` `<-` | 三元 | 复制和更新 | 请参阅[复制和更新表达式](#copy-and-update-expressions)

## <a name="next-steps"></a>后续步骤

现在你可以使用中的表达式 Q# ，请转到[中 Q# 的操作和函数](xref:microsoft.quantum.guide.operationsfunctions)以了解如何定义和调用操作和函数。
