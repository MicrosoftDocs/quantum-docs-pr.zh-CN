---
title: 'Q # 技术-局部变量 |Microsoft Docs'
description: 'Q # 技术-局部变量'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4f5eff1ee8482fa5e5fee9dff421efab93fc0c5a
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183278"
---
# <a name="local-variables"></a>局部变量 #

可以通过使用 `let` 关键字，将 Q # 中任何类型的值分配给变量以便在操作或函数中重复使用。
对于实例：

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

这会将 Pauli 运算符的特定数组分配给名为 `measurementOperator`的变量。

> [!TIP]
> 请注意，我们不需要显式指定新变量的类型，因为 `let` 语句右侧的表达式明确，且该类型由编译器推断。 

Q # 中的变量是*不可变*的，这意味着，一旦以这种方式定义了变量，就不能再以任何方式对其进行更改。
这允许实现多种优化，包括对要重新排序的变量进行优化，以便应用操作的 `Adjoint` 变体。

使用如上所示的 `let` 绑定定义的变量是特定范围的本地变量，如操作体或 `for` 循环的内容。


## <a name="mutability"></a>可变性 ##

作为使用 `let`创建变量的替代方法，`mutable` 关键字将创建一个特殊的可变变量，该变量在最初使用 `set` 关键字创建后可重新绑定。

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Q # 中的所有类型（包括数组）都遵循值语义。 具体而言，不能更新数组项。 若要修改现有阵列，需要利用复制和更新机制，这与中F#的记录非常类似。 对于[`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)中提供的数组使用库工具，我们可以轻松地定义一个函数，该函数返回一个 Paulis 数组，其中 Pauli 的索引 `i` 使用给定值，所有其他项都是该标识： 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

在讨论 Q # 语句和表达式时，我们将详细介绍如何使用数组。 

Q # 中的可变性是一个适用于*符号*而不是类型或值的概念。 具体来说，它在类型系统中不具有表示形式（隐式或显式）以及绑定是否可变（如 `mutable` 关键字所指示）或不可变（如 `let`所示）不会更改绑定变量的类型。 这提供了一种在专用函数和操作内隔离可变性的重要方式。
具体而言，即使使用可变变量的操作的 adjoint 专用化不能自动生成，在调用使用可变性的函数的操作时，自动生成仍可正常工作。
出于此原因，最好使使用可变性的函数和操作尽可能简短，使量程程序的其余部分可以使用普通的不可变变量来编写。


## <a name="deconstruction"></a>析构 ##

除了分配单个变量外，`let` 和 `mutable` 关键字，或者事实上任何其他绑定构造，还允许将[元组类型](xref:microsoft.quantum.language.type-model#tuple-types)的内容解包。
此窗体的赋值被称为*析构*该元组的元素。
例如，如果我们通过元组对 Hamiltonian 中的字词进行建模，则可以使用析构来访问在该术语下需要模拟的不同数据：

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


