---
title: 'Q # 类型模型 |Microsoft Docs'
description: 'Q # 类型模型'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184740"
---
# <a name="the-type-model"></a>类型模型

本部分介绍了 Q # 类型的模型，并介绍了用于指定和使用类型的语法。
我们注意到，Q # 是一种*强类型*语言，因此，仔细地使用这些类型可帮助编译器在编译时为 Q # 程序提供强大的保证。

为了尽可能提供最强的保证，在 Q # 中的类型之间进行转换时，必须使用对函数的调用来显式转换。 此类函数作为 <xref:microsoft.quantum.convert> 命名空间的一部分提供。
另一方面，向上转换到兼容类型是隐式的。 

Q # 提供了基元类型，可以直接使用，也可以通过多种方式从其他类型生成新类型。
本部分的其余部分介绍了每个。

## <a name="primitive-types"></a>基元类型

Q # 语言提供若干*基元类型*，可以从这些类型构造其他类型：

- `Int` 类型表示64位有符号整数，例如： `2`、`107``-5`。
- `BigInt` 类型表示任意大小的有符号整数，如 `2L`、`107L``-5L`。
   此类型基于 .NET <xref:System.Numerics.BigInteger>
   类别.
- `Double` 类型表示双精度浮点数，例如： `0.0`、`-1.3``4e-7`。
- `Bool` 类型表示可 `true` 或 `false`的布尔值。
- `Qubit` 类型表示量程位或 qubit。
   用户不透明 `Qubit`;仅在将其传递给其他操作时，才可以对其进行操作，而不是将其传递到其他操作。
   最终，对 `Qubit`的操作是通过对量程处理器（或其模拟）调用内部指令来实现的。
- `Pauli` 类型表示四个 qubit Pauli 运算符之一。
   此类型用于表示旋转的基本操作，并指定要测量的可观察对象。
   这是一个枚举类型，它具有四个可能的值： `PauliI`、`PauliX`、`PauliY`和 `PauliZ`，它们是类型 `Pauli`的常量。
- `Result` 类型表示度量值的结果。
   这是具有两个可能值的枚举类型： `One` 和 `Zero`，它们是 `Result`类型的常量。
   `Zero` 指示已度量 + 1 eigenvalue;`One` 指示-1 eigenvalue。
- `Range` 类型表示由 `start..step..stop`表示的整数序列，其中表示步骤为选项。 
   这与 `start..1..stop``start .. stop` 相对应，例如 `1..2..7` 表示序列 $\{1、3、5、7\}$。
- `String` 类型是一系列 Unicode 字符，在用户创建后不透明。
  在发生错误或诊断事件时，此类型用于向传统主机报告消息。
- `Unit` 类型是仅允许 `()`一个值的类型。 
  此类型用于指示 Q # 函数或操作不返回任何信息。 

常量 `true`、`false`、`PauliI`、`PauliX`、`PauliY`、`PauliZ`、`One`和 `Zero` 都是 Q # 中的所有保留符号。

## <a name="array-types"></a>数组类型

给定任意有效的 Q # 类型 `'T`，都有一个类型表示 `'T`类型的值数组。
此数组类型表示为 `'T[]`;例如，`Qubit[]` 或 `Int[][]`。
例如，整数的集合 `Int[]`表示，而 `(Bool, Pauli)` 值数组的数组则 `(Bool, Pauli)[][]`表示。

在第二个示例中，请注意，这表示数组的可能交错数组，而不是矩形二维数组。
Q # 不提供对矩形多维数组的支持。

通过在数组的元素周围使用方括号（如 `[PauliI, PauliX, PauliY, PauliZ]`中所示），可以用 Q # 源代码来编写数组值。
数组文本的类型由数组中所有项的通用基类型决定。 

> [!WARNING]
> 创建数组后，不能更改数组的元素。
> 更新和重新分配语句和/或复制和更新表达式可用于构造修改后的数组。

或者，可以使用 `new` 关键字创建数组的大小：

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

在任一情况下，一旦构造了某个数组，就可以使用核心函数 `Length` 获取作为 `Int`的元素数。
数组可以使用方括号（带有类型 `Int` 或类型 `Range`的下标）作为下标，以获取包含数组元素子集的单个元素或新数组。
数组的下标是从零开始的：

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>元组类型

给定零个或多个不同类型 `T0`，`T1`，...，`Tn`，则可以将新的*元组类型*表示为 `(T0, T1, ..., Tn)`。
用于构造新元组类型的类型本身可以是元组，如 `(Int, (Qubit, Qubit))`中所示。
但这种嵌套始终是有限的，因为在任何情况下，元组类型都不能包含自身。

