---
title: 'Q # 语句 |Microsoft Docs'
description: 'Q # 语句'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9157cf3336ce0894816dbfbaf13ce0e712a6b096
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821059"
---
# <a name="statements-and-other-constructs"></a>语句和其他构造

## <a name="comments"></a>注释

注释以两个正斜杠（`//`）开头，并继续到行尾。
注释可以出现在 Q # 源文件中的任何位置。

### <a name="documentation-comments"></a>文档注释

当编译器在命名空间、操作、专用化、函数或类型定义紧靠前出现时，编译器会对以第三个正斜杠（`///`）开头的注释进行专门处理。
在这种情况下，它们的内容将作为定义的可调用或用户定义类型的文档，如其他 .NET 语言所示。

在 `///` 注释中，作为 API 文档一部分显示的文本格式设置为[Markdown](https://daringfireball.net/projects/markdown/syntax)，并且特殊命名的标头所指示的文档的不同部分。
作为 Markdown 的扩展，可以使用 `@"<ref target>"`包含 Q # 中对操作、函数和用户定义类型的交叉引用，其中 `<ref target>` 替换为所引用的代码对象的完全限定名称。
文档引擎也可以选择支持其他 Markdown 扩展。

例如：

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

以下名称被识别为文档注释标头。

- **摘要**：函数或操作行为或类型用途的简短摘要。 摘要的第一个段落用于悬停信息。 它应为纯文本。
- **说明**：对函数或操作的行为或类型用途的说明。 摘要和描述连接起来，以形成函数、操作或类型生成的文档文件。
  描述可以包含行内 LaTeX 格式的符号和公式。
- **输入**：对操作或函数的输入元组的说明。
  可以包含其他 Markdown 子节，指示输入元组的每个单独元素。
- **输出**：操作或函数返回的元组的说明。
- **类型参数**：一个空节，其中每个泛型类型参数包含一个附加子节。
- **示例**：操作、函数或类型正在使用的简短示例。
- **备注**：其他 prose，描述操作、函数或类型的某个方面。
- **另请参阅**：表示相关函数、操作或用户定义类型的完全限定名称的列表。
- **引用**：要记录的项的引用和引文的列表。

## <a name="namespaces"></a>命名空间

每个 Q # 操作、函数和用户定义的类型都是在命名空间中定义的。
Q # 遵循的规则与其他 .NET 语言相同。
但是，Q # 不支持对命名空间进行相对引用。
也就是说，如果已打开命名空间 `a.b`，则不会将对操作名称 `c.d` 的引用解析为具有完整名称 `a.b.c.d`的操作。

在命名空间块中，可以使用 `open` 指令导入在某个命名空间中声明的所有类型和 callables，并按其非限定名称引用它们。 （可选）可定义已打开命名空间的短名称，使来自该命名空间的所有元素都可以（并且需要）由定义的短名称限定。 `open` 指令适用于文件中的整个命名空间块。

在当前命名空间中未打开的其他命名空间中定义的类型或可调用必须由其完全限定名称引用。
例如，除非之前在当前块中打开了 `X.Y` 命名空间，否则 `X.Y` 命名空间中名为 `Op` 的操作必须由其完全限定名称 `X.Y.Op`引用。 如上所述，即使已打开 `X` 命名空间，也无法 `Y.Op`中引用操作。
如果在该命名空间和文件中定义了 `X.Y` 的短名称 `Z`，则 `Op` 需要称为 `Z.Op`。 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

通常，最好通过使用 `open` 指令来包含命名空间。
如果两个命名空间定义具有相同名称的构造，并且当前源使用两者中的构造，则需要使用完全限定的名称。

## <a name="formatting"></a>格式设置

大多数 Q # 语句和指令以终止分号 `;`结束。
语句和声明（如 `for` 和以语句块结尾的 `operation`）不需要终止分号。
每个语句说明都说明终止分号是否是必需的。

语句（如表达式、声明和指令）可以跨多行进行划分。
应避免在单个行上包含多个语句。

## <a name="statement-blocks"></a>语句块

Q # 语句分组为语句块。
语句块以开始 `{` 开始，以结束 `}`结束。

在词法上包含在另一个块内的语句块被视为包含块的子块;包含和子块也称为外部和内部块。

## <a name="symbol-binding-and-assignment"></a>符号绑定和赋值

Q # 区分可变和不可变符号。
通常，建议使用不可变符号，因为它允许编译器执行更多优化。

绑定的左侧包含一个符号元组和一个表达式的右端。

由于所有 Q # 类型都是值类型-如果 qubits 采用特殊的角色，则在将值绑定到符号或重新绑定符号时，会创建 "copy"。 也就是说，Q # 的行为与在分配时创建副本的行为相同。 这特别包括数组。 当然，实际上只需根据需要重新创建相关的部分。 

### <a name="tuple-deconstruction"></a>元组析构

如果绑定的右侧是一个元组，则该元组可能在赋值时是析构的。
此类 deconstructions 可能涉及嵌套元组，只要右侧的元组形状与符号元组的形状兼容，所有完整或部分析构都有效。
当 `=` 的右侧是元组值表达式时，也可以使用元组析构。

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>不可变符号

使用 `let` 语句绑定不可变符号。
这大致相当于语言（例如C#）中的变量声明和初始化，但 Q # 符号一旦绑定后可能不会更改;`let` 绑定是不可变的。

不可变绑定包含关键字 `let`，后跟符号或符号元组、等号 `=`、将符号绑定到的表达式和终止分号。
绑定符号的类型是根据右侧的表达式推断出来的。

### <a name="mutable-symbols"></a>可变符号

可变符号使用 `mutable` 语句进行定义和初始化。
作为 `mutable` 语句的一部分声明和绑定的符号可能会在后面的代码中重新绑定到不同的值。 

可变绑定语句包含关键字 `mutable`，后跟符号或符号元组、等号 `=`、将符号绑定到的表达式和终止分号。
绑定符号的类型是根据右侧的表达式推断出来的。 如果稍后在代码中重新绑定符号，则其类型不会更改，并且绑定值需要与该类型兼容。

### <a name="rebinding-of-mutable-symbols"></a>重新绑定可变符号

可以使用 `set` 语句重新绑定可变变量。
这种重新绑定包含关键字 `set`，后跟符号或符号元组、等号 `=`、将符号重新绑定到的表达式和终止分号。
该值必须与它所绑定到的符号的类型兼容。

#### <a name="apply-and-reassign-statement"></a>应用和重新分配语句

如果右侧包含二元运算符的应用程序，并将结果重新绑定到运算符的左侧参数，则称为 "应用" 和 "重新分配" 语句的一种特殊的 set 语句。 例如，
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
递增 `for` 循环的每次迭代中的计数器 `counter` 的值。 上述代码等效于 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
类似的语句可用于所有的二元运算符，其中左侧的类型与表达式类型匹配。 这为示例提供了一种简单的方法来累积值：
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>更新和重新分配语句

在右侧的复制和更新表达式中存在类似的连接。 相应地，对于用户定义的类型中的命名项以及数组项，都存在更新和重新分配语句。  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ElementwisePlus(reals : Double[], ims : Double[]) : Complex[] {
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

对于数组，我们的标准库包含用于许多常见数组初始化和操作需求的必需工具，因此有助于避免第一次更新数组项。 如果需要，更新和重新分配语句提供了一种替代方法：

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

> [!TIP]   
> 通过利用 <xref:microsoft.quantum.arrays>中提供的工具，避免不必要地使用 update 和重新分配语句。

函数
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
例如，可以简单地使用 `Microsoft.Quantum.Arrays`中的函数 `ConstantArray`，并返回一个复制和更新表达式：

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a>绑定范围

通常，符号绑定超出范围，并且在中出现的语句块的末尾变为不起作用。
此规则有两种例外情况：

- `for` 循环的循环变量的绑定处于 for 循环主体的范围内，而不是在循环结束后。
- `repeat`/`until` 循环的所有三个部分（正文、测试和修正）都被视为单个作用域，因此，在正文中绑定的符号可用于测试和修复中。

对于这两种类型的循环，每次循环都在其自己的作用域中执行，因此更早传递中的绑定在稍后的传递中不可用。

来自外部块的符号绑定由内部块继承。
一个符号只能绑定每个块一次;定义与作用域中的另一个符号名称相同（无 "隐藏"）的符号是非法的。
以下顺序是合法的：

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

和

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
```

但这是非法的：

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

如下所示：

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a>控制流

### <a name="for-loop"></a>For 循环

`for` 语句支持对整数范围或数组进行迭代。
语句由关键字 `for`、左括号 `(`、符号或符号元组、关键字 `in`、类型 `Range` 或数组的表达式、右括号 `)`和语句块组成。

语句块（循环的主体）将重复执行，其中定义的符号（即循环变量）绑定到范围或数组中的每个值。
请注意，如果范围表达式的计算结果为空范围或数组，则不会执行主体。
在进入循环之前，将完全计算该表达式，并且在执行循环时不会更改。

声明的符号的绑定是不可变的，并且与其他变量绑定遵循相同的规则。 特别是，在赋值给循环变量时，可能会销毁数组，例如，在数组上循环的数组项。

例如，

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

循环变量绑定到循环体的每个入口，并在主体末尾解除绑定。
具体而言，for 循环完成后不会绑定循环变量。

### <a name="repeat-until-success-loop"></a>重复执行-成功循环

`repeat` 语句支持量程 "重复到成功" 模式。
它包含关键字 `repeat`，后跟语句块（_循环体_）、关键字 `until`、布尔表达式、终止分号或关键字 `fixup` 后跟另一个语句块（_修正_）。
循环体、condition 和修正均视为单个作用域，因此，在主体中绑定的符号可用于条件和修正。

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

执行循环体，然后计算条件。
如果条件为 true，则语句已完成;否则，将执行修正，并从循环体开始重新执行该语句。
请注意，完成修正的执行将结束语句的范围，以便在正文或修正范围内进行的符号绑定在后续的重复项中不可用。

例如，下面的代码是一种概率线路，可使用 Hadamard 和 T 入口 $V _3 = （\boldone + 2 i Z）/\sqrt{5}$。
循环在 $ \frac 中终止，{8}平均 {5}$ 重复。
有关详细信息，请参阅[*重复截止时间：单 qubit unitaries 的非确定性分解*](https://arxiv.org/abs/1311.1074)（Paetznick 和 Svore，2014）。

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

> [!TIP]   
> 避免在函数内使用重复-until 循环。 当函数中的循环时，将提供相应的功能。 

### <a name="while-loop"></a>While 循环

重复-直到成功模式有一个非常特定于量程的内涵。 它们广泛用于特定的量程算法类，因此，它是 Q # 中的专用语言构造。 但是，在编译时，需要在量程运行时中特别小心地处理基于某个条件、其执行长度未知的循环。 另一方面，它们在函数中的使用是 unproblematic 的，因为它们仅包含将在常规（非量程）硬件上执行的代码。 

因此，Q # 支持仅在函数内使用 while 循环。 `while` 语句由关键字 `while`、左括号 `(`、条件（即布尔表达式）、右括号 `)`和语句块组成。
只要条件的计算结果为 `true`，就会执行语句块（循环的主体）。

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>条件语句

`if` 语句支持条件执行。
它包含关键字 `if`、左括号 `(`、布尔表达式、右括号 `)`和语句块（ _then_块）。
这可能后跟任意数量的 else if 子句，其中每个子句都由关键字 `elif`、左括号 `(`、布尔表达式、右括号 `)`和语句块（ _else-if_块）组成。
最后，语句可选择使用 else 子句完成，后者由关键字 `else` 后跟另一个语句块（ _else_块）组成。
计算条件，如果该条件为 true，则执行 then 块。
如果条件为 false，则计算第一个 else if 条件;如果为 true，则执行此 else-if block。
否则，将测试第二个 else-if 块，然后是第三个块，依此类推，直到遇到具有 true 条件的子句或没有其他的 else 子句。
如果原始 if 条件和所有 else-if 子句的计算结果为 false，则在提供时将执行 else 块。

请注意，执行的任何块在其自己的作用域中执行。
在 if 语句结束后，在 then、else 或 else 块内进行的绑定将不可见。

例如，

```qsharp
if (result == One) {
    X(target);
} 
```

或

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>返回

Return 语句结束操作或函数的执行，并将值返回给调用方。
它包含关键字 `return`，后跟适当类型的表达式和终止分号。

返回空元组 `()`的可调用不需要 return 语句。
如果需要提前退出，可在这种情况下使用 `return ()`。
返回任何其他类型的 Callables 需要最终的 return 语句。

操作中不存在最大返回语句数。
如果语句在块内跟随 return 语句，则编译器可能会发出警告。

例如，

```qsharp
return 1;
```

或

```qsharp
return ();
```

或

```qsharp
return (results, qubits);
```

### <a name="fail"></a>失败

Fail 语句结束操作的执行，并将错误值返回给调用方。
它由关键字 `fail`组成，后跟一个字符串和一个终止分号。
该字符串返回到传统驱动程序作为错误消息。

操作中的 fail 语句数量没有限制。
如果语句在块中跟随 fail 语句，则编译器可能会发出警告。

例如，

```qsharp
fail $"Impossible state reached";
```

或

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Qubit 管理

请注意，函数的主体内不允许使用这些语句。
它们仅在操作内有效。

### <a name="clean-qubits"></a>清理 Qubits

`using` 语句用于获取要在语句块中使用的新 qubits。
Qubits 可以确保初始化为计算 `Zero` 状态。
Qubits 应处于语句块末尾的计算 `Zero` 状态;鼓励模拟器强制实施此要求。

语句包含关键字 `using`，后跟左括号 `(`、绑定、右括号 `)`和 qubits 将在其中可用的语句块。
绑定遵循与 `let` 语句相同的模式：单个符号或符号的元组，后跟一个等号 `=`，一个值或匹配项的匹配元组。
初始值设定项可用于单个 qubit，指示为 `Qubit()`或 qubits 数组，由 `Qubit[`、`Int` 表达式和 `]`指示。

例如，

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a>借用 Qubits

`borrowing` 语句用于获取临时使用的 qubits。 语句包含关键字 `borrowing`，后跟左括号 `(`、绑定、右括号 `)`和 qubits 将在其中可用的语句块。
绑定遵循的模式和规则与 `using` 语句中的相同。

例如，

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

借 qubits 处于未知状态，在语句块结束时超出范围。
借款人提交 qubits，使其在其被借用时处于相同状态，即，它们在语句块开始和结束时的状态应相同。
此状态特别不一定是经典状态，因此在大多数情况下，借款范围不应包含度量值。 

有关借用 Svore 使用的示例，请参阅[*使用 2n + 2 qubits 与基于 Toffoli 的模块乘法*](https://arxiv.org/abs/1611.07995)（Haner、Roetteler 和 qubit 2017）进行分解。

借用 qubits 时，系统将首先尝试填写正在使用的 qubits 中的请求，但不会在 `borrowing` 语句的主体中访问该请求。
如果没有足够的 qubits，则它将分配新的 qubits 来完成请求。

## <a name="conjugations"></a>语态

与传统位相比，释放量程内存会稍微增加一点，因为在 qubits 仍放大时，盲目重置 qubits 可能会对剩余计算产生意外影响。 在释放内存之前，可以通过正确的方式 "撤消" 已执行的计算来避免这种情况。 量程计算的常见模式如下： 

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

：新增：从0.9 版开始，我们支持语态语句来实现上述转换。 使用该语句，可以通过以下方式实现 `ApplyWith` 操作：

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
如果外部和内部转换不能像操作那样轻松地提供，则这种语态语句就变得非常有用，但通过多个语句组成的块可以更方便地进行描述。 

在内块中定义的语句的反转换是由编译器自动生成的，并在 apply 块完成后执行。 由于不能在 apply 块中重新绑定用作内部块的一部分的任何可变变量，因此，生成的转换将保证为内块中计算的 adjoint。 

## <a name="expression-evaluation-statements"></a>表达式计算语句

`Unit` 类型的任何调用表达式都可以用作语句。
这主要用于在 qubits 上调用返回 `Unit` 的操作，因为该语句的用途是修改隐式量程状态。
表达式计算语句需要终止分号。

例如，

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
