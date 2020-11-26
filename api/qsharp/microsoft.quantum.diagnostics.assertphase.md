---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202254"
---
# <a name="assertphase-operation"></a><span data-ttu-id="71332-102">AssertPhase 操作</span><span class="sxs-lookup"><span data-stu-id="71332-102">AssertPhase operation</span></span>

<span data-ttu-id="71332-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="71332-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="71332-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71332-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71332-105">断言 superposition 状态相同的阶段具有预期值。</span><span class="sxs-lookup"><span data-stu-id="71332-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="71332-106">描述</span><span class="sxs-lookup"><span data-stu-id="71332-106">Description</span></span>

<span data-ttu-id="71332-107">此操作断言对于一些任意实 $t $，可以表示为 $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ 票证 {0} + e ^ {-i\phi} \ 票证) $ 的阶段 $ \phi $ {1} 具有预期值。</span><span class="sxs-lookup"><span data-stu-id="71332-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="71332-108">输入</span><span class="sxs-lookup"><span data-stu-id="71332-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="71332-109">应为： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="71332-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="71332-110">$ \Phi \in 的预期值 (-\pi，\pi] $。</span><span class="sxs-lookup"><span data-stu-id="71332-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="71332-111">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="71332-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="71332-112">存储预期状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="71332-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="71332-113">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="71332-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="71332-114">实际值与预期值的绝对容差。</span><span class="sxs-lookup"><span data-stu-id="71332-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71332-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71332-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

