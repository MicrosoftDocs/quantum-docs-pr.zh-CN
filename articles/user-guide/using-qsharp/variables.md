---
title: 问答中的变量#
description: 填充说明
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 456c05d4ca66a747e0cc514a30c6bbb33610f481
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327775"
---
# <a name="variables-in-q"></a>问答中的变量#

Q # 区分可变和不可变符号，或 "变量" （绑定/分配到表达式）。
通常，建议使用不可变符号，因为它允许编译器执行更多优化。

绑定的左侧由符号元组和表达式的右侧组成的位置组成。

## <a name="immutable-variables"></a>不可变变量

使用关键字，可以将 Q # 中任何类型的值分配给变量以便在操作或函数中重复使用 `let` 。

不可变绑定包含关键字 `let` ，后跟符号或符号元组、等号 `=` 、要将符号绑定到的表达式和终止分号。

例如：

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

这会将一个特定的 Pauli 运算符数组分配给变量名（或 "symbol"） `measurementOperator` 。

> [!NOTE]
> 我们不需要显式指定新变量的类型，因为语句右侧的表达式 `let` 是明确的，并且该类型由编译器推断。 

使用定义的变量 `let` 是*不可变*的，也就是说，定义后，将无法再以任何方式对其进行更改。
这允许实现多种优化，包括对要重新排序的变量进行优化，以便应用 `Adjoint` 操作的变体。

## <a name="mutable-variables"></a>可变变量

作为使用创建变量的替代方法 `let` ， `mutable` 关键字将创建一个可变变量，该变量在最初使用关键字创建后*可*重新绑定 `set` 。

声明并作为语句的一部分绑定的符号 `mutable` 可能会在后面的代码中重新绑定到不同的值。 如果稍后在代码中重新绑定符号，则其类型不会更改，并且新绑定的值需要与该类型兼容。

### <a name="rebinding-of-mutable-symbols"></a>重新绑定可变符号

可以使用语句重新绑定可变变量 `set` 。
此类重新绑定包含关键字 `set` ，后跟符号或符号元组、等号、将 `=` 符号重新绑定到的表达式和终止分号。

在这里，我们提供了一些可能的重新绑定语句技术示例

### <a name="apply-and-reassign-statements"></a>应用和重新分配语句

`set`如果右侧包含二元运算符的应用程序，并将结果重新绑定到运算符的左侧参数，则我们将一种特定类型的语句称为 "*应用" 和 "重新分配*" 语句。 例如，
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
`counter`在循环的每次迭代中递增计数器的值 `for` 。 上述代码等效于 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

类似的语句可用于所有的二元运算符，其中左侧的类型与表达式类型匹配。 这为示例提供了一种简单的方法来累计值。

例如，supposing `qubits` 是 qubits 的 regsiter：
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a>更新和重新分配语句

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

对于数组， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 在标准库中，可以为许多常见数组初始化和操作需求提供必要的工具，从而有助于避免第一次更新数组项。 

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

例如，使用在中提供的数组的库工具， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 可以轻松地定义一个函数，该函数返回一个 Paulis 数组，其中 Pauli 的索引 `i` 采用给定值，所有其他项都是标识。

下面是此类函数的两个定义，第二个是利用我们的处理工具。

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

我们可以使用 from 创建的数组，而不是循环访问数组中的每个索引，并有条件地将其设置为 `PauliI` 或 `Pauli` ，而只是 `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) `PauliI` 返回一个复制和更新表达式，在此表达式中，我们在索引处更改了特定值 `location` ：

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>元组析构

除了分配单个变量外， `let` 和 `mutable` 关键字---或事实上任何其他绑定构造，如 `set` （如下所述）---还允许将[元组类型](xref:microsoft.quantum.guide.types#tuple-types)的内容解包。
此窗体的赋值被称为*析构*该元组的元素。

如果绑定的右侧是一个元组，则该元组可能在赋值时是析构的。
此类 deconstructions 可能涉及嵌套元组，只要右侧的元组形状与符号元组的形状兼容，所有完整或部分析构都有效。

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
- 循环的所有三个部分 `repeat` / `until` （正文、测试和修正）被视为单个作用域，因此，在主体中绑定的符号在测试中可用，在修正中可用。

对于这两种类型的循环，每次循环都在其自己的作用域中执行，因此更早传递中的绑定在稍后的传递中不可用。
可以在[控制流](xref:microsoft.quantum.guide.controlflow)中找到有关这些循环的详细信息。

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