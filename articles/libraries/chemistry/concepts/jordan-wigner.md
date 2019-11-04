---
title: 约旦-Wigner 表示形式 |Microsoft Docs
description: 约旦-Wigner 表示概念文档
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: f34233bc17ff68a9e04256959f8d79be2682c34f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184043"
---
# <a name="jordan-wigner-representation"></a>约旦-Wigner 表示形式

尽管第二个量化 Hamiltonians 可根据 $a ^ \dagger $ （创建）和 $a $ （annihilation）来方便地表示，但这些操作不是量子计算机的基本操作。
因此，如果想要在量程计算机上实现它们，则需要将这些操作员映射到可在量程计算机上实现的单一矩阵。
约旦– Wigner 表示形式提供了一个此类地图。
但有些其他类（例如 Bravyi – Kitaev 表示形式）也存在，并有其各自的优点和缺点。
约旦 Wigner 表示形式的主要优点是它的简单性。

约旦 Wigner 表示形式是直接派生的。
回忆一下，状态 $ \ket{0}_j $ 表示自旋 orbital $j $ 为空，$ \ket{1}_j $ 表示其已被占用。
这意味着 qubits 可以自然地存储给定旋转 orbital 的职业。
接下来，我们将 $a ^ \dagger_j \ket{0}_j = \ket{1}_j $ 和 $a ^ \dagger_j \ket{1}_j = $0。
可以轻松验证 \begin{align} a ^ \dagger_j & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}，\nonumber\\\\ a_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0 \end{bmatrix} = \frac{X_j-iY_j}{2}，\end{align}，其中 $X _j $ 和 $Y _j $ 是作用于 Pauli $Y $ 的 $X Qubit $ 和-$j $ 运算符。
这表明，对于单个自旋 orbital，可以根据量子计算机可识别的单一矩阵轻松表示创建和 annihilation 运算符。
请注意，尽管 $X $ 和 $Y $ 是单一 $a ^ \dagger $，但 $a $ 不是。
稍后我们将会看到，这不会为模拟带来挑战。

还有一个问题是，尽管上述构造适用于单个自旋 orbital，但对于具有两个或多个自旋 orbitals 的系统，它会失败。
由于 Fermions 是 antisymmetic 的，因此我们知道 $a ^ \dagger_j a ^ \dagger_k =-a ^ \dagger_k ^ \dagger_j $ 用于任何 $j $ 和 $k $。
但是，$ $ \left （\frac{X_j-iY_j}{2}\right） \left （\frac{X_k-iY_k}{2}\right） = \left （\frac{X_k-iY_k}{2}\right） \left （\frac{X_j-iY_j}{2}\right）。
换言之，这两个创建运算符不会根据需要进行反接。
这可以通过简单的 inelegant 方式来纠正。
解决方法是注意，Pauli 运算符天生都是反路程。
具体而言，$XZ =-ZX $ and $YZ =-ZY $。
因此，通过 interspersing 将 $ operators $Z 为构造运算符，我们可以模拟正确的通信。
完整的构造如下所示： 

\begin{align} a ^ \dagger_1 & = \left （\frac{X-iY}{2}\right） \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1，\\\\ a ^ \dagger_2 & = Z\otimes\left （\frac{X-iY}{2}\right） \otimes 1 \ otimes 1 \otimes \cdots \otimes 1，\\\\ ^ \dagger_3 & = Z\otimes Z\otimes \left （\frac{X-iY}{2}\right） \otimes 1 \otimes \cdots \otimes 1，\\\\ & \vdots\\\\ ^ \dagger_N & = Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimesZ\otimes \left （\frac{X-iY}{2}\right）。 \label{eq： JW} \end{align}

也可以根据 Pauli 运算符来表达数字运算符，$n _j $。
令人欣慰，$Z $ operators 的字符串（称为 Wigner 字符串）在进行一次替换后取消。
在执行此项（并再次调用 $X _jY_j = iZ_j $）后，我们已 \begin{equation} n_j = a ^ \dagger_j a_j = \frac{（1-Z_j）}{2}。
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>构建约旦 Wigner 表示形式的 Hamiltonians

一旦我们调用了 Wigner 表示形式，则将 Hamiltonian 转换为 Pauli 运算符的总和就是一种直接的方法。
只需将 Fermionic Hamiltonian 中的每个 $a ^ \dagger $ 和 $a $ 运算符替换为上面给定的 Pauli 运算符。
当一次执行此替换时，Hamiltonian 中只有五个术语。
这五个类对应于我们可以选择 $p、q $ 和 $p、q、r、Hamiltonian 中的单正文和两正文术语中的方法的不同方式。
对于这五个类，如果 $p > q > r > s $ 和实值 orbitals，则会

\begin{align} h_ {pp} a_p ^ \dagger a_p & = \sum_p \frac{h_{pp}}{2}（1-Z_p）\\\\ h_ {pq} （a_p ^ \dagger a_q + a ^ \dagger_q a_p） & = \frac{h_{pq}}{2}\left （\prod_{j = q + 1} ^ {p-1} Z_j \right） \left （X_pX_q + Y_pY_q\right）\\\\ h_ {pqqp} n_p n_q & = \frac{h_{pqqp}}{4}\left （1-Z_p-Z_q + Z_pZ_q \right）\\\\ H_ {pqqr} & = \frac{h_{pqqr}}{2}\left （\prod_{j =r + 1} ^ {p-1} Z_j \right） \left （X_pX_r + Y_pY_r\right） \left （\frac{1-Z_q}{2}\right）\\\\ H_ {pqrs} & = \frac{h_{pqrs}}{8}\prod_{j = s + 1} ^ {r-1} Z_j\prod_ {k = q + 1} ^ {p-1} Z_k \Big （XXXX-XXYY +XYXY\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big） \end{align}

尽管手动生成此类 Hamiltonians 需要应用这些替换规则，但对于大型分子来说，这种做法不可行，因为这种情况可能包含数百万 Hamiltonian 条款。
作为替代方法，可以根据 Hamiltonian 的 `FermionHamiltonian` 表示形式自动构造 `JordanWignerEncoding`。

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

在此窗体中构造 Hamiltonians 后，我们可以使用一段量程模拟算法将动态 $e 生成的 dynamics 编译为一个基本入口序列（在某些用户可定义的容错范围内）。
我们在算法文档中讨论了用于量程模拟、qubitization 和 Trotter – Suzuki 公式的两种最常用的方法。 我们在 Hamiltonian 模拟库中提供了这两种方法的实现。
