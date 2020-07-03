---
title: 问答中的变量#
description: 填充说明
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 08301f408dcb2211ba25c582a5e5aa43310b714a
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885292"
---
# <a name="variables-in-q"></a>问答中的变量#

Q # 区分可变和不可变的符号，或者绑定/分配给表达式的*变量*。
通常，建议使用不可变符号，因为它允许编译器执行更多优化。

绑定的左侧由一个符号元组和一个表达式的右侧组成。

## <a name="immutable-variables"></a>不可变变量

可以通过使用关键字，将 Q # 中的任何类型的值分配给变量以便在操作或函数内重复使用 `let` 。 

不可变绑定包含关键字 `let` ，后跟符号或符号元组、等号 `=` 、要将符号绑定到的表达式和终止分号。

例如：

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

这会将一个特定的 Pauli 运算符数组分配给变量名（或 "symbol"） `measurementOperator` 。

> [!NOTE]
> 在前面的示例中，无需显式指定新变量的类型，因为语句右侧的表达式 `let` 是明确的，编译器将推断正确的类型。 

使用定义的变量 `let` 是*不可变*的，这意味着，定义后，不能再以任何方式对其进行更改。
这可以实现多个有利的优化，包括对要对变量进行排序以便应用操作变体的传统逻辑的优化 `Adjoint` 。

## <a name="mutable-variables"></a>可变变量

作为使用创建变量的替代方法 `let` ， `mutable` 关键字创建一个可变变量，该变量在最初使用关键字创建后*可以*重新绑定 `set` 。

稍后可将在语句中声明并绑定的符号重新绑定 `mutable` 到代码中的其他值。 如果稍后在代码中重新绑定符号，则其类型不会更改，并且新绑定的值必须与该类型兼容。

### <a name="rebinding-of-mutable-symbols"></a>重新绑定可变符号

您可以使用语句重新绑定可变变量 `set` 。
此类重新绑定包含关键字 `set` ，后跟符号或符号元组、等号、将 `=` 符号重新绑定到的表达式和终止分号。

下面是重新绑定语句方法的一些示例。

#### <a name="apply-and-reassign-statements"></a>应用和重新分配语句

`set`如果右侧包含二元运算符的应用程序，则特定类型的语句（即*apply 和重新分配*语句）提供了一种简便的连接方式，并将结果重新绑定到运算符的左侧参数。 例如，

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
`counter`在循环的每次迭代中递增计数器的值 `for` 。 前面的代码等效于 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

类似的语句适用于所有的二元运算符，其中左侧的类型与表达式类型匹配。 这些语句提供了一种简便的方法来累计值。

例如，supposing `qubits` 是 qubits 的一种注册：
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>更新和重新分配语句

在右侧的[复制和更新表达式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)中存在类似的连接。
相应地，对于用户定义的类型中的*命名项*以及*数组项*，都存在*更新和重新分配*语句。  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
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

对于数组， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 在 Q # 标准库中，可以为许多常见数组初始化和操作需要提供所需的工具，从而有助于避免第一次更新数组项。 

如果需要，更新和重新分配语句提供了一种替代方法：

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

例如，使用中提供的数组的库工具， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 可以轻松地定义一个函数，该函数返回一个类型数组，该数组的 `Pauli` 索引处的元素 `i` 采用给定的 `Pauli` 值，其他所有项均为标识（ `PauliI` ）。

下面是此类函数的两个定义，第二个是利用我们的处理工具。

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

您可以改为使用 from 来创建类型数组，而不是遍历数组中的每个索引，并有条件地将其设置为 `PauliI` 或给定 `pauli` ，而 `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) `PauliI` 只需返回已在索引中更改了特定值的复制和更新表达式 `location` ：

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>元组析构

除了分配单个变量外，还可以使用 `let` 和 `mutable` 关键字（或任何其他绑定构造，如）将 `set` [元组类型](xref:microsoft.quantum.guide.types#tuple-types)的内容解压缩。
此窗体的赋值被称为*析构*该元组的元素。

如果绑定右侧是元组，则可以在赋值时析构该元组。
此类 deconstructions 可以涉及嵌套元组，只要右侧的元组形状与符号元组的形状兼容，所有完整或部分析构都有效。

例如：

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>绑定范围

通常，符号绑定超出范围，并且在中出现的语句块的末尾变为不起作用。
此规则有两种例外情况：

- 循环的循环变量的绑定处于 `for` for 循环的主体的范围内，但不在循环结束后。
- 循环的所有三个部分 `repeat` / `until` （正文、测试和修正）都充当单个作用域，因此，在主体中绑定的符号可用于测试和修正。

对于这两种类型的循环，每次循环都在其自己的作用域中运行，因此更早传递中的绑定在稍后的传递中不可用。
有关这些循环的详细信息，请参阅[控制流](xref:microsoft.quantum.guide.controlflow)。

内部块从外部块继承符号绑定。
每个块只能绑定一个符号;定义与作用域中的另一个符号名称相同（无 "隐藏"）的符号是非法的。
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

and

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
...                 // n is not bound to a value
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

## <a name="next-steps"></a>后续步骤

了解如何使用 Q # 中[的 Qubits](xref:microsoft.quantum.guide.qubits) 。