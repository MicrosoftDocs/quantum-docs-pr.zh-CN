---
title: Pauli 度量值
description: Pauli 度量值
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 300a1ebcfd5d7bca8b025c69adebaad03106433d
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036589"
---
# <a name="pauli-measurements"></a>Pauli 度量值

在前面的讨论中，我们重点介绍计算基础度量值。
事实上，从符号的角度来看，量子计算会出现其他常见的度量，这在计算基础度量方面非常方便。
当你使用 Q # 时，你将遇到的最常见的度量值可能是*Pauli 的度量值*，它将计算基础度量值纳入其他基准，并在不同 qubits 之间进行奇偶校验。
在这种情况下，通常会讨论度量 Pauli 运算符，通常是运算符，如 $X、Y、Z $ 或 $Z \otimes Z、X\otimes X、X\otimes Y $ 等。

> [!TIP]
> 在 Q # 中，多 qubit Pauli 运算符通常由 `Pauli[]`类型的数组表示。
> 例如，若要表示 $X \otimes Z \otimes Y $，可以使用数组 `[PauliX, PauliZ, PauliY]`。

在量程错误纠正的子字段中，讨论 Pauli 运算符的度量值尤其常见。
在 Q # 中，我们遵循类似的约定;现在，我们将介绍此替代度量视图。

在深入了解有关如何思考 Pauli 度量的详细信息之前，请考虑测量量程内单个 qubit 对量程状态的作用。
假设有一个 $n 的 "qubit" 量程状态;然后，测量一个 qubit 会立即将该状态的一半作为 $ 2 ^ n $ 可能的一半。
换言之，该度量值将量程状态投影到两个半个空格。
我们可以通用化我们对量化指标的看法，以反映这种直觉。

为了简洁地识别这些 subspaces，我们需要一种用于描述这些的语言。
描述这两个 subspaces 的一种方法是通过一个矩阵来指定它们，该矩阵只包含两个唯一的本征值，约定为 "\pm $1"。
有关以这种方式描述 subspaces 的简单示例，请考虑 $Z $：

$ $ \begin{align} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}。
\end{align} $ $

通过读取 $Z Pauli $ matrix 的对角元素，我们可以看到 $Z $ 具有两个本征向量、$ \ket{0}$ 和 $ \ket{1}$，其中包含相应的本征值 $ \pm $1。
因此，如果我们测量 qubit 并获取 `Zero` （对应于状态 $ \ket{0}$），我们知道我们的 qubit 的状态是 $Z $ operator 的 $ + $1 eigenstate。
同样，如果我们获取 `One`，我们知道，qubit 的状态为 $Z $ 的 $-$1 eigenstate。
此过程在 Pauli 度量语言中称为 "度量 Pauli $Z $"，完全等同于执行计算基础度量。

为 $Z $ 的单一转换的任何 $ 2 \ $2 矩阵都还满足此条件。
也就是说，我们还可以使用矩阵 $A = U ^ \dagger Z U $，其中 $U $ 是任何其他单一矩阵，以便为矩阵定义其 $ \pm $1 本征向量中的两个测量结果。
Pauli 度量值的表示法通过将 $X、Y、Z $ 度量值识别为可从 qubit 获取信息的等效度量来引用这种单一等效性。
为方便起见，下面提供了这些度量值。


|Pauli 度量  |单一转换  |
|-------------------|------------------------|
| $Z $               | $ \boldone $             |
| $X $               | $H $                    |
| $Y $               | $HS ^ {\dagger} $         |

也就是说，使用这种语言时，"度量值 $Y $" 相当于应用 $HS ^ \dagger $，然后以计算为基础进行度量，其中[`S`](xref:microsoft.quantum.intrinsic.s)是一个内部量程操作，有时称为 "阶段入口"，可由单一矩阵模拟

$ $ \begin{align} S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}。
\end{align} $ $

它还等效于将 $HS ^ \dagger $ 应用于量程状态向量，然后测量 $ $Z $，以便以下操作等效于 `Measure([PauliY], [q]])`：

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

然后，将转换回计算基础，以将 $SH $ 应用到量程状态向量，从而找到正确的状态;在上面的代码片段中，转换回计算基础的方式是通过使用 `within … apply` 块自动处理。

在 Q # 中，我们说结果---也就是说，从与状态---交互中提取的传统信息由 $j \in \\{\texttt{Zero}，\texttt{One}\\} $ 的 `Result` 值指定，以指示结果是否位于 Pauli 运算符度量的 $ （-1） ^ j $ eigenspace 中。


## <a name="multiple-qubit-measurements"></a>多 qubit 度量

多 qubit Pauli 运算符的度量值的定义类似，如下所示：

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 & & 0 & 0\\\\ 0 & 0 & & 0\\\\ 0 & 0 & 1 \ end {bmatrix}。
$$

