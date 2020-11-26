---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203308"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="b8d33-102">ApplyTransposition 操作</span><span class="sxs-lookup"><span data-stu-id="b8d33-102">ApplyTransposition operation</span></span>

<span data-ttu-id="b8d33-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b8d33-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b8d33-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8d33-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b8d33-105">描述</span><span class="sxs-lookup"><span data-stu-id="b8d33-105">Description</span></span>

<span data-ttu-id="b8d33-106">此操作将索引中的波幅替换 `a` 为 `b` 长度为 $n $ 的给定状态向量的索引中的波幅 `register` 。</span><span class="sxs-lookup"><span data-stu-id="b8d33-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="b8d33-107">如果 `a` 等于 `b` ，则不更改状态向量。</span><span class="sxs-lookup"><span data-stu-id="b8d33-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="b8d33-108">输入</span><span class="sxs-lookup"><span data-stu-id="b8d33-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b8d33-109">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b8d33-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b8d33-110">第一个索引 (的值必须介于0到 $ 2 ^ n-$1) </span><span class="sxs-lookup"><span data-stu-id="b8d33-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="b8d33-111">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b8d33-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b8d33-112">第二个索引 (的值必须介于0到 $ 2 ^ n-$1) </span><span class="sxs-lookup"><span data-stu-id="b8d33-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="b8d33-113">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b8d33-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b8d33-114">要向其应用调换的 $n $ qubits 的列表。</span><span class="sxs-lookup"><span data-stu-id="b8d33-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b8d33-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b8d33-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

