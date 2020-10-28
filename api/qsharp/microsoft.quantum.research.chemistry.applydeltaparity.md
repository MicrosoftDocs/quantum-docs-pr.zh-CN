---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700712"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="a1d85-102">ApplyDeltaParity 操作</span><span class="sxs-lookup"><span data-stu-id="a1d85-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="a1d85-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a1d85-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="a1d85-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1d85-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1d85-105">计算上一个 PQRS 之间的奇偶校验差异条款和下一 PQRS二项式.</span><span class="sxs-lookup"><span data-stu-id="a1d85-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="a1d85-106">这种差异是在辅助 qubit 上计算的。</span><span class="sxs-lookup"><span data-stu-id="a1d85-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a1d85-107">输入</span><span class="sxs-lookup"><span data-stu-id="a1d85-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="a1d85-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a1d85-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a1d85-109">上一个 PQRS 的索引列表 .。。规定.</span><span class="sxs-lookup"><span data-stu-id="a1d85-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="a1d85-110">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a1d85-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a1d85-111">下一个 PQRS 的索引列表 .。。规定.</span><span class="sxs-lookup"><span data-stu-id="a1d85-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="a1d85-112">aux： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a1d85-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a1d85-113">辅助 qubit 将存储奇偶校验计算结果。</span><span class="sxs-lookup"><span data-stu-id="a1d85-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a1d85-114">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a1d85-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a1d85-115">Qubit 由所有 PQRS 进行操作 .。。规定.</span><span class="sxs-lookup"><span data-stu-id="a1d85-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a1d85-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1d85-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a1d85-117">注解</span><span class="sxs-lookup"><span data-stu-id="a1d85-117">Remarks</span></span>

<span data-ttu-id="a1d85-118">这假设 P < Q < R < S 的索引 < .。。适用于 prevPQ 和 nextPQ。</span><span class="sxs-lookup"><span data-stu-id="a1d85-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>