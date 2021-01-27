---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: cb34078c09f8c28b5b9bbda1bae6936d13ffcc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854404"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="70bde-102">PrepareChoiState 操作</span><span class="sxs-lookup"><span data-stu-id="70bde-102">PrepareChoiState operation</span></span>

<span data-ttu-id="70bde-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="70bde-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="70bde-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70bde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70bde-105">将给定操作的 Choi – Jamiołkowski 状态准备到给定的引用和目标寄存器。</span><span class="sxs-lookup"><span data-stu-id="70bde-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="70bde-106">输入</span><span class="sxs-lookup"><span data-stu-id="70bde-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="70bde-107">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70bde-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="70bde-108">操作 $ \Lambda $，其 Choi – Jamiołkowski 状态 $J ( \Lambda) /2 ^ N $ 准备好，其中 $N $ 是其作用的 qubits 的数目 `op` 。</span><span class="sxs-lookup"><span data-stu-id="70bde-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="70bde-109">参考： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="70bde-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="70bde-110">以 $ \ket{00\cdots 0} $ 状态开头的 qubits 的寄存器，将用作操作的引用 `op` 。</span><span class="sxs-lookup"><span data-stu-id="70bde-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="70bde-111">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="70bde-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="70bde-112">最初在 $ \ket{00\cdots 0} $ 状态的 qubits 的寄存器，将应用该状态 `op` 。</span><span class="sxs-lookup"><span data-stu-id="70bde-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70bde-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70bde-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="70bde-114">备注</span><span class="sxs-lookup"><span data-stu-id="70bde-114">Remarks</span></span>

<span data-ttu-id="70bde-115">Choi – Jamiłkowski 状态 $J 量程进程的 ( \Lambda) $ 定义为 $ $ \begin{align} J ( \Lambda) \mathrel{： =} ( \boldone \otimes \Lambda)  (| \boldone\rangle \! \rangle\langle \! \langle\boldone |) ，\end{align} $ $ where $ |X\rangle \! \rangle $ 是列堆栈约定中的矩阵 $X $ 的 *矢量化* 。</span><span class="sxs-lookup"><span data-stu-id="70bde-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="70bde-116">了解此状态的传统说明会提供有关 $ \Lambda $ 对任意输入状态的影响的完整信息，并构成 *量程进程 tomography* 的基础。</span><span class="sxs-lookup"><span data-stu-id="70bde-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="70bde-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70bde-117">See Also</span></span>

- [<span data-ttu-id="70bde-118">PrepareChoiStateA。</span><span class="sxs-lookup"><span data-stu-id="70bde-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="70bde-119">PrepareChoiStateC。</span><span class="sxs-lookup"><span data-stu-id="70bde-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="70bde-120">PrepareChoiStateCA。</span><span class="sxs-lookup"><span data-stu-id="70bde-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)