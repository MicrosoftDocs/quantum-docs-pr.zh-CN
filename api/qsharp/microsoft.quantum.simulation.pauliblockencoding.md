---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: b1df6d239e6ef061cf0a4784c652e9dd126991d5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230423"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="57f07-102">PauliBlockEncoding 函数</span><span class="sxs-lookup"><span data-stu-id="57f07-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="57f07-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="57f07-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="57f07-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57f07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57f07-105">为 Hamiltonian 创建块编码单一编码。</span><span class="sxs-lookup"><span data-stu-id="57f07-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="57f07-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ 由 $P $ _j $ 的 Pauli 术语的总和进行描述，每个术语都包含实系数 $ \ alpha_j $。</span><span class="sxs-lookup"><span data-stu-id="57f07-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="57f07-107">输入</span><span class="sxs-lookup"><span data-stu-id="57f07-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="57f07-108">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="57f07-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="57f07-109">一个 `GeneratorSystem` ，它描述 $H $ 作为 Pauli 条款的总和</span><span class="sxs-lookup"><span data-stu-id="57f07-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="57f07-110">输出： ([Double](xref:microsoft.quantum.lang-ref.double)、[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)) </span><span class="sxs-lookup"><span data-stu-id="57f07-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="57f07-111">第一个参数</span><span class="sxs-lookup"><span data-stu-id="57f07-111">First parameter</span></span>

<span data-ttu-id="57f07-112">系数 $ \alpha = \ sum_ {j} | \ alpha_j | $ 的一个标准。</span><span class="sxs-lookup"><span data-stu-id="57f07-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="57f07-113">第二个参数</span><span class="sxs-lookup"><span data-stu-id="57f07-113">Second parameter</span></span>

<span data-ttu-id="57f07-114">`BlockEncodingReflection`Hamiltonian 的单一 $U $ $H $。</span><span class="sxs-lookup"><span data-stu-id="57f07-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="57f07-115">由于这个单一的 $U ^ 2 = I $，它也是一个反射。</span><span class="sxs-lookup"><span data-stu-id="57f07-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="57f07-116">备注</span><span class="sxs-lookup"><span data-stu-id="57f07-116">Remarks</span></span>

<span data-ttu-id="57f07-117">这是通过以下方法获取的：准备并 unpreparing 状态 $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $，并构造一个按乘法控制的单一 <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> 和 <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> 。</span><span class="sxs-lookup"><span data-stu-id="57f07-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>