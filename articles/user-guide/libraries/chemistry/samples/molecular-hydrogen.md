---
title: 获取能量级别估算
description: '演练一个示例 :::no-loc(Q#)::: 程序，该程序估算分子 hydrogen 的能源级别值。'
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 81fba0c52c854d61f9143659795fb4d3c3cee8b9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691524"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="98f4b-103">获取能量级别估算</span><span class="sxs-lookup"><span data-stu-id="98f4b-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="98f4b-104">估计能耗级别的值是量程化学的主要应用程序之一。</span><span class="sxs-lookup"><span data-stu-id="98f4b-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="98f4b-105">本文概述了如何针对分子 hydrogen 的规范示例执行此操作。</span><span class="sxs-lookup"><span data-stu-id="98f4b-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="98f4b-106">此部分中引用的示例位于 [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) 化学示例存储库中。</span><span class="sxs-lookup"><span data-stu-id="98f4b-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="98f4b-107">演示中绘制出了一个更直观的示例 [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) 。</span><span class="sxs-lookup"><span data-stu-id="98f4b-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="98f4b-108">估计分子 hydrogen 的能耗值</span><span class="sxs-lookup"><span data-stu-id="98f4b-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="98f4b-109">第一步是构造表示分子 hydrogen 的 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="98f4b-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="98f4b-110">尽管可以使用 NWChem 工具构造此项，但为简单起见，此示例将手动添加 Hamiltonian 术语。</span><span class="sxs-lookup"><span data-stu-id="98f4b-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

<span data-ttu-id="98f4b-111">模拟 Hamiltonian 需要将 fermion 运算符转换为 qubit 运算符。</span><span class="sxs-lookup"><span data-stu-id="98f4b-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="98f4b-112">这种转换是通过 Jordan-Wigner 编码执行的，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98f4b-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the :::no-loc(Q#)::: operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="98f4b-113">接下来， `qSharpData` 将（表示 Hamiltonian）传递给 `TrotterStepOracle` 函数。</span><span class="sxs-lookup"><span data-stu-id="98f4b-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="98f4b-114">`TrotterStepOracle` 返回一项量程运算，它模拟 Hamiltonian 的实时演变。</span><span class="sxs-lookup"><span data-stu-id="98f4b-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="98f4b-115">有关详细信息，请参阅 [模拟 Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms)。</span><span class="sxs-lookup"><span data-stu-id="98f4b-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

<span data-ttu-id="98f4b-116">此时，你可以使用标准库的 [阶段估算算法](xref:microsoft.quantum.libraries.characterization) ，使用以前的模拟来了解地面状态能量。</span><span class="sxs-lookup"><span data-stu-id="98f4b-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="98f4b-117">这需要准备好近似值到量子地面状态。</span><span class="sxs-lookup"><span data-stu-id="98f4b-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="98f4b-118">架构中提供了此类近似值的建议 [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 。</span><span class="sxs-lookup"><span data-stu-id="98f4b-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="98f4b-119">但是，如果不提供这些建议，则默认方法会将多个 `hamiltonian.NElectrons` 电子添加到贪婪，从而最大程度地减少 electron 字词凝聚的。</span><span class="sxs-lookup"><span data-stu-id="98f4b-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="98f4b-120">DocFX [命名空间中的](xref:Microsoft.Quantum.Characterization) 表示法中提供了阶段估计函数和操作。</span><span class="sxs-lookup"><span data-stu-id="98f4b-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization) namespace.</span></span>

<span data-ttu-id="98f4b-121">以下代码片段演示了化学模拟库的实时演变输出如何与量程阶段估算集成。</span><span class="sxs-lookup"><span data-stu-id="98f4b-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

<span data-ttu-id="98f4b-122">你现在可以 :::no-loc(Q#)::: 从宿主程序调用该代码。</span><span class="sxs-lookup"><span data-stu-id="98f4b-122">You can now invoke the :::no-loc(Q#)::: code from the host program.</span></span> <span data-ttu-id="98f4b-123">下面的 c # 代码创建一个全状态模拟器，并运行 `GetEnergyByTrotterization` 以获取地面状态能量。</span><span class="sxs-lookup"><span data-stu-id="98f4b-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

<span data-ttu-id="98f4b-124">操作返回两个参数：</span><span class="sxs-lookup"><span data-stu-id="98f4b-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="98f4b-125">`energyEst` 是对地面省电的估计，并且应接近 `-1.137` 平均。</span><span class="sxs-lookup"><span data-stu-id="98f4b-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="98f4b-126">`phaseEst` 是阶段估算算法返回的原始阶段。</span><span class="sxs-lookup"><span data-stu-id="98f4b-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="98f4b-127">这对于因值太大而无法诊断别名时非常有用 `trotterStep` 。</span><span class="sxs-lookup"><span data-stu-id="98f4b-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