因此，两个 Pauli $Z $ 运算符的 tensor 产品构成一个矩阵，其中包含由 $ + $1 和 $-$1 本征值组成的两个空格。
与单 qubit 大小写一样，两者都构成一半空间，这意味着可访问的矢量空间的一半属于 $ + $1 eigenspace，另一半是 $-$1 eigenspace。
一般情况下，从 tensor 产品的定义可以轻松地看出 $Z Pauli $ operators 的任何 tensor 产品以及标识也服从这一点。
例如，

$ $ \begin{align} Z \otimes \boldone = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & & \\0 \\ & 0 & 0 & 0-1 \end{bmatrix}。
\end{align} $ $

与之前一样，此类矩阵的任何单一转换还将描述 $ \pm $1 本征值标记的两个半角空格。
例如，$X $Z = HXH $ 的标识中的 \otimes X = H\otimes H （Z\otimes Z） H\otimes H $。
与 qubit 情况类似，所有 qubit Pauli 度量值都可以编写为 $U ^ \dagger （Z\otimes \id） U $，$ 4 \ $4 单一矩阵 $U $。 枚举下表中的转换。

> [!NOTE]
> 在下表中，我们使用 $ \operatorname{SWAP} $ 指示矩阵 $ $ \begin{align} \operatorname{SWAP} & = \left （\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right） \end{align} $ $ 用于模拟内部操作[`SWAP`](xref:microsoft.quantum.intrinsic)。

|Pauli 度量     |单一转换  |
|----------------------|------------------------|
| $Z \otimes \boldone $ | $ \boldone \otimes \boldone $ |
| $Z \otimes \boldone $ | $ \boldone\otimes \boldone $ |
| $X \otimes \boldone $ | $H \otimes \boldone $ |
| $Y \otimes \boldone $ | $HS ^ \dagger\otimes \boldone $ |
| $ \boldone \otimes Z $ | $ \operatorname{SWAP} $ |
| $ \boldone \otimes X $ | $ （H\otimes \boldone） \operatorname{SWAP} $ |
| $ \boldone \otimes Y $ | $ （HS ^ \dagger\otimes \boldone） \operatorname{SWAP} $ |
| $Z \otimes Z $ | $ \operatorname{CNOT}\_{10}$ |
| $X \otimes Z $ | $ \operatorname{CNOT}\_{10}（H\otimes \boldone） $ |
| $Y \otimes Z $ | $ \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes \boldone） $ |
| $Z \otimes X $ | $ \operatorname{CNOT}\_{10}（\boldone\otimes H） $ |
| $X \otimes X $ | $ \operatorname{CNOT}\_{10}（H\otimes H） $ |
| $Y \otimes X $ | $ \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes H） $ |
| $Z \otimes Y $ | $ \operatorname{CNOT}\_{10}（\boldone \otimes HS ^ \dagger） $ |
| $X \otimes Y $ | $ \operatorname{CNOT}\_{10}（H\otimes HS ^ \dagger） $ |
| $Y \otimes Y $ | $ \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes HS ^ \dagger） $ |

此处出现[`CNOT`](xref:microsoft.quantum.intrinsic.cnot)操作的原因如下。
每个不包含 $ \boldone $ matrix 的 Pauli 度量值都等效于一个单一的，以便按以上推理 $Z \otimes Z $。
$Z \otimes Z $ 的本征值仅依赖于构成每个计算基础向量的 qubits 的奇偶校验，并且用于计算此奇偶校验并将其存储在第一位的受控 not 运算。
然后，在度量第一位后，可以恢复生成的半角空格的标识，这相当于测量 Pauli 运算符。

另外一个注意事项：尽管测量 $Z \otimes Z $ 与按顺序 $Z \otimes \mathbb{1}$ 和 $ \mathbb{1} \otimes Z $，此假设将为 false。
原因是度量 $Z \otimes Z $ 将量程状态投影到这些运算符的 $ + $1 或 $-$1 eigenstate 中。
测量 $Z \otimes \mathbb{1}$，then $ \mathbb{1} \otimes Z $ 将量程状态向量首先投影到 $Z \otimes \mathbb{1}$ 的半个空格上，然后再投影到 $ \mathbb{1} \otimes Z $ 的半个空格。
由于有四个计算基准向量，同时执行这两个度量会将状态降到一个四分之一空间，因此将其减少为单个计算基础向量。

## <a name="correlations-between-qubits"></a>Qubits 之间的关联
查看度量标准（例如 $X \otimes X $ 或 $Z \otimes Z $）的 tensor 产品的另一种方法是，这些度量值使你可以查看在这两个 qubits 之间的关联中存储的信息。
度量 $X \otimes \id $ 使你可以查看在第一个 qubit 中本地存储的信息。
尽管这两种类型的度量在量程计算中都同样很有价值，但前者会导致量程计算的强大功能。
它在量程计算中显示，通常情况下，你想要学习的信息不会存储在任何单个 qubit 中，而是在所有 qubits 中同时存储为非本地存储，因此仅通过联合度量（例如 $Z \otimes Z $）来查看此项信息成为清单。

