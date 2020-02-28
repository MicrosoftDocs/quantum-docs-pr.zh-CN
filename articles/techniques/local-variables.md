---
title: '局部变量-Q # 技术'
description: '了解如何在 Q # 中定义和使用局部变量。'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: cb6c662137c31a13c3dd6e9ca3f67879c469f788
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906859"
---
# <a name="local-variables"></a><span data-ttu-id="484cb-103">局部变量</span><span class="sxs-lookup"><span data-stu-id="484cb-103">Local Variables</span></span> #

<span data-ttu-id="484cb-104">可以通过使用 `let` 关键字，将 Q # 中任何类型的值分配给变量以便在操作或函数中重复使用。</span><span class="sxs-lookup"><span data-stu-id="484cb-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="484cb-105">例如：</span><span class="sxs-lookup"><span data-stu-id="484cb-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="484cb-106">这会将 Pauli 运算符的特定数组分配给名为 `measurementOperator`的变量。</span><span class="sxs-lookup"><span data-stu-id="484cb-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="484cb-107">请注意，我们不需要显式指定新变量的类型，因为 `let` 语句右侧的表达式明确，且该类型由编译器推断。</span><span class="sxs-lookup"><span data-stu-id="484cb-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="484cb-108">Q # 中的变量是*不可变*的，这意味着，一旦以这种方式定义了变量，就不能再以任何方式对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="484cb-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="484cb-109">这允许实现多种优化，包括对要重新排序的变量进行优化，以便应用操作的 `Adjoint` 变体。</span><span class="sxs-lookup"><span data-stu-id="484cb-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="484cb-110">使用如上所示的 `let` 绑定定义的变量是特定范围的本地变量，如操作体或 `for` 循环的内容。</span><span class="sxs-lookup"><span data-stu-id="484cb-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="484cb-111">可变性</span><span class="sxs-lookup"><span data-stu-id="484cb-111">Mutability</span></span> ##

<span data-ttu-id="484cb-112">作为使用 `let`创建变量的替代方法，`mutable` 关键字将创建一个特殊的可变变量，该变量在最初使用 `set` 关键字创建后可重新绑定。</span><span class="sxs-lookup"><span data-stu-id="484cb-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="484cb-113">Q # 中的所有类型（包括数组）都遵循值语义。</span><span class="sxs-lookup"><span data-stu-id="484cb-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="484cb-114">具体而言，不能更新数组项。</span><span class="sxs-lookup"><span data-stu-id="484cb-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="484cb-115">若要修改现有阵列，需要利用复制和更新机制，这与中F#的记录非常类似。</span><span class="sxs-lookup"><span data-stu-id="484cb-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="484cb-116">对于[`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)中提供的数组使用库工具，我们可以轻松地定义一个函数，该函数返回一个 Paulis 数组，其中 Pauli 的索引 `i` 使用给定值，所有其他项都是该标识：</span><span class="sxs-lookup"><span data-stu-id="484cb-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="484cb-117">在讨论 Q # 语句和表达式时，我们将详细介绍如何使用数组。</span><span class="sxs-lookup"><span data-stu-id="484cb-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="484cb-118">Q # 中的可变性是一个适用于*符号*而不是类型或值的概念。</span><span class="sxs-lookup"><span data-stu-id="484cb-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="484cb-119">具体来说，它在类型系统中不具有表示形式（隐式或显式）以及绑定是否可变（如 `mutable` 关键字所指示）或不可变（如 `let`所示）不会更改绑定变量的类型。</span><span class="sxs-lookup"><span data-stu-id="484cb-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="484cb-120">这提供了一种在专用函数和操作内隔离可变性的重要方式。</span><span class="sxs-lookup"><span data-stu-id="484cb-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="484cb-121">具体而言，即使使用可变变量的操作的 adjoint 专用化不能自动生成，在调用使用可变性的函数的操作时，自动生成仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="484cb-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="484cb-122">出于此原因，最好使使用可变性的函数和操作尽可能简短，使量程程序的其余部分可以使用普通的不可变变量来编写。</span><span class="sxs-lookup"><span data-stu-id="484cb-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="484cb-123">析构</span><span class="sxs-lookup"><span data-stu-id="484cb-123">Deconstruction</span></span> ##

<span data-ttu-id="484cb-124">除了分配单个变量外，`let` 和 `mutable` 关键字，或者事实上任何其他绑定构造，还允许将[元组类型](xref:microsoft.quantum.language.type-model#tuple-types)的内容解包。</span><span class="sxs-lookup"><span data-stu-id="484cb-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="484cb-125">此窗体的赋值被称为*析构*该元组的元素。</span><span class="sxs-lookup"><span data-stu-id="484cb-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="484cb-126">例如，如果我们通过元组对 Hamiltonian 中的字词进行建模，则可以使用析构来访问在该术语下需要模拟的不同数据：</span><span class="sxs-lookup"><span data-stu-id="484cb-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


