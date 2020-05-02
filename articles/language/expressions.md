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
# <a name="expressions"></a>表达式

## <a name="grouping"></a>分组

给定任意表达式，括在括号中的同一表达式是同一类型的表达式。
例如`(7)` ，是一个`Int`表达式， `([1,2,3])`是类型为的数组的表达式， `Int` `((1,2))`是类型`(Int, Int)`为的表达式。

[类型模型](xref:microsoft.quantum.language.type-model#tuple-types)中所述的简单值和单元素元组之间的等效性会消除`(6)`作为组和`(6)`作为单元素元组之间的多义性。

## <a name="symbols"></a>符号

绑定的符号或赋给类型`'T`的值的名称是类型`'T`的表达式。
例如，如果符号`count`绑定到整数值`5`，则`count`是整数表达式。

## <a name="numeric-expressions"></a>数值表达式

数值表达式是、 `Int` `BigInt`或`Double`类型的表达式。
也就是说，它们是整数或浮点数。

`Int`Q # 中的文本与 c # 中的整数文本相同，不同之处在于不需要尾随 "l" 或 "L" （或允许）。
十六进制和二进制整数分别支持 "0x" 和 "0b" 前缀。

`BigInt`Q # 中的文本与 .NET 中的大整数字符串相同，尾随 "l" 或 "L"。
支持使用 "0x" 前缀的十六进制大整数。
因此，以下是`BigInt`文本的有效用法：

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`Q # 中的文本与 c # 中的 double 文本相同，只不过不需要尾随 "d" 或 "D" （或允许）。

给定任意元素类型的数组表达式，可以使用`Int` `Length`内置函数，使用括在括号中的数组表达式`(`和`)`来构造表达式。
例如，如果`a`绑定到数组，则`Length(a)`是整数表达式。
如果`b`是`Int[][]`整数数组的数组， `Length(b)`则为中`b`的子数组的数目， `Length(b[1])`是中`b`第二个子数组中的整数的数目。

假设两个数值表达式具有相同的类型，则可以`+`使用`-`二元`*`运算符、 `/` 、和形成新的数值表达式。
新表达式的类型将与构成表达式的类型相同。

假设有两个整数表达式，二元`^`运算符（power）可用于构成新的整数表达式。
同样， `^`可以使用两个双表达式来形成新的双精度表达式。
最后， `^`可与左侧的大整数一起使用，并在右侧使用一个整数来形成新的大整数表达式。
在这种情况下，第二个参数必须适合32位;否则，将引发运行时错误。

假设有`%`两个整数或大整数表达式，可以使用（取模）、 `&&&` （位与）、 `|||` （位或）或`^^^` （位 XOR）运算符来形成新的整数或大整数表达式。

给定左侧的整数或大整数表达式，并在右侧输入整数表达式，则`<<<`可以使用（算术左移位）或`>>>` （算术右移位）运算符来创建与左侧表达式具有相同类型的新表达式。

转换操作的第二个参数（移位量）必须大于或等于零;负移位量的行为是不确定的。
移位运算的移位量还必须适合32位;否则，将引发运行时错误。
如果要移位的数字是整数，则会解释`mod 64`移位量;也就是说，1和65的移位都具有相同的效果。

对于整数和大整数值，移位均为算术运算。
向左或向右移位负值将导致负数。
也就是说，向左或向右移动一个步骤的方式与2的乘法或除法完全相同。

对于负数，整数除法和整数取模的行为与 c # 的行为相同。
也就是说， `a % b`将始终具有相同的符号`a`，并`b * (a / b) + a % b`始终相等。 `a`
例如：

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

大整数除法和取模的工作方式相同。

如果给定了数值表达式，则可以使用`-`一元运算符构造新的表达式。
新表达式将与构成表达式的类型相同。

给定任意整数或大整数表达式时，可以使用`~~~` （按位求补）一元运算符来构造相同类型的新表达式。

## <a name="boolean-expressions"></a>布尔表达式

这两`Bool`个文本值`true`为`false`和。

给定任意两个具有相同基元类型的表达式， `==`和`!=`二元运算符可用于构造`Bool`表达式。
如果两个表达式相等，则表达式将为 true; 否则为 false。

不能比较用户定义类型的值，只能比较它们的解包值。 例如，使用 "解包" 运算符`!` （在 " [Q # 类型模型" 页](xref:microsoft.quantum.language.type-model#user-defined-types)中介绍），

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

值的`Qubit`相等比较是恒等的;也就是说，这两个表达式是否标识同一 qubit。
这两个 qubits 的状态不会进行比较、访问、度量或修改。

由于舍入`Double`效果，值的相等比较可能会产生误导。
例如， `49.0 * (1.0/49.0) != 1.0`。

给定任意两个数值表达式，二元运算符`>`、 `<` `>=`、和`<=`可用于构造新的布尔表达式，如果第一个表达式分别大于、小于、大于或等于，或者小于或等于第二个表达式，则该值为 true。

给定任意两个布尔表达式， `and`和`or`二元运算符可用于构造新的布尔表达式，如果这两个表达式都为 true，则这两个表达式均为 true。

给定任何布尔表达式， `not`一元运算符可用于构造新的布尔表达式，如果构成表达式为 false，则为 true。

## <a name="string-expressions"></a>字符串表达式

Q # 允许在`fail`语句和`Log`标准函数中使用字符串。

Q # 中的字符串是文本或内插字符串。
字符串文本类似于大多数语言中的简单字符串文本：括在双引号中的 Unicode 字符序列`"`。
在字符串中， `\`反斜杠字符可用于转义双引号字符，还可以将新行作为`\n`、回车符`\r`和制表符插入到中。 `\t`
例如：

```qsharp
"\"Hello world!\", she said.\n"
```

字符串内插的 Q # 语法是 c # 7.0 语法的子集;Q # 不支持逐字（多行）内插字符串。
请参阅 c # 语法的内[*插字符串*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。

内插字符串中的表达式遵循 Q # 语法，而不是 c # 语法。
任何有效的 Q # 表达式都可以出现在内插字符串中。

## <a name="qubit-expressions"></a>Qubit 表达式

唯一`Qubit`的表达式是绑定到`Qubit`数组的`Qubit`值或数组元素的符号。
没有`Qubit`文本。

## <a name="pauli-expressions"></a>Pauli 表达式

四个`Pauli`值（ `PauliI`、 `PauliX` `PauliY`、和`PauliZ`）都是有效`Pauli`的表达式。

除了这样，唯一`Pauli`的表达式是绑定到`Pauli`数组的`Pauli`值或数组元素的符号。

## <a name="result-expressions"></a>结果表达式

和都是有效`Result`的表达式。 `Zero` `Result` `One`

除了这样，唯一`Result`的表达式是绑定到`Result`数组的`Result`值或数组元素的符号。
特别要注意的`One`是，与整数`1`不同，它们之间没有直接转换。
对于`Zero`和`0`也是如此。

## <a name="range-expressions"></a>范围表达式

给定任意三`Int`个`start`表达式`step`，和`stop` `start .. step .. stop`是一个范围表达式，其第一个元素`start`是，第二`start+step`个元素是， `start+step+step`第三个元素为`stop` ，依此类推，直到传递。
例如， `step`如果为正值，则范围可能为空`stop < start`。
如果`stop`与之间`start`的差异是的`stop` `step`整数倍数，则范围的最后一个元素将为;也就是说，范围两端都包含。

给定任意两`Int`个`start`表达式`stop`和`start .. stop` ，是等于的范围表达式`start .. 1 .. stop`。
请注意，即使`step`小于`stop` ，隐含也是 + 1 `start`;在这种情况下，该范围为空。

一些示例范围如下：

- `1..3`的范围为1、2、3。
- `2..2..5`范围为2、4。
- `2..2..6`范围为2、4、6。
- `6..-2..2`范围为6、4、2。
- `2..1`为空范围。
- `2..6..7`范围为2。
- `2..2..1`为空范围。
- `1..-1..2`为空范围。

## <a name="callable-expressions"></a>可调用表达式

可调用的文本是编译范围中定义的操作或函数的名称。
例如， `X`是引用标准库`X`操作的操作文本， `Message`是引用标准库`Message`函数的函数文本。

如果操作支持`Adjoint`函子，则`Adjoint op`是操作表达式。
同样，如果操作支持`Controlled`函子，则`Controlled op`是操作表达式。
这些表达式的类型在[函子](xref:microsoft.quantum.language.type-model#functors)中指定。

除解`Adjoint`包`Controlled`运算符`!`和数组索引外，函子（和）与`[]`其他所有运算符更紧密地绑定。
因此，以下各项均为合法，前提是这些操作支持使用的函子：

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

可调用的文本可用作值，假设要分配给变量或传递给其他可调用的。
在这种情况下，如果可调用的具有类型参数，则必须将它们作为可调用值的一部分提供。
可调用的值不能具有任何未指定的类型参数。

例如，如果`Fun`是具有签名`'T1->Unit`的函数：

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>可调用调用表达式

给定可调用（操作或函数）表达式和可调用签名的输入类型的元组表达式时，可以通过将元组表达式追加到可调用表达式来形成调用表达式。
调用表达式的类型是可调用的签名的输出类型。

例如， `Op`如果是具有`((Int, Qubit) => Double)`签名的操作， `Op(3, qubit1)`则为类型`Double`的表达式。
同样，如果`Sin`是具有签名`(Double -> Double)`的函数， `Sin(0.1)`则是类型`Double`的表达式。
最后，如果`Builder`是具有签名`(Int -> (Int -> Int))`的函数，则`Builder(3)`是从到 Int 的函数。

若要调用可调用值表达式的结果，需要在可调用的表达式前后使用一对括号。
因此，若要调用上一段落`Builder`中调用的结果，正确的语法为：

```qsharp
(Builder(3))(2)
```

调用类型参数化的可调用时，可以在尖括号`<`和`>`可调用表达式之后指定实际的类型参数。
这通常是不必要的，因为 Q # 编译器将推断实际类型。
如果未指定类型参数化的参数，则此参数对于部分应用程序是必需的（见下文）。
在将具有不同函子支持的操作传递给可调用时，有时也很有用。

`Func`例如，如果具有签名`('T1, 'T2, 'T1) -> 'T2`， `Op1`并`Op2` `(Qubit[] => Unit is Adj)`具有签名，并`Op3`具有签名`(Qubit[] => Unit)`，则将使用`Func` `Op1`作为第一个参数进行调用`Op2` ，并`Op3`将作为第二个参数，第三个参数为：

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

类型规范是必需的， `Op3`因为`Op1`和具有不同的类型，因此，如果没有规范，编译器会将此视为不明确的。

### <a name="partial-application"></a>部分应用程序

给定可调用的表达式，可以通过向可调用的参数提供一个子集来创建新的可调用的。
这称为_部分应用程序_。

在 Q # 中，部分应用的可调用通过编写常规调用表达式来表示，但对于未指定`_`的参数使用下划线。
生成的可调用与基可调用的结果类型相同，并且具有相同的操作专用化。
部分应用程序的输入类型只是删除了指定参数的原始类型。

如果在创建部分应用程序时将可变变量作为指定参数传递，则使用该变量的当前值。
此后更改变量的值不会影响部分应用程序。

例如，如果`Op`具有类型`((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`：

- `Op(5,(_,_))`具有类型`(((Qubit,Qubit), Double) => Unit is Adj)`，因此具有`Op(5,_)`。
- `Op(_,(_,1.0))` 的类型为 `((Int, (Qubit,Qubit)) => Unit is Adj)`。
- `Op(_,((q1,q2),_))` 的类型为 `((Int,Double) => Unit is Adj)`。
   请注意，我们已在此处应用了单一元组等效性。

如果部分应用的可调用具有编译器无法推断的类型参数，则这些参数必须在调用站点提供。
部分应用程序不能具有任何未指定的类型参数。

例如，如果`Op`具有类型`(('T1, Qubit, 'T1) => Unit : Adjoint)`：

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>递归

Q # callables 允许直接或间接递归。
也就是说，操作或函数可能调用自身，或者它可能调用直接或间接调用可调用操作的另一个可调用的。

不过，有两个关于递归使用的重要说明：

- 在操作中使用递归可能会干扰某些优化。
  这可能会对算法的执行时间产生重大影响。
- 在实际的量程设备上执行时，堆栈空间可能会受到限制，因此深度递归可能导致运行时错误。
  特别是，Q # 编译器和运行时不标识和优化尾递归。

## <a name="tuple-expressions"></a>元组表达式

元组文本是一系列以逗号分隔的合适类型的元素表达式，括在和`(` `)`中。
例如， `(1, One)`是一个`(Int, Result)`表达式。

除了文本以外，唯一的元组表达式是绑定到元组值、元组数组的数组元素和返回元组的可调用调用的符号。

## <a name="user-defined-type-expressions"></a>用户定义的类型表达式

用户定义类型的文本包含类型名称，后跟类型的基元组类型的元组文本。
例如，如果`IntPair`是基于的用户定义类型`(Int, Int)`，则`IntPair(2,3)`是该类型的有效文本。

除了文本以外，用户定义类型的唯一表达式是绑定到该类型的值、该类型的数组元素和返回该类型的可调用调用的符号。

## <a name="unwrap-expressions"></a>解包表达式

在 Q # 中，解包运算符是一个尾随引号`!`。
例如，如果`IntPair`是具有`(Int, Int)`基础类型的用户定义类型，并且`s`是具有值`IntPair(2,3)`的变量，则`s!`将为。 `(2,3)`

对于根据其他用户定义类型定义的用户定义类型。 可以重复解包运算符;例如， `s!!`指示的双重解包值`s`。
因此，如果`WrappedPair`是具有基础类型`IntPair` `t`的用户定义类型，并且是具有值`WrappedPair(IntPair(1,2))`的变量，则`t!!`将为。 `(1,2)`

`!`运算符的优先级高于除数组索引和切片以外`[]`的其他所有运算符。
`!`并`[]`绑定按位置;也就是说， `a[i]![3]`应如下所示`((a[i])!)[3]`：取`i`的第一个`a`元素，将其解包，然后获取解包值（必须是数组）的第3个元素。

`!`运算符的优先级有一个可能不明显的影响。
如果函数或操作返回一个值，则该函数或操作调用必须括在括号中，以便参数元组绑定到该调用，而不是绑定到解包。
例如：

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>数组表达式

数组文字是由`[`和`]`括起来的由逗号分隔的一个或多个元素表达式的序列。
所有元素都必须兼容同一类型。

如果公共元素类型是运算或函数类型，则所有元素必须具有相同的输入和输出类型。
数组的元素类型将支持所有元素支持的任何函子。
`Op1`例如，如果、 `Op2`和`Op3`都是`Qubit[] => Unit`， `Op1` `Adjoint` `Op2` `Controlled`则支持、支持和`Op3`均支持：

- `[Op1, Op2]`是一组`(Qubit[] => Unit)`操作。
- `[Op1, Op3]`是一组`(Qubit[] => Unit is Adj)`操作。
- `[Op2, Op3]`是一组`(Qubit[] => Unit is Ctl)`操作。

不允许空数组`[]`文本。
而是`new ★[0]`使用， `★`其中作为适当类型的占位符，允许创建长度为零的所需数组。

如果给定两个相同类型的数组，则`+`可以使用二元运算符形成一个新数组，该数组是两个数组的串联。
例如， `[1,2,3] + [4,5,6]`为`[1,2,3,4,5,6]`。

### <a name="array-creation"></a>数组创建

给定类型和`Int`表达式后， `new`运算符可用于分配给定大小的新数组。
例如， `new Int[i+1]`将使用`Int` `i+1`元素分配新数组。

新数组的元素被初始化为依赖于类型的默认值。
在大多数情况下，这是零的一些变体。

对于引用实体的 qubits 和 callables，没有合理的默认值。
因此，对于这些类型，默认值是无效的引用，不能使用而不会导致运行时错误。
这类似于 c # 或 Java 等语言的空引用。
必须使用非默认值正确地初始化包含 qubits 或 callables 的数组，才能安全地使用其元素。 可在中找到合适的<xref:microsoft.quantum.arrays>初始化例程。

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

元组类型是逐个元素初始化的。


### <a name="jagged-arrays"></a>交错数组

交错数组，有时称为 "数组数组"，是元素为数组的数组。 交错数组的元素的大小可以不同。 下面的示例演示如何声明和初始化表示乘法表的交错数组。

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


### <a name="array-slices"></a>数组切片

给定数组表达式和`Range`表达式时，可以使用`[`和`]`数组切片运算符构造一个新的表达式。
新表达式将与数组的类型相同，并将包含由的`Range`元素编制索引的数组项（按定义的顺序）。 `Range`
例如， `a`如果绑定到的`Double`数组，则`a[3..-1..0]`是一个`Double[]`表达式，该表达式包含的`a`前四个元素，但其显示顺序与中的顺序相反。 `a`

如果`Range`为空，则生成的数组切片长度为零。

如果数组表达式不是简单的标识符，则必须将其括在括号中，以便进行切片。
例如，如果`a`和`b`都是的`Int`数组，则串联的切片将表示为：

```qsharp
(a+b)[1..2..7]
```

Q # 中的所有数组都是从零开始的。
也就是说，数组`a`的第一个元素始终`a[0]`为。

从0.8 版本开始，我们支持范围切片的上下文表达式。 具体而言，范围切片表达式的上下文中可能会省略范围起始值和结束值。 在这种情况下，编译器将应用以下规则来推导范围的预期分隔符。 

例如，如果省略范围起始值，则推断出的起始值 
- 如果未指定步骤或指定步骤为正值，则为零; 
- 如果指定的步骤为负，则为切片的数组的长度减去1。 

如果省略范围结束值，则推断出的结束值 
- 如果未指定步骤或指定步骤为正值，则切片数组的长度减1 
- 如果指定的步骤为负数，则为零。 

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

## <a name="array-element-expressions"></a>数组元素表达式

给定数组表达式和`Int`表达式时，可以使用`[`和`]`数组元素运算符构造一个新的表达式。
新表达式将与数组的元素类型相同。
例如， `a`如果绑定到`Double`的数组，则`a[4]`是一个`Double`表达式。

如果数组表达式不是简单的标识符，则必须将其括在括号中，以便选择一个元素。
例如，如果`a`和`b`都是的`Int`数组，则连接中的元素将表示为：

```qsharp
(a+b)[13]
```

Q # 中的所有数组都是从零开始的。
也就是说，数组`a`的第一个元素始终`a[0]`为。


## <a name="copy-and-update-expressions"></a>复制和更新表达式

可以通过复制和更新表达式从现有阵列创建新的阵列。
复制和更新表达式是窗`expression1 w/ expression2 <- expression3`体的表达式，其中`expression1`必须是某种类型`T[]` `T`的类型。 第二`expression2`个定义要修改的元素的索引，该索引与中`expression1`的数组进行比较，并且必须是类型的`Int`类型或`Range`。 如果`expression2`的类型`Int`为， `expression3`则必须为类型`T`。 如果`expression2`的类型`Range`为， `expression3`则必须为类型`T[]`。

复制`arr w/ idx <- value`和更新表达式构造一个新数组，其中所有元素都设置为中`arr`的相应元素，但中的元素除外`idx`，后者设置为中`value`的一个。 例如，如果`arr`包含一个数组`[0,1,2,3]`，则 
- `arr w/ 0 <- 10`是数组`[10,1,2,3]`。
- `arr w/ 2 <- 10`是数组`[0,1,10,3]`。
- `arr w/ 0..2..3 <- [10,12]`是数组`[10,1,12,3]`。

对于用户定义类型中的命名项，存在类似的表达式。 例如，请考虑类型 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
如果`c`包含类型`Complex(1.,-1.)`的值，则`c w/ Re <- 0.`是类型`Complex`的表达式，其计算结果为`Complex(0.,-1.)`。

## <a name="conditional-expressions"></a>条件表达式

假设有两个具有相同类型和布尔表达式的其他表达式，则可以使用问号`?`和竖线构造条件表达式。 `|`
例如， `a==b ? c | d`。
在此示例中，如果`c` `a==b`为 true， `d`则条件表达式的值为; 如果为 false，则为。

这两个表达式的计算结果可能为具有相同输入和输出但支持不同函子的操作。
在这种情况下，条件表达式的类型是一个操作，其中包含支持两个表达式支持的任何函子的输入和输出。
`Op1`例如，如果、 `Op2`和`Op3`都是`Qubit[]=>Unit`， `Op1` `Adjoint` `Op2` `Controlled`则支持、支持和`Op3`均支持：

- `flag ? Op1 | Op2`为`(Qubit[] => Unit)`操作。
- `flag ? Op1 | Op3`为`(Qubit[] => Unit is Adj)`操作。
- `flag ? Op2 | Op3`为`(Qubit[] => Unit is Ctl)`操作。

如果两个可能的结果表达式中有一个包含函数或操作调用，则只会在该结果是调用的值时进行调用。
例如，在这种情况`a==b ? C(qs) | D(qs)`下， `a==b`如果为 true， `C`则将调用操作，如果为 false，则只`D`调用。
这类似于其他语言的短路。


## <a name="operator-precedence"></a>运算符优先级

除了之外，所有二元运算符都是右结合`^`运算符。

`[`对于数组切片和索引，请在任何运算符之前`]`绑定。

数组索引`Adjoint`后`Controlled` ，但在所有其他运算符之前，函子和绑定。

用于运算和函数调用的括号也绑定在任何运算符之前，但在数组索引和函子之后。

按优先顺序排列的运算符，从高到低：

操作员 | 元 | 说明 | 操作数类型
---------|----------|---------|---------------
 加`!` | 一元 | 解包 | 任何用户定义类型
 `-`, `~~~`, `not` | 一元 | 数值负，按位求补，逻辑求反 | `Int`对于`BigInt` ， `Double`为`-`或`Int` `BigInt` `~~~` `Bool``not`
 `^` | Binary | 整数幂 | `Int`对于`BigInt`指数， `Int`为或
 `/`, `*`, `%` | Binary | 除法、乘法、integer 模数 | `Int``Double` `BigInt` `*`对于`Int`或为`/` `BigInt``%`
 `+`, `-` | Binary | 加法或 string 和 array 串联，减法 | `Int`、 `BigInt`或`Double`，另外`String`或任何类型的数组类型`+`
 `<<<`, `>>>` | Binary | 左移、右移 | `Int` 或 `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | 小于、小于或等于、大于、大于等于或等于比较的比较 | `Int`， `BigInt`或`Double`
 `==`, `!=` | Binary | 相等，不等于比较 | 任何基元类型
 `&&&` | Binary | 位与 | `Int` 或 `BigInt`
 `^^^` | Binary | 按位“异或” | `Int` 或 `BigInt`
 <code>\|\|\|</code> | Binary | 按位“或” | `Int` 或 `BigInt`
 `and` | Binary | 逻辑与 | `Bool`
 `or` | Binary | 逻辑或 | `Bool`
 `..` | 二进制/三元 | 范围运算符 | `Int`
 `?` `|` | 三元 | 条件逻辑 | `Bool`对于左侧
`w/` `<-` | 三元 | 复制和更新 | 请参阅[复制和更新表达式](#copy-and-update-expressions)
