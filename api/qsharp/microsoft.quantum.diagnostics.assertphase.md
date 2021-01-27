---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830084"
---
# <a name="assertphase-operation"></a><span data-ttu-id="1514f-102">AssertPhase 操作</span><span class="sxs-lookup"><span data-stu-id="1514f-102">AssertPhase operation</span></span>

<span data-ttu-id="1514f-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1514f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1514f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1514f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1514f-105">断言 superposition 状态相同的阶段具有预期值。</span><span class="sxs-lookup"><span data-stu-id="1514f-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="1514f-106">说明</span><span class="sxs-lookup"><span data-stu-id="1514f-106">Description</span></span>

<span data-ttu-id="1514f-107">此操作断言对于一些任意实 $t $，可以表示为 $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ 票证 {0} + e ^ {-i\phi} \ 票证) $ 的阶段 $ \phi $ {1} 具有预期值。</span><span class="sxs-lookup"><span data-stu-id="1514f-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="1514f-108">输入</span><span class="sxs-lookup"><span data-stu-id="1514f-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="1514f-109">应为： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1514f-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1514f-110">$ \Phi \in 的预期值 (-\pi，\pi] $。</span><span class="sxs-lookup"><span data-stu-id="1514f-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="1514f-111">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1514f-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1514f-112">存储预期状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="1514f-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="1514f-113">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1514f-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1514f-114">实际值与预期值的绝对容差。</span><span class="sxs-lookup"><span data-stu-id="1514f-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1514f-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1514f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="1514f-116">示例</span><span class="sxs-lookup"><span data-stu-id="1514f-116">Example</span></span>

<span data-ttu-id="1514f-117">以下断言成功： `qubit` 处于状态 $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ 票证 {0} + e ^ {i 0.5} \ sqrt {1/2} \ 票证 {1} $;</span><span class="sxs-lookup"><span data-stu-id="1514f-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="1514f-118">`qubit` 处于状态 $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ 票证 {0} + e ^ {-i 0.5} \ sqrt {1/2} \ 票证 {1} $;</span><span class="sxs-lookup"><span data-stu-id="1514f-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="1514f-119">`qubit` 处于状态 $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ 票证 {0} + e ^ {i 0.2} \ sqrt {1/2} \ 票证 {1} $;</span><span class="sxs-lookup"><span data-stu-id="1514f-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`