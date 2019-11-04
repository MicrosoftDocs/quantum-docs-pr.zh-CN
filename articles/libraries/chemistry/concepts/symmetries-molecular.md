---
title: 分子积分的 Symmetries |Microsoft Docs
description: 分子积分概念文档的 Symmetries
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442398"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="2527c-103">Symmetries of 分子积分</span><span class="sxs-lookup"><span data-stu-id="2527c-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="2527c-104">Coulomb Hamiltonian 的固有对称（这是[针对电子系统的量程模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中提供的 Hamiltonian，用于描述与 nuclei 之间的电子交互，以及与 symmetries 之间的交互），可导致许多利用它来压缩 Hamiltonian 中的条款。</span><span class="sxs-lookup"><span data-stu-id="2527c-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="2527c-105">通常，如果对基本函数 $ \psi_j $ 没有进一步的假设，则我们仅具有 \begin{equation} h_ {pqrs} = h_ {qpsr}，\tag{★} \label{eq： hpqrs} \end{equation}，可立即从[如果电子系统](xref:microsoft.quantum.chemistry.concepts.quantummodels)注意到 $p、q $ 和 $r 的值相同，则 s $ 将与反通信交换。</span><span class="sxs-lookup"><span data-stu-id="2527c-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="2527c-106">如果我们假设 orbitals 是实际值（因为它们适用于高斯 orbital），则我们会进一步了解 \begin{equation} h_ {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {spqr} = h_ {qrsp} .\tag {★} \label{eq： hpqrsreal} \end{公式} 假设有这样的假设，我们可以使用上面的 symmetries 来减少按 $8 $ 的系数存储 Hamiltonian 的矩阵元素所需的数据。虽然这样做会使导入数据的方式略有挑战性。</span><span class="sxs-lookup"><span data-stu-id="2527c-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="2527c-107">幸运的是，Hamiltonian 模拟库具有可用于从[LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)或从[NWChem](http://www.nwchem-sw.org/index.php/Main_Page)直接导入整型文件的子例程。</span><span class="sxs-lookup"><span data-stu-id="2527c-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="2527c-108">分子 orbital 积分（例如 $h\_{pq} $ 和 $h\_{pqrs} $ 词条），这种情况下使用 `OrbitalIntegral` 类型来表示，这提供了许多有用的函数来表示此对称。</span><span class="sxs-lookup"><span data-stu-id="2527c-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
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

<span data-ttu-id="2527c-109">除了枚举数值相同的所有 orbital 整型，还可以按如下所示生成由 `OrbitalIntegral` 表示的 Hamiltonian 中包含的所有 orbital 索引的列表。</span><span class="sxs-lookup"><span data-stu-id="2527c-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="2527c-110">从分子整型构造 Fermionic Hamiltonians</span><span class="sxs-lookup"><span data-stu-id="2527c-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="2527c-111">不是通过添加 `FermionTerm`来构造 Fermionic Hamiltonian，而是可以自动添加对应于每个 orbital 整数的所有字词。</span><span class="sxs-lookup"><span data-stu-id="2527c-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="2527c-112">例如，以下代码将自动枚举所有 permutational symmetries 并按规范顺序对术语进行排序：</span><span class="sxs-lookup"><span data-stu-id="2527c-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
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
