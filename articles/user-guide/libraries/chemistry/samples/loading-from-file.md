---
title: 从文件加载 Hamiltonian
description: 了解如何使用 Broombridge 架构自动生成大型 Hamiltonian。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 715dbcefc10ecc5af45f2bdd228890f1cb28886b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274280"
---
# <a name="loading-a-hamiltonian-from-file"></a>从文件加载 Hamiltonian
以前，我们通过向其中添加单个字词来构造 Hamiltonians。 虽然这对小型示例而言很不错，但大规模的量程化学要求 Hamiltonians 或数十亿。 由化学包（如 NWChem）生成的此类 Hamiltonians 太大，无法手动导入。 在此示例中，我们将演示如何通过 `FermionHamiltonian` [Broombridge 架构](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)表示的分子自动生成实例。 对于引用，可以检查提供的 `LithiumHydrideGUI` 示例或 `RunSimulation` 示例。 有限支持还可用于从 LIQUi 使用的格式导入[|>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)。

接下来，请考虑示例存储库的文件夹中提供的 Nitrogen 分子的示例 `IntegralData/YAML` 。 用于加载架构的方法 `Broombridge` 非常简单。

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

Broombridge 架构还包含要准备的初始状态的建议。 `"|G⟩"` `"|E1⟩"` 可以通过检查文件来查看这些状态的标签（例如或）。 若要准备这些初始状态，将 `qSharpData` 获得由 Q # 量程算法使用的，与[上一部分](xref:microsoft.quantum.chemistry.examples.energyestimate)类似，但使用其他参数选择所需的初始状态。 例如，
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

上述所有步骤都可以使用提供的简便方法缩写，如下所示。
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

我们还可以从 LIQUi 加载 Hamiltonian |使用非常相似的语法> 格式。 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

通过从 Broombridge 的任何实例或任何中间步骤中执行此过程，可在指定的电子结构问题上运行量程阶段估算等量程算法。
