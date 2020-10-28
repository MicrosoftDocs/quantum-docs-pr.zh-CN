---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695594"
---
# <a name="assertphase-operation"></a><span data-ttu-id="b46d0-102">AssertPhase 操作</span><span class="sxs-lookup"><span data-stu-id="b46d0-102">AssertPhase operation</span></span>

<span data-ttu-id="b46d0-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b46d0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b46d0-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b46d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b46d0-105">断言 superposition 状态相同的阶段具有预期值。</span><span class="sxs-lookup"><span data-stu-id="b46d0-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="b46d0-106">说明</span><span class="sxs-lookup"><span data-stu-id="b46d0-106">Description</span></span>

<span data-ttu-id="b46d0-107">此操作断言对于一些任意实 $t $，可以表示为 $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ 票证 {0} + e ^ {-i\phi} \ 票证) $ 的阶段 $ \phi $ {1} 具有预期值。</span><span class="sxs-lookup"><span data-stu-id="b46d0-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="b46d0-108">输入</span><span class="sxs-lookup"><span data-stu-id="b46d0-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="b46d0-109">应为： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b46d0-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b46d0-110">$ \Phi \in 的预期值 (-\pi，\pi] $。</span><span class="sxs-lookup"><span data-stu-id="b46d0-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="b46d0-111">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b46d0-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b46d0-112">存储预期状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="b46d0-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="b46d0-113">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b46d0-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b46d0-114">实际值与预期值的绝对容差。</span><span class="sxs-lookup"><span data-stu-id="b46d0-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b46d0-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b46d0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