例如，在 "纠错" 中，我们经常想要了解在学习有关我们尝试保护的状态时所发生的错误。
"[位翻转" 代码示例](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)显示了如何使用诸如 $Z \otimes z \otimes \id $ 和 $ \Id \otimes Z \otimes z $ 这类度量的示例。
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

也可以测量任意 Pauli 运算符（如 $X \otimes Y \otimes Z \otimes \boldone $）。
Pauli 运算符的所有此类 tensor 产品仅具有两个本征值 $ \pm $1，并且两个 eigenspaces 构成整个矢量空间的半个空格。
因此，它们符合上面所述的要求。

在 Q # 中，此类度量值将返回 $j $ （如果度量值产生 eigenspace 符号 $ （-1） ^ j $ 的结果）。
将 Pauli 度量作为 Q # 中的内置功能非常有用，因为测量此类运算符需要使用受控-NOT 入口和基础转换的长链来描述将操作表达为 $Z $ 和 $ \id $ 的 tensor 产品所需的 diagonalizing $U $ 门。
通过能够指定想要执行其中一项预定义度量，无需担心如何转换基础，以使计算基础度量提供必要的信息。
Q # 会自动处理所有必要的基础转换。
有关详细信息，请参阅[`Measure`](xref:microsoft.quantum.intrinsic.measure)和[`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis)操作。

## <a name="the-no-cloning-theorem"></a>无克隆定理

量程信息非常强大。
它使我们能够以指数形式比最佳已知传统算法更快地执行令人惊叹的东西，或高效模拟经典需要指数成本来准确模拟的相关 electron 系统。
但对量程计算的强大功能有一些限制。
这种限制是由*无克隆定理*提供的。

不克隆的定理为名称正好。
它不允许量程计算机克隆通用量程状态。
定理的证明非常简单。
虽然在这里我们的讨论中，无克隆定理的完整证明是一项很少的技术，但在我们的范围内没有额外的辅助 qubits 的证明（辅助 qubits 在计算期间用于暂存空间，并且在 Q # 中易于使用和管理，请参阅 <xref:microsoft.quantum.techniques.qubits>）。

对于此类量程计算机，克隆操作必须由单一矩阵进行描述。
我们不允许进行度量，因为它会损坏我们尝试克隆的量程状态。
若要模拟克隆操作，我们希望单一矩阵使用 $ $ U \ket{\psi} \ket 的属性，为任何状态 $ \ket{\psi} ${0} = \ket{\psi} \ket{\psi} $ $。
然后，matrix 乘法的线性属性表示对于任何第二个量程状态 $ \ket{\phi} $，

$ $ \begin{align} U \left [\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right] \ket{0} & = \frac{1}{\sqrt{2}} U\ket {\ phi} \ 票证{0} + \frac{1}{\sqrt{2}} U\ket {\ psi} \ 票证{0} \\\\ & = \frac{1}{\sqrt{2}} \left （\ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi} \right） \\\\ & \ne \left （\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right） \otimes \left （\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right）。
\end{align} $ $

这提供了不克隆定理背后的基本直觉：复制未知量程状态的任何设备必须至少在其复制的某些状态下引发错误。
虽然 cloner 在输入状态下线性处理的关键假设可以通过添加和度量辅助 qubits 来突破，此类交互也会通过测量统计信息泄漏有关系统的信息并防止精确在这种情况下进行克隆。
有关无克隆定理的更完整的证明，请参阅[以获取详细信息](xref:microsoft.quantum.more-information)。

无克隆定理对于定性了解量程计算非常重要，因为如果可以将量程状态重新克隆，则会被授予近乎神奇的功能，可以从量程状态中学习。
事实上，您可能违反了海森堡的 vaunted 不确定性原则。
或者，您可以使用最佳的 cloner 从复杂的量程分布中获取一个示例，并从一个示例中了解有关该分布的所有内容。
这就像你翻转硬币和观察打印头，然后在告诉朋友，使其响应 "Ah 该硬币的分布必须与 $p = 0.512643 \ ldots $！  此类语句是不 sensical 的，因为有一位信息（头结果）只是不能提供编码分发所需的多个信息，而不会有大量的信息。
同样，如果没有以前的信息，我们就不能完全克隆量程状态，因为我们不知道 $p $ 就无法准备系综的此类硬币。

信息在量程计算中不可用。
每个 qubit 都提供一项信息，而不克隆定理显示没有后门，可以利用它来解决有关系统所获得的信息与对其调用的干扰之间的基本平衡点。
