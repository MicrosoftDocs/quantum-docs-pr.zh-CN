---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701077"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="f909d-102">ApplyTransposition 操作</span><span class="sxs-lookup"><span data-stu-id="f909d-102">ApplyTransposition operation</span></span>

<span data-ttu-id="f909d-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f909d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f909d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f909d-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="f909d-105">说明</span><span class="sxs-lookup"><span data-stu-id="f909d-105">Description</span></span>

<span data-ttu-id="f909d-106">此操作将索引中的波幅替换 `a` 为 `b` 长度为 $n $ 的给定状态向量的索引中的波幅 `register` 。</span><span class="sxs-lookup"><span data-stu-id="f909d-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="f909d-107">如果 `a` 等于 `b` ，则不更改状态向量。</span><span class="sxs-lookup"><span data-stu-id="f909d-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="f909d-108">输入</span><span class="sxs-lookup"><span data-stu-id="f909d-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f909d-109">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f909d-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f909d-110">第一个索引 (的值必须介于0到 $ 2 ^ n-$1) </span><span class="sxs-lookup"><span data-stu-id="f909d-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="f909d-111">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f909d-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f909d-112">第二个索引 (的值必须介于0到 $ 2 ^ n-$1) </span><span class="sxs-lookup"><span data-stu-id="f909d-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f909d-113">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f909d-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f909d-114">要向其应用调换的 $n $ qubits 的列表。</span><span class="sxs-lookup"><span data-stu-id="f909d-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f909d-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f909d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

