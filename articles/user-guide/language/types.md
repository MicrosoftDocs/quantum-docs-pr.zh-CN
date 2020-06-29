---
title: Q# 中的类型
description: '了解 Q # 编程语言中使用的不同类型。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: e37ce6e3a2dfad5395cdecf06178d64ec51b79f1
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415278"
---
# <a name="types-in-q"></a>Q# 中的类型

本文介绍了用于指定和使用类型的 Q # 类型模型和语法。 有关如何创建和操作这些类型的表达式的详细信息，请参阅[类型表达式](xref:microsoft.quantum.guide.expressions)。

我们注意到，Q # 是一种*强类型*语言，因此，仔细地使用这些类型可帮助编译器在编译时为 Q # 程序提供强大的保证。
为了尽可能提供最强的保证，在 Q # 中的类型之间进行转换时，必须使用对函数的调用来显式转换。 Q # 提供作为命名空间一部分的各种此类函数 <xref:microsoft.quantum.convert> 。
另一方面，向上转换到兼容类型是隐式发生的。 

Q # 提供了直接使用的基元类型，以及从其他类型生成新类型的各种方法。
本文的其余部分将对此进行介绍。

## <a name="primitive-types"></a>基元类型

Q # 语言提供以下*基元类型*，所有这些类型都可直接在 Q # 程序中使用。 你还可以使用这些基元类型构造新类型。

- `Int`类型表示64位有符号整数，例如，、 `2` `107` 、 `-5` 。
- `BigInt`类型表示任意大小的有符号整数，例如、、 `2L` `107L` `-5L` 。
   此类型基于 .NET<xref:System.Numerics.BigInteger>
   type。

- `Double`类型表示双精度浮点数，如、、 `0.0` `-1.3` `4e-7` 。
- `Bool`类型表示或的布尔值 `true` `false` 。
- 此 `Range` 类型表示一个由表示的整数序列， `start..step..stop` 其中表示该步骤是可选的。 
   例如， `start .. stop` 对应于 `start..1..stop` ， `1..2..7` 表示序列 $ \{ 1、3、5、7 \} $。
- `String`类型是一系列 Unicode 字符，在用户创建后不透明。
  在发生 `string` 错误或诊断事件时，使用类型向传统主机报告消息。
- `Unit`类型只能有一个值 `()` 。 
  使用此类型可指示 Q # 函数或操作不返回任何信息。 
- `Qubit`类型表示量程位或 qubit。
   `Qubit`s 对用户不透明。 仅在将其传递给其他操作时，才可以对其进行操作，而不是将其传递到其他操作。
   最终，你可以通过在 `Qubit` 量程处理器（或量程模拟器）上调用内部指令来在上执行操作。
- 此 `Pauli` 类型表示四个 Qubit Pauli 运算符之一。
   使用此类型可表示旋转的基本操作，并指定要测量的可观察对象。
   这是一个枚举类型，它具有四个可能 `PauliI` 的值：、 `PauliX` 、 `PauliY` 和 `PauliZ` ，它们是类型的常量 `Pauli` 。
- `Result`类型表示度量值的结果。
   它是具有两个可能值的枚举类型： `One` 和 `Zero` ，它们是类型的常量 `Result` 。
   `Zero`指示已度量 + 1 eigenvalue;`One`指示已测量-1 eigenvalue。

常量、、、、、、 `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` 和 `Zero` 都是 Q # 中的所有保留符号。

## <a name="array-types"></a>数组类型

* 对于任何有效的 Q # 类型，都有一个类型，表示该类型的值的数组。
    例如， `Qubit[]` 和 `(Bool, Pauli)[]` 表示 `Qubit` 值和 `(Bool, Pauli)` 元组值的数组。

* 数组的数组也是有效的。 在前面的示例中，将指示数组的数组 `(Bool, Pauli)` `(Bool, Pauli)[][]` 。

> [!NOTE] 
> 此示例 `(Bool, Pauli)[][]` 表示数组的可能交错数组，而不是矩形二维数组。 Q # 不支持矩形多维数组。

