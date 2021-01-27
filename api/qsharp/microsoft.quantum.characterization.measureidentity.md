---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851813"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="b5866-102">MeasureIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="b5866-102">MeasureIdentity operation</span></span>

<span data-ttu-id="b5866-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="b5866-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="b5866-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5866-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5866-105">测量 qubits 的寄存器上的标识运算符。</span><span class="sxs-lookup"><span data-stu-id="b5866-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="b5866-106">输入</span><span class="sxs-lookup"><span data-stu-id="b5866-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="b5866-107">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b5866-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b5866-108">要测量的寄存器。</span><span class="sxs-lookup"><span data-stu-id="b5866-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="b5866-109">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b5866-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="b5866-110">结果值 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="b5866-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5866-111">备注</span><span class="sxs-lookup"><span data-stu-id="b5866-111">Remarks</span></span>

<span data-ttu-id="b5866-112">由于 $ \boldone $ 只有 eigenvalue $1 $，并且没有负 eigenvalue，此操作始终返回 `Zero` ，对应于 eigenvalue $ + 1 = (-1) ^ $0，而不会导致的状态折叠 `register` 。</span><span class="sxs-lookup"><span data-stu-id="b5866-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="b5866-113">此操作本身并不有用，但在进程 tomography 的上下文中很有用，因为它提供了有关量程进程的跟踪保存的信息。</span><span class="sxs-lookup"><span data-stu-id="b5866-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="b5866-114">特别是，具有有损度量的目标计算机应将此操作替换为 $ \boldone $ 的实际度量值。</span><span class="sxs-lookup"><span data-stu-id="b5866-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>