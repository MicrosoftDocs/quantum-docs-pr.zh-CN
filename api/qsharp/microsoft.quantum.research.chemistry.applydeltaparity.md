---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851096"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="7d9b2-102">ApplyDeltaParity 操作</span><span class="sxs-lookup"><span data-stu-id="7d9b2-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="7d9b2-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7d9b2-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="7d9b2-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7d9b2-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="7d9b2-105">计算上一个 PQRS 之间的奇偶校验差异条款和下一 PQRS二项式.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="7d9b2-106">这种差异是在辅助 qubit 上计算的。</span><span class="sxs-lookup"><span data-stu-id="7d9b2-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7d9b2-107">输入</span><span class="sxs-lookup"><span data-stu-id="7d9b2-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="7d9b2-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7d9b2-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7d9b2-109">上一个 PQRS 的索引列表 .。。规定.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="7d9b2-110">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7d9b2-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7d9b2-111">下一个 PQRS 的索引列表 .。。规定.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="7d9b2-112">aux： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d9b2-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d9b2-113">辅助 qubit 将存储奇偶校验计算结果。</span><span class="sxs-lookup"><span data-stu-id="7d9b2-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7d9b2-114">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7d9b2-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7d9b2-115">Qubit 由所有 PQRS 进行操作 .。。规定.</span><span class="sxs-lookup"><span data-stu-id="7d9b2-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d9b2-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d9b2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7d9b2-117">备注</span><span class="sxs-lookup"><span data-stu-id="7d9b2-117">Remarks</span></span>

<span data-ttu-id="7d9b2-118">这假设 P < Q < R < S 的索引 < .。。适用于 prevPQ 和 nextPQ。</span><span class="sxs-lookup"><span data-stu-id="7d9b2-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>