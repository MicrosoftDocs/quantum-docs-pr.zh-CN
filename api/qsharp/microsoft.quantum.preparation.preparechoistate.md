---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700717"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="6ad41-102">PrepareChoiState 操作</span><span class="sxs-lookup"><span data-stu-id="6ad41-102">PrepareChoiState operation</span></span>

<span data-ttu-id="6ad41-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="6ad41-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="6ad41-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ad41-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ad41-105">将给定操作的 Choi – Jamiłkowski 状态准备到给定的引用和目标寄存器。</span><span class="sxs-lookup"><span data-stu-id="6ad41-105">Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6ad41-106">输入</span><span class="sxs-lookup"><span data-stu-id="6ad41-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="6ad41-107">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ad41-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6ad41-108">操作 $ \Lambda $，其 Choi – Jamiłkowski 状态 $J ( \Lambda) /2 ^ N $ 准备好，其中 $N $ 是其作用的 qubits 的数目 `op` 。</span><span class="sxs-lookup"><span data-stu-id="6ad41-108">Operation $\Lambda$ whose Choi–Jamiłkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="6ad41-109">参考： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6ad41-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6ad41-110">以 $ \ket{00\cdots 0} $ 状态开头的 qubits 的寄存器，将用作操作的引用 `op` 。</span><span class="sxs-lookup"><span data-stu-id="6ad41-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6ad41-111">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6ad41-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6ad41-112">最初在 $ \ket{00\cdots 0} $ 状态的 qubits 的寄存器，将应用该状态 `op` 。</span><span class="sxs-lookup"><span data-stu-id="6ad41-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ad41-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ad41-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6ad41-114">注解</span><span class="sxs-lookup"><span data-stu-id="6ad41-114">Remarks</span></span>

<span data-ttu-id="6ad41-115">Choi – Jamiłkowski 状态 $J 量程进程的 ( \Lambda) $ 定义为 $ $ \begin{align} J ( \Lambda) \mathrel{： =} ( \boldone \otimes \Lambda)  (| \boldone\rangle \! \rangle\langle \! \langle\boldone |) ，\end{align} $ $ where $ |X\rangle \! \rangle $ 是列堆栈约定中的矩阵 $X $ 的 *矢量化* 。</span><span class="sxs-lookup"><span data-stu-id="6ad41-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="6ad41-116">了解此状态的传统说明会提供有关 $ \Lambda $ 对任意输入状态的影响的完整信息，并构成 *量程进程 tomography* 的基础。</span><span class="sxs-lookup"><span data-stu-id="6ad41-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography* .</span></span>

## <a name="see-also"></a><span data-ttu-id="6ad41-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ad41-117">See Also</span></span>

- [<span data-ttu-id="6ad41-118">PrepareChoiStateA。</span><span class="sxs-lookup"><span data-stu-id="6ad41-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="6ad41-119">PrepareChoiStateC。</span><span class="sxs-lookup"><span data-stu-id="6ad41-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="6ad41-120">PrepareChoiStateCA。</span><span class="sxs-lookup"><span data-stu-id="6ad41-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)