* 使用方括号将数组的元素括起来，就可以用 Q # 源代码编写数组值，如中所示 `[PauliI, PauliX, PauliY, PauliZ]` 。
数组中所有项的通用基类型确定数组文本的类型。 因此，使用没有公共基类型的元素构造数组将引发错误。  
有关示例，请参阅[callables 的数组](xref:microsoft.quantum.guide.expressions#arrays-of-callables)。

    > [!WARNING]
    > 创建后，不能更改数组的元素。
    > 若要构造修改后的数组，请使用[更新和重新分配语句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)或[副本和更新表达式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)。

* 或者，可以使用关键字通过其大小创建数组 `new` ：

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* 使用 core 函数 `Length` 获取数组中的元素数作为 `Int` 。
* 数组可以为下标，以获取包含数组元素子集的单个元素或新数组。
数组的下标从零开始，必须是类型 `Int` 或类型 `Range` ：

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>元组类型

元组是一种功能强大的概念，用于在整个 Q # 中将值组合成单个值，使其更易于传递。
特别是，使用元组表示法，可以表达每个操作和可调用只采用一个输入，并只返回一个输出。

* 给定零个或多个不同类型 `T0` ， `T1` ，...， `Tn` 可将新的*元组类型*表示为 `(T0, T1, ..., Tn)` 。
用于构造新元组类型的类型本身可以是元组，如中所示 `(Int, (Qubit, Qubit))` 。
但这种嵌套始终是有限的，因为在任何情况下，元组类型都不能包含自身。

* 新元组类型的值是由元组中每个类型的值序列组成的元组。
例如， `(3, false)` 是一个其类型为元组类型的元组 `(Int, Bool)` 。
可以创建元组、数组的元组、子元组的元组等的数组。

* 从 Q # 0.3， `Unit` 是空元组的*类型*名称; `()` 用于空元组的*值*。

* 元组实例是不可变的。
Q # 不提供在创建元组内容之后更改元组内容的机制。



### <a name="singleton-tuple-equivalence"></a>单一实例元组等效

可以创建单一实例（单元素）元组 `('T1)` ，例如 `(5)` 或 `([1,2,3])` 。
但是，Q # 将单一实例元组视为等效于所包含的类型的值。
也就是说，and `5` `(5)` 、or 和 between 之间没有区别 `5` `(((5)))` `(5, (6))` `(5, 6)` 。
这与编写时一样有效 `(5)+3` `5+3` ; 两个表达式的计算结果均为 `8` 。

此等效性适用于所有用途，包括赋值和表达式。
给定任意表达式，括在括号中的同一表达式是同一类型的表达式。
例如， `(7)` 是类型为的表达式， `Int` 它是类型的 `([1,2,3])` 表达式 `Int[]` ， `((1,2))` 是类型的表达式 `(Int, Int)` 。

具体而言，这意味着您可以查看其输入元组或输出元组类型具有一个字段的操作或函数，以采用单个参数或返回单个值。

我们将此属性称为_单独元组等效_。


## <a name="user-defined-types"></a>用户定义类型

用户定义的类型声明包含关键字 `newtype` ，后跟用户定义类型的名称、 `=` 有效类型规范和终止分号。

例如：

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* 每个 Q # 源文件可以声明任意数量的用户定义类型。
* 类型名称在命名空间中必须是唯一的，且不能与操作和函数名称冲突。
* 用户定义类型是不同的，即使基类型相同也是如此。
具体而言，两个用户定义类型的值之间不会自动转换，即使基础类型相同也是如此。

### <a name="named-vs-anonymous-items"></a>命名与匿名项

Q # 文件可以定义包含任何合法类型的单个值的新命名类型。
对于任何元组类型 `T` ，可以使用语句声明一个新的用户定义类型，该类型是的子类型 `T` `newtype` 。
@"microsoft.quantum.math"例如，在命名空间中，复数定义为用户定义的类型：

```qsharp
newtype Complex = (Double, Double);
```
此语句创建一个新类型，其中包含两个匿名项类型 `Double` 。   

除了匿名项以外，用户定义类型还支持从 Q # 版本0.7 或更高版本开始的*命名项*。 例如，可以将的项命名为， `Re` 表示复数的实部和 `Im` 虚部： 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
为用户定义类型中的一个项命名并不意味着需要命名所有项-支持命名项和未命名项的任意组合。 此外，内部项还可以命名为。
`Nested`例如，下面定义的类型具有基础类型 `(Double, (Int, String))` ，其类型仅为类型为的项 `Int` ，所有其他项都是匿名的。 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

命名项的优点是可以通过*访问运算符*直接访问它们 `::` 。 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

除了为可能复杂的元组类型提供短别名以外，定义此类类型的一个明显优势在于它们可以记录特定值的意图。
返回到的示例 `Complex` ，一个还可以将2d 极坐标定义为用户定义的类型：

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

尽管 `Complex` 和两者都 `Polar` 具有基础类型，但这 `(Double, Double)` 两种类型在 Q # 中完全不兼容，因此，最大程度地减少了意外调用带有极坐标的复杂数学函数的风险，反之亦然。

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>使用解包运算符访问匿名项

若要访问匿名项，请首先使用后缀运算符提取包装的值 `!` 。
使用 "解包" 运算符， `!` 可以提取用户定义类型中包含的值。
此类 "解包" 表达式的类型为用户定义类型的基础类型。 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

单个解包运算符对一层包装进行了解包。 使用多个解包运算符来访问乘换行值。

例如：

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

有关解包运算符的更多详细信息，请参阅[Q # 中的类型表达式](xref:microsoft.quantum.guide.expressions)。

### <a name="creating-values-of-user-defined-types"></a>创建用户定义类型的值

通过调用相应的类型构造函数来创建用户定义类型的值：

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

或者，您可以使用[复制和更新表达式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)从现有值创建新值。 与在数组中一样，复制和更新表达式会复制原始表达式的所有项值（指定的已命名项除外）。 对于这些异常，这些项的值是在表达式的右侧定义的值。 对于用户定义类型中的命名项，还存在可用于数组项的任何其他语言构造（例如，[更新和重新分配语句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)）。

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

* 你可以使用任何其他类型的任意位置的用户定义类型。
具体而言，可以定义用户定义类型的数组，并将用户定义类型作为元组类型的元素包括在内。

* 无法创建递归类型结构。
也就是说，定义用户定义类型的类型不能是包含用户定义类型的元素的元组类型。
更常见的情况是，用户定义类型可能没有彼此之间的循环依赖关系，因此下面的一组类型定义无效：

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>操作和函数类型

给定类型 `'Tinput` 和 `'Tresult` ：

* `('Tinput => 'Tresult)`是任何*操作*的基本类型，例如 `((Qubit, Pauli) => Result)` 。
* `('Tinput -> 'Tresult)`是任何*函数*的基本类型，例如 `(Int -> Int)` 。 

这些是可调用的*签名*。

* 所有 Q # callables 采用单个值作为输入，并返回单个值作为输出。
* 可以对输入和输出值使用元组。
* 不返回结果的 Callables，返回 `Unit` 。
* 不带输入的 Callables 将空元组作为输入。

### <a name="functors"></a>函子

*函数*类型由其签名完全指定。 例如，计算角度正弦值的函数将具有类型 `(Double -> Double)` 。 

*操作*具有一些其他特征，这些特征表示为操作类型的一部分。 此类特征包括有关操作支持的*函子*的信息。
例如，如果执行操作依赖于其他 qubits 的状态，则它应支持 `Controlled` 函子; 如果操作具有反向，则它应支持 `Adjoint` 函子。

> [!NOTE]
> 本文仅讨论函子如何更改操作签名。 有关函子和操作的更多详细信息，请参阅[Q # 中的操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。 

若要要求对 `Controlled` 操作类型中的和/或函子提供支持 `Adjoint` ，需要添加指示相应特征的注释。
批注 `is Ctl` （例如 `(Qubit => Unit is Ctl)` ）指示操作可控制。 也就是说，它的执行依赖于另一个 qubit 或 qubits 的状态。 同样，批注 `is Adj` 指示操作具有 adjoint，也就是说，它可以 "反转" 以便连续应用操作，然后将其 adjoint 为状态，使状态保持不变。 

如果你希望要求该类型的操作同时支持 `Adjoint` 和 `Controlled` 函子，则可以将此表示为 `(Qubit => Unit is Adj + Ctl)` 。 例如，内置 Pauli 操作的类型为 <xref:microsoft.quantum.intrinsic.x> `(Qubit => Unit is Adj + Ctl)` 。 

不支持任何函子的操作类型由其输入和输出类型单独指定，无附加批注。

### <a name="type-parameterized-functions-and-operations"></a>类型参数化的函数和操作

可调用类型可以包含*类型参数*。
使用以单引号为前缀的符号指示类型参数;例如， `'A` 是一个合法的类型参数。
有关如何定义类型参数化 callables 的详细信息和详细信息，请参阅[Q # 中的操作和函数](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)。

类型参数可能在单个签名中出现多次。
例如，将其他函数应用于数组的每个元素并返回所收集结果的函数具有签名 `(('A[], 'A->'A) -> 'A[])` 。
同样，返回两个操作的组合的函数具有签名 `((('A=>'B), ('B=>'C)) -> ('A=>'C))` 。

调用类型参数化的可调用时，具有相同类型参数的所有参数都必须具有相同的类型。

Q # 不提供一种机制，用于约束用户可能替换为类型参数的类型。

## <a name="next-steps"></a>后续步骤

现在，你已了解包含 Q # 语言的所有类型，请参阅[q # 中的类型表达式](xref:microsoft.quantum.guide.expressions)，了解如何创建和操作这些各种类型的表达式。
