---
title: 获取能源水平估算 |Microsoft Docs
description: 获取能源水平估计文档
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 0fd457b152083af364d924502c18bc0813e34b83
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442577"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="5f871-103">获取能量级别估算</span><span class="sxs-lookup"><span data-stu-id="5f871-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="5f871-104">估计能耗级别的值是量程化学的主要应用程序之一。</span><span class="sxs-lookup"><span data-stu-id="5f871-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="5f871-105">在此，我们概述了如何针对分子 Hydrogen 的规范示例执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5f871-105">Here, we outline how this may be performed for the canonical example of molecular Hydrogen.</span></span> <span data-ttu-id="5f871-106">本部分中所述的示例在化学示例存储库中 `MolecularHydrogen`。</span><span class="sxs-lookup"><span data-stu-id="5f871-106">The sample referenced in this section is `MolecularHydrogen` in the chemistry samples repository.</span></span> <span data-ttu-id="5f871-107">绘制输出的更直观的示例是 `MolecularHydrogenGUI` 演示。</span><span class="sxs-lookup"><span data-stu-id="5f871-107">A more visual example that plots the output is the `MolecularHydrogenGUI` demo.</span></span>

<span data-ttu-id="5f871-108">第一步是构造表示分子 Hydrogen 的 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="5f871-108">Our first step is to construct the Hamiltonian representing molecular Hydrogen.</span></span> <span data-ttu-id="5f871-109">尽管这可以通过 NWChem 工具构造，但我们会在此示例中手动添加 Hamiltonian 术语。</span><span class="sxs-lookup"><span data-stu-id="5f871-109">Though this can be constructed through the NWChem tool, we manually add Hamiltonian terms for brevity in this sample.</span></span>

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

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

<span data-ttu-id="5f871-110">模拟 Hamiltonian 要求我们将 fermion 运算符转换为 qubit 运算符。</span><span class="sxs-lookup"><span data-stu-id="5f871-110">Simulating the Hamiltonian requires us to convert the fermion operators to qubit operators.</span></span> <span data-ttu-id="5f871-111">此转换是通过 Wigner 编码执行的，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5f871-111">This conversion is performed through the Jordan-Wigner encoding as follows.</span></span>

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="5f871-112">现在，我们将代表 Hamiltonian 的 `qSharpData` 传递给[模拟 Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms)的 `TrotterStepOracle` 函数。</span><span class="sxs-lookup"><span data-stu-id="5f871-112">We now pass the `qSharpData` representing the Hamiltonian to the `TrotterStepOracle` function in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span></span> <span data-ttu-id="5f871-113">`TrotterStepOracle` 返回一项量程操作，该操作接近 Hamiltonian 的实时演变。</span><span class="sxs-lookup"><span data-stu-id="5f871-113">`TrotterStepOracle` returns a quantum operation that approximates the real time-evolution of the Hamiltonian.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

<span data-ttu-id="5f871-114">现在，我们可以使用标准库的阶段估算算法，使用上述模拟来了解地面状态能量。</span><span class="sxs-lookup"><span data-stu-id="5f871-114">We can now use the standard library's phase estimation algorithms to learn the ground state energy using the above simulation.</span></span> <span data-ttu-id="5f871-115">这需要准备好近似值到量子地面状态。</span><span class="sxs-lookup"><span data-stu-id="5f871-115">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="5f871-116">`Broombridge` 架构中提供了此类近似值的建议，但没有这些建议，默认方法会将多个 `hamiltonian.NElectrons` 电子添加到贪婪，从而最大程度地减少 electron 字词凝聚的。</span><span class="sxs-lookup"><span data-stu-id="5f871-116">Suggestions for such approximations are provided in the `Broombridge` schema, but absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to  greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="5f871-117">阶段估算函数和操作位于 " [..." 命名空间](xref:microsoft.quantum.characterization in DocFX notation)中。</span><span class="sxs-lookup"><span data-stu-id="5f871-117">The phase estimation functions and operations are located in the [Microsoft.Quantum.Characterization namespace](xref:microsoft.quantum.characterization in DocFX notation).</span></span>

<span data-ttu-id="5f871-118">以下代码片段显示了化学模拟库的实时演变输出如何与量程阶段估算集成。</span><span class="sxs-lookup"><span data-stu-id="5f871-118">The following snippet shows how the real time-evolution output by the chemistry simulation library may be integrated with quantum phase estimation.</span></span>

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

<span data-ttu-id="5f871-119">现在可以从驱动程序调用此 Q # 代码。</span><span class="sxs-lookup"><span data-stu-id="5f871-119">This Q# code may now be invoke from the driver program.</span></span> <span data-ttu-id="5f871-120">在下面，我们将创建一个完整状态模拟器，并运行 `GetEnergyByTrotterization` 以获取地面状态能量。</span><span class="sxs-lookup"><span data-stu-id="5f871-120">In the following, we create a full-state simulator and run `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

<span data-ttu-id="5f871-121">请注意，将返回两个参数。</span><span class="sxs-lookup"><span data-stu-id="5f871-121">Note that two parameters are returned.</span></span> <span data-ttu-id="5f871-122">`energyEst` 是对地面省电的估计，并且应该平均 `-1.137`。</span><span class="sxs-lookup"><span data-stu-id="5f871-122">`energyEst` is the estimate of the ground state energy, and should be around `-1.137` on average.</span></span> <span data-ttu-id="5f871-123">`phaseEst` 是由阶段估算算法返回的原始阶段，当因某个 `trotterStep` 太大而导致别名时，诊断会很有用。</span><span class="sxs-lookup"><span data-stu-id="5f871-123">`phaseEst` is the raw phase returned by the phase estimation algorithm, and is useful to diagnose when aliasing occurs due to a `trotterStep` that is too large.</span></span>
