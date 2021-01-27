---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 281855ec79d280c903ebb4d05614081767840778
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830860"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="9e295-102">AssertAllZeroWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="9e295-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="9e295-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9e295-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9e295-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9e295-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9e295-105">断言给定的 qubits 都处于 $ \ket {0} $ 状态，直到达到给定的容差。</span><span class="sxs-lookup"><span data-stu-id="9e295-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9e295-106">输入</span><span class="sxs-lookup"><span data-stu-id="9e295-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="9e295-107">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9e295-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9e295-108">断言为 $ \ket {0} $ 状态的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="9e295-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="9e295-109">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9e295-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9e295-110">状态应为 $ \ket {0} $ 状态的精度</span><span class="sxs-lookup"><span data-stu-id="9e295-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e295-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e295-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9e295-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e295-112">See Also</span></span>

- [<span data-ttu-id="9e295-113">AssertQubitWithinTolerance。</span><span class="sxs-lookup"><span data-stu-id="9e295-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)