新元组类型的值是由元组中每个类型的值序列构成的元组。
例如，`(3, false)` 是其类型为 `(Int, Bool)`元组类型的元组。
可以创建元组、数组的元组、子元组的元组等的数组。

从 Q # 0.3，`Unit` 是空元组的*类型*名称;`()` 用于空元组*值*。

元组实例是不可变的。
Q # 不提供在创建元组内容之后更改元组内容的机制。

元组是一种功能强大的概念，用于在整个 Q # 中将值组合成单个值，使其更易于传递。
特别是，使用元组表示法，可以表达每个操作和可调用只采用一个输入，并只返回一个输出。

### <a name="singleton-tuple-equivalence"></a>单一实例元组等效

可以创建单一实例（单元素）元组，`('T1)`，如 `(5)` 或 `([1,2,3])`。
不过，Q # 将单一实例元组视为完全等效于封闭类型的值。
也就是说，`5` 和 `(5)`之间，或者在 `5` 和 `(((5)))`之间，或者在 `(5, (6))` 和 `(5, 6)`之间没有任何区别。

此等效性适用于所有用途，包括赋值和表达式。
与写入 `5+3`一样，编写 `(5)+3` 都是有效的，并且这两个表达式的计算结果都是 `8`。
具体而言，这意味着，其输入元组或输出元组类型具有一个字段的操作或函数可以被视为采用单个参数或返回单个值。

我们将此属性称为_单独元组等效_。

## <a name="user-defined-types"></a>用户定义的类型

Q # 文件可以定义包含任何合法类型的单个值的新命名类型。
对于任何元组类型 `T`，可以声明一个新的用户定义类型，该类型是具有 `newtype` 语句 `T` 的子类型。
例如，在 @"microsoft.quantum.canon" 命名空间中，复数定义为用户定义的类型：

```qsharp
newtype Complex = (Double, Double);
```

此语句创建一个新类型，该类型具有两个 `Double`类型的匿名项。   
除了匿名项以外，用户定义类型还支持从 Q # 版本0.7 或更高版本开始的命名项。 例如，对于表示复数实部和虚部 `Im` 的双精度值，我们可以将 `Re` 命名为： 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
为用户定义类型中的一个项命名并不意味着需要命名所有项-支持命名项和未命名项的任意组合。 此外，也可以将内部项命名为。
下面定义的类型 `Nested` （例如）具有基础类型 `(Double, (Int, String))`，其中仅命名 `Int` 类型的项，所有其他项都是匿名的。 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
命名项的优点是可以通过访问运算符 `::`直接访问它们。 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

为了访问匿名项，首先需要使用后缀运算符 `!`来提取换行值。
"解包" 运算符 `!`允许提取用户定义类型中包含的值。
此类 "解包" 表达式的类型为用户定义类型的基础类型。 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

解包运算符仅解包一层包装。
可以使用多个解包运算符来访问乘换行值。

对于实例：

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

