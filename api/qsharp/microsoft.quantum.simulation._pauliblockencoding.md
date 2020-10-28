---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695267"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="0257a-102">_PauliBlockEncoding 函数</span><span class="sxs-lookup"><span data-stu-id="0257a-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="0257a-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0257a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0257a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0257a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0257a-105">为 Hamiltonian 创建块编码单一编码。</span><span class="sxs-lookup"><span data-stu-id="0257a-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="0257a-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ 由 $P $ _j $ 的 Pauli 术语的总和进行描述，每个术语都包含实系数 $ \ alpha_j $。</span><span class="sxs-lookup"><span data-stu-id="0257a-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="0257a-107">输入</span><span class="sxs-lookup"><span data-stu-id="0257a-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="0257a-108">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="0257a-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="0257a-109">一个 `GeneratorSystem` ，它描述 $H $ 作为 Pauli 条款的总和</span><span class="sxs-lookup"><span data-stu-id="0257a-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a><span data-ttu-id="0257a-110">statePrepUnitary： [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0257a-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0257a-111">给定函数 $f： j\rightarrow V_j $，单一操作 $V $，该操作在索引 $ \ket{j} $ 上应用单一 $V _j $ 控制。</span><span class="sxs-lookup"><span data-stu-id="0257a-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="0257a-112">多路复用器： ([int](xref:microsoft.quantum.lang-ref.int)、[int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)、[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0257a-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="0257a-113">输出： ([Double](xref:microsoft.quantum.lang-ref.double)、[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)) </span><span class="sxs-lookup"><span data-stu-id="0257a-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="0257a-114">第一个参数</span><span class="sxs-lookup"><span data-stu-id="0257a-114">First parameter</span></span>

<span data-ttu-id="0257a-115">系数 $ \alpha = \ sum_ {j} | \ alpha_j | $ 的一个标准。</span><span class="sxs-lookup"><span data-stu-id="0257a-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="0257a-116">第二个参数</span><span class="sxs-lookup"><span data-stu-id="0257a-116">Second parameter</span></span>

<span data-ttu-id="0257a-117">`BlockEncodingReflection`Hamiltonian 的单一 $U $ $U $。</span><span class="sxs-lookup"><span data-stu-id="0257a-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="0257a-118">由于这个单一的 $U ^ 2 = I $，它也是一个反射。</span><span class="sxs-lookup"><span data-stu-id="0257a-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="0257a-119">注解</span><span class="sxs-lookup"><span data-stu-id="0257a-119">Remarks</span></span>

<span data-ttu-id="0257a-120">示例操作： prepare 和 unpreparing state $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $，并构造一个被乘以控制的单一 <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> 。</span><span class="sxs-lookup"><span data-stu-id="0257a-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>