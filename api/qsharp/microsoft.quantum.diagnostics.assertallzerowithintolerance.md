---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695607"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="9f6c2-102">AssertAllZeroWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="9f6c2-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="9f6c2-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9f6c2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9f6c2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f6c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f6c2-105">断言给定的 qubits 都处于 $ \ket {0} $ 状态，直到达到给定的容差。</span><span class="sxs-lookup"><span data-stu-id="9f6c2-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="9f6c2-106">输入</span><span class="sxs-lookup"><span data-stu-id="9f6c2-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="9f6c2-107">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9f6c2-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9f6c2-108">断言为 $ \ket {0} $ 状态的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="9f6c2-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="9f6c2-109">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9f6c2-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9f6c2-110">状态应为 $ \ket {0} $ 状态的精度</span><span class="sxs-lookup"><span data-stu-id="9f6c2-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f6c2-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f6c2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9f6c2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f6c2-112">See Also</span></span>

- [<span data-ttu-id="9f6c2-113">AssertQubitWithinTolerance。</span><span class="sxs-lookup"><span data-stu-id="9f6c2-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)