有关更多详细信息，请查看有关[解包](xref:microsoft.quantum.language.expressions#unwrap-expressions)和[运算符优先级](xref:microsoft.quantum.language.expressions#operator-precedence)的部分。

可以通过调用相应的类型构造函数来创建用户定义类型的值：

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

或者，可以使用[复制和更新表达式](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)从现有值创建新值。 与 for 数组一样，此类表达式会复制原始表达式的所有项值（指定的已命名项除外）。 对于这些值，这些值将设置为在表达式的右侧定义的值。 对于用户定义的类型中的命名项，还存在可用于数组项的任何其他语言结构（例如，[更新和重新分配语句](xref:microsoft.quantum.language.statements#update-and-reassign-statement)）。

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

用户定义的类型可以在任何其他类型可以使用的任何地方使用。
具体而言，可以定义用户定义类型的数组，并将用户定义类型作为元组类型的元素包括在内。

无法创建递归类型结构。
也就是说，定义用户定义类型的类型不能是包含用户定义类型的元素的元组类型。
通常，用户定义类型可能没有彼此之间的循环依赖关系，因此以下类型定义将是非法的：

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

除了为可能复杂的元组类型提供短别名外，定义此类类型的一个明显优势在于它们可以记录特定值的意图。
返回到 `Complex`的示例中，一个还可以将2D 极坐标定义为用户定义的类型：

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

即使 `Complex` 和 `Polar` 都具有基础类型 `(Double, Double)`，两种类型在 Q # 中完全不兼容，最大限度地降低意外调用具有极坐标的复杂数学函数的风险，反之亦然。
通过这种方式，用户定义类型与中F#的记录具有类似的角色，例如。 


## <a name="operation-and-function-types"></a>操作和函数类型

Q #_操作_是一个量程子例程。
也就是说，它是包含量程操作的可调用例程。

Q #_函数_是在量程算法中使用的传统子例程。
它可能包含传统代码，但不包含量程运算。
具体而言，函数不能分配或借用 qubits，也不能调用操作。
不过，可以通过这些操作或 qubits 来进行处理。
函数是完全确定的，因此调用具有相同参数的函数将始终产生相同的结果。 

操作和函数共同称为_callables_。  可以在下面查看一些[示例](#examples)。

所有 Q # callables 都视为采用单个值作为输入，并返回单个值作为输出。
输入和输出值都可以是元组。
不 `Unit`返回结果的 Callables。
不带输入的 Callables 将空元组作为输入。

任何可调用的基本类型都编写为 `('Tinput => 'Tresult)` 或 `('Tinput -> 'Tresult)`，其中 `'Tinput` 和 `'Tresult` 都是类型。
第一种窗体（带有 `=>`）用于操作;函数的第二个窗体，其中包含 `->`。
例如，`((Qubit, Pauli) => Result)` 表示可能的 qubit 测量操作的签名。

函数类型由其签名完全指定。
例如，计算角度正弦值的函数的类型 `(Double -> Double)`。

操作（但不是函数）具有某些其他特征，这些_特征_表示为操作类型的一部分。 此类特征包括有关操作支持的函子的信息。
函子是生成基本操作专用化的元操作;请参阅下面的[函子](#functors)。

操作类型由其输入类型、输出类型及其特征来指定。    
为了要求对操作类型中的 `Controlled` 和/或 `Adjoint` 函子提供支持，我们需要添加一个批注以指示相应的特性。
批注 `is Ctl` 例如，指示操作可控制。 如果希望要求该类型的操作同时支持 `Adjoint` 和 `Controlled` 函子，我们可以将其表示为 `(Qubit => Unit is Adj + Ctl)`。 已使用的操作特征 `Adj` 和 `Ctl` 严格地说，这是两个预定义的标签集，其中每个标签都指示特定操作特征，如对特定函子的支持。
因此，`+` 用于指示这两个集的并集，并且 `*` 用于指示交集（即这两个集共有的标签）。  

例如，Pauli `X` 操作的类型 `(Qubit => Unit is Adj + Ctl)`。
不支持任何函子的操作类型由其输入和输出类型单独指定，无附加批注。


### <a name="type-parameterized-functions-and-operations"></a>类型参数化的函数和操作

可调用类型可以包含类型参数。
类型参数由单个引号作为前缀的符号指示;例如，`'A` 是合法的类型参数。

类型参数可能在单个签名中出现多次。
例如，将另一个函数应用于数组的每个元素并返回所收集结果的函数将 `(('A[], 'A->'A) -> 'A[])`签名。
同样，返回两个操作的组合的函数可能具有签名 `((('A=>'B), ('B=>'C)) -> ('A=>'C))`。

调用类型参数化的可调用时，具有相同类型参数的所有参数都必须具有相同的类型。

Q # 不提供约束可能替换为类型参数的可能类型的机制。

### <a name="type-compatibility"></a>类型兼容性

具有更多函子支持的操作可能会在具有较少函子但需要相同签名的操作的任何位置使用。
例如，类型 `(Qubit => Unit is Adj)` 的操作可在需要 `(Qubit => Unit)` 类型的操作的任何位置使用。

Q # 对于可调用的返回类型是协变的：返回类型 `'A` 的可调用与具有相同输入类型的可调用和与 `'A` 兼容的结果类型兼容。

Q # 对于输入类型是逆变的：使用类型 `'A` 作为输入的可调用与具有相同结果类型的可调用和与 `'A`兼容的输入类型兼容。

也就是说，提供以下定义：

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

以下为 true：

- 可以使用 `Invertible` 或 `Unitary`的 `inner` 参数调用操作 `ConjugateInvertibleWith`。
- 可以使用 `Unitary`的 `inner` 参数调用 `ConjugateUnitaryWith` 操作，但是不能 `Invertible`。
- 类型 `(Qubit[] => Unit is Adj + Ctl)` 的值可能从 `ConjugateInvertibleWith`返回。

> [!IMPORTANT]
> Q # 0.3 在用户定义类型的行为上引入了显著的差异。

用户定义的类型被视为基础类型的包装版本，而不是作为子类型。
这意味着，如果需要基础类型的值，用户定义类型的值将无法使用。

### <a name="functors"></a>函子

Q # 中的函子是一个工厂，它定义了其他操作的新操作。
在定义新操作的实现时，函子有权访问基操作的实现。
因此，函子可以比传统的高级函数执行更复杂的功能。

函子在 Q # 类型系统中没有表示形式。 因此，目前不可能将其绑定到变量或将其作为参数传递。 

函子可通过将其应用于操作来使用，返回新操作。
例如，将 `Adjoint` 函子应用到 `Y` 操作而生成的操作将以 `Adjoint Y`形式写入。
然后，可以像任何其他操作一样调用新操作。
因此，`Adjoint Y(q1)` 将 Adjoint 函子应用于 `Y` 操作以生成新的操作，并将该新操作应用于 `q1`。

同样，`Controlled X(controls, target)` 将控制的函子应用于 `X` 操作以生成新的操作，并将该新操作应用到 `controls` 和 `target`。

Q # 中的两个标准函子是 `Adjoint` 和 `Controlled`。

#### <a name="adjoint"></a>Adjoint

在量程计算中，操作的 adjoint 是操作的复杂共轭转置。
对于实现单一运算符的操作，adjoint 是操作的反向操作。
对于只调用一组 qubits 上的其他单一操作序列的简单操作，可以通过在反向序列中对同一 qubits 应用子操作的 adjoints 来计算 adjoint。

给定一个操作表达式，可以使用 `Adjoint` 函子生成新的操作表达式。
例如，`Adjoint QFT` 指定 `QFT` 操作的 adjoint。
新操作与基本操作具有相同的签名和类型。
具体而言，新操作还允许 `Adjoint`，并且仅当基本操作执行时才允许 `Controlled`。

Adjoint 函子是其自身的反向;也就是说，`Adjoint Adjoint Op` 始终与 `Op`相同。

#### <a name="controlled"></a>操控

操作的受控版本是新操作，仅当所有控件 qubits 都处于指定状态时，才会有效地应用基本操作。
如果控件 qubits 在 superposition 中，则会将基本操作一致应用到 superposition 的相应部分。
因此，受控操作通常用于生成牵连。

在 Q # 中，受控版本始终采用控制 qubits 的数组，并且指定的状态始终为所有控件 qubits 都处于计算（`PauliZ`） `One` 状态，$ \ket{1}$。
可以通过将适当的单一操作应用于受控操作之前的控件 qubits 来实现基于其他状态的控制，然后在受控操作后应用单一操作的逆。
例如，在受控操作前后将 `X` 操作应用于控件 qubit，将导致操作控制该 qubit 的 `Zero` 状态（$ \ket{0}$）;应用 `H` 操作之前和之后，将控制 `PauliX` `One` 状态，即 Pauli X，$ \ket{-} \mathrel{： =} （\ket{0}-\ket{1}）/\sqrt{2}$ 而不是 `PauliZ` `One` 状态。

给定一个操作表达式，可以使用 `Controlled` 函子生成新的操作表达式。
新操作的签名基于原始操作的签名。
结果类型是相同的，但输入类型是具有 qubit 数组的两元组，它将控件 qubit 保存为第一个元素，并将原始操作的参数作为第二个元素。
新操作支持 `Controlled`，且仅当原始操作执行时才支持 `Adjoint`。

如果原始操作只使用了一个参数，则会在此处播放单独的元组等效性。
例如，`Controlled X` 是 `X` 操作的受控版本。
`X` 具有类型 `(Qubit => Unit is Adj + Ctl)`，因此 `Controlled X` 具有类型 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`;由于单独的元组等效，这与 `((Qubit[], Qubit) => Unit is Adj + Ctl)`相同。

如果基本操作采用多个参数，请记住将操作的受控版本的相应参数括在括号中，以将其转换为元组。
例如，`Controlled Rz` 是 `Rz` 操作的受控版本。
`Rz` 具有类型 `((Double, Qubit) => Unit is Adj + Ctl)`，因此 `Controlled Rz` 具有类型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`。
因此，`Controlled Rz(controls, (0.1, target))` 是 `Controlled Rz` 的有效调用（请注意 `0.1, target`之间的括号）。

作为另一个示例，可以按 `Controlled X([control], target)`实现 `CNOT(control, target)`。 如果目标应由2个 control qubits （CCNOT）控制，则可以使用 `Controlled X([control1, control2], target)` 语句。

### <a name="examples"></a>示例

此 Q # 操作示例来自[测量](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement)示例。 在操作中，可以分配 qubits 并对这些 qubits （如 `H` 和 `X`）使用量程操作：

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit

            set result = M(qubit);      // Measure the qubit

            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

此函数示例来自[PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)示例。 它包含纯传统代码。 您可以看到，与上面的示例不同，不会分配任何 qubits，也不会使用任何量程运算。


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

还可以将函数传递给 qubits 以进行处理，如本示例中的[ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis)示例。 Qubits 会传递到函数并用于处理，不过，在任何时候都不会修改 qubit 状态。

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
