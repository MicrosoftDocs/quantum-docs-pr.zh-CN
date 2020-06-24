---
title: Symmetries of 分子积分
description: '了解如何使用 Q # OrbitalIntegral 类型枚举分子 symmetries。'
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: b7e7b79af17af544c4a784eff08500498afc9f67
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274281"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries of 分子积分

Coulomb Hamiltonian 的固有对称（这是[针对电子系统的量程模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中提供的 Hamiltonian，用于描述电子彼此之间相互交互，而与 nuclei 之间的交互）会导致许多 symmetries，可以利用这些来压缩 Hamiltonian 中的条款。
一般情况下，如果没有对基础函数 $ \ psi_j $ 进行进一步的假设，则我们仅具有 \begin{equation} h_ {pqrs} = h_ {qpsr}，\tag{★} \label{eq： hpqrs} \end{equation}，该通信可立即从[电子系统的量程模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中的积分中查看，注意，如果 $p、q $ 和 $r，s $ 将与反互换。

如果我们假设 orbitals 是实值（因为它们适用于高斯 orbital），则我们会进一步使 \begin{equation} h_ {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} h_ {h_} spqr： hpqrsreal} \end{equation} 假设有这样的假设，我们可以使用上面的 symmetries 来减少按 $8 $ 的系数存储 Hamiltonian 的矩阵元素所需的数据。虽然这样做会使导入数据的方式略有挑战性。
幸运的是，Hamiltonian 模拟库具有可用于从[LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)或从[NWChem](http://www.nwchem-sw.org/index.php/Main_Page)直接导入整型文件的子例程。

分子 orbital （例如 $h \_ {pq} $ 和 $h \_ {pqrs} $ 词条）使用 `OrbitalIntegral` 类型表示，该类型提供了很多有助于表达此对称的有用函数。
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

除了枚举所有数字相同的 orbital 积分，可按如下所示生成包含在中的 Hamiltonian 中包含的所有 orbital 索引的列表 `OrbitalIntegral` 。
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>从分子整型构造 Fermionic Hamiltonians

不是通过添加来构造 Fermionic Hamiltonian，而是会 `FermionTerm` 自动添加对应于每个 orbital 整数的所有字词。
例如，以下代码将自动枚举所有 permutational symmetries 并按规范顺序对术语进行排序： 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
