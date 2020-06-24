---
title: Hartree-Fock 理论
description: 了解 Hartree – Fock 理论，它是一种简单的方法来构造量程系统的初始状态。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274439"
---
# <a name="hartreefock-theory"></a>Hartree – Fock 理论

在量程化学模拟中，最重要的数量或许是地面状态，即 Hamiltonian 矩阵的最小能量 eigenvector。
这是因为，对房间温度的大多数分子（例如，反应速率）由描述反应通道中某个步骤的开始和结束时间的量程状态和房间温度（如中间状态）中的可用能量差异构成。
尽管地面状态通常太难学习（即使是在量程计算机上），因为它是通过指数量大的配置进行分布的。
可以了解地面状态的能源。
例如，如果 $ \ket{\psi} $ 是任何纯量子状态，则 \begin{equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{equation} 提供系统处于该状态的平均能量。
而地面状态则为提供最小此类值的状态。 因此，选择尽可能接近真实状态的状态对于直接估计能源至关重要（如在 variational eigensolvers 中完成）或通过阶段估算至关重要。

Hartree – Fock 理论提供一种简单的方法来构造量程系统的初始状态。 它将对量程系统的基本状态产生单个 Slater 决定。 为此，它在 Fock 范围内找到一个可最大程度地减少地面能耗的旋转。 具体而言，对于 $N $ 电子的系统，该方法执行旋转 \begin{equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket \mapsto \ {0} prod_ {j = 0} ^ {n-1} e ^ {u} \ket \defeq\ { {0} j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket，dagger_j {0} prod_ \End{equation} 与反 Hermitian （即 $u =-u ^ \dagger $） matrix $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $。 应注意的是，矩阵 $u $ 表示 orbital 旋转，$ \widetilde{a} ^ \ dagger_j $ 和 $ \widetilde{a} _j $ 表示电子占用 Hartree – Fock 分子 orbitals 的创建和 annihilation 运算符。


然后优化矩阵 $u $，以最大程度地减少预期能量 $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket {0} $。 虽然这种优化问题可能会很难，但实际上，Hartree – Fock 算法常常会迅速汇聚到优化问题的近乎最佳解决方案，尤其是对于平衡几何图形中的封闭式 shell 分子。 我们可以将这些状态指定为对象的实例 `FermionWavefunction` 。 例如，状态 $a ^ \ dagger_ ^ \ {1} dagger_ {2} 在 {6} {0} 化学库中实例化 ^ \ dagger_ \ket $，如下所示。
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
还可以用索引为波形函数建立索引 `SpinOrbital` ，然后将这些索引转换为整数，如下所示。
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

关于 Hartree 的最重要的功能-Fock 理论是，它生成的量程状态在电子之间没有牵连。
这意味着，它通常提供分子系统属性的合适定性说明。 

还可以从中重新构造 Hartree Fock 状态 `FermionHamiltonian` ，如下所示。
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

但是，若要获得准确的结果，尤其是对于强关联系统，一定要有超过 Hartree – Fock 理论的量程状态。
