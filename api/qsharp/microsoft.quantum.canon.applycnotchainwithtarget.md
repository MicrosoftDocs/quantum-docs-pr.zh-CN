---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696371"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="766eb-102">ApplyCNOTChainWithTarget 操作</span><span class="sxs-lookup"><span data-stu-id="766eb-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="766eb-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="766eb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="766eb-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="766eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="766eb-105">计算 qubits 数组到目标 qubit 的奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="766eb-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="766eb-106">说明</span><span class="sxs-lookup"><span data-stu-id="766eb-106">Description</span></span>

<span data-ttu-id="766eb-107">如果数组最初处于状态 $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{target}}} $，则最终状态由 $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{target}}} $。</span><span class="sxs-lookup"><span data-stu-id="766eb-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="766eb-108">输入</span><span class="sxs-lookup"><span data-stu-id="766eb-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="766eb-109">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="766eb-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="766eb-110">计算其奇偶校验的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="766eb-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="766eb-111">targetQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="766eb-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="766eb-112">"Qubits" 的奇偶校验的最终 qubit 为 XORed。</span><span class="sxs-lookup"><span data-stu-id="766eb-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="766eb-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="766eb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="766eb-114">注解</span><span class="sxs-lookup"><span data-stu-id="766eb-114">Remarks</span></span>

<span data-ttu-id="766eb-115">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="766eb-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="766eb-116">和</span><span class="sxs-lookup"><span data-stu-id="766eb-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```