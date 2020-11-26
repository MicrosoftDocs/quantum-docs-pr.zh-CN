---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225748"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="25ffe-102">ApplyDeltaParity 操作</span><span class="sxs-lookup"><span data-stu-id="25ffe-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="25ffe-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="25ffe-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="25ffe-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="25ffe-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="25ffe-105">计算上一个 PQRS 之间的奇偶校验差异条款和下一 PQRS二项式.</span><span class="sxs-lookup"><span data-stu-id="25ffe-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="25ffe-106">这种差异是在辅助 qubit 上计算的。</span><span class="sxs-lookup"><span data-stu-id="25ffe-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="25ffe-107">输入</span><span class="sxs-lookup"><span data-stu-id="25ffe-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="25ffe-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="25ffe-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="25ffe-109">上一个 PQRS 的索引列表 .。。规定.</span><span class="sxs-lookup"><span data-stu-id="25ffe-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="25ffe-110">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="25ffe-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="25ffe-111">下一个 PQRS 的索引列表 .。。规定.</span><span class="sxs-lookup"><span data-stu-id="25ffe-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="25ffe-112">aux： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="25ffe-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="25ffe-113">辅助 qubit 将存储奇偶校验计算结果。</span><span class="sxs-lookup"><span data-stu-id="25ffe-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="25ffe-114">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="25ffe-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="25ffe-115">Qubit 由所有 PQRS 进行操作 .。。规定.</span><span class="sxs-lookup"><span data-stu-id="25ffe-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25ffe-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25ffe-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="25ffe-117">备注</span><span class="sxs-lookup"><span data-stu-id="25ffe-117">Remarks</span></span>

<span data-ttu-id="25ffe-118">这假设 P < Q < R < S 的索引 < .。。适用于 prevPQ 和 nextPQ。</span><span class="sxs-lookup"><span data-stu-id="25ffe-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>