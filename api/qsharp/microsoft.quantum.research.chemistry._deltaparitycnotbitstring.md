---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226071"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="e5bf8-102">_DeltaParityCNOTbitstring 函数</span><span class="sxs-lookup"><span data-stu-id="e5bf8-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="e5bf8-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e5bf8-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="e5bf8-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e5bf8-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="e5bf8-105">的传统处理步骤 `ApplyDeltaParity` 。</span><span class="sxs-lookup"><span data-stu-id="e5bf8-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="e5bf8-106">这会计算控制 qubits 的列表，用于评估任意两个 PQRS 之间的奇偶校验差异 .。。偶数的长度。</span><span class="sxs-lookup"><span data-stu-id="e5bf8-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="e5bf8-107">输入</span><span class="sxs-lookup"><span data-stu-id="e5bf8-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="e5bf8-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e5bf8-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="e5bf8-109">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e5bf8-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="e5bf8-110">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) </span><span class="sxs-lookup"><span data-stu-id="e5bf8-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="e5bf8-111">备注</span><span class="sxs-lookup"><span data-stu-id="e5bf8-111">Remarks</span></span>

<span data-ttu-id="e5bf8-112">这假定字词的长度为偶数。</span><span class="sxs-lookup"><span data-stu-id="e5bf8-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="e5bf8-113">计算任意两个字词之间的奇偶校验差异的控件列表。</span><span class="sxs-lookup"><span data-stu-id="e5bf8-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="e5bf8-114">这假定输入列表按升序排序。</span><span class="sxs-lookup"><span data-stu-id="e5bf8-114">This assumes that the input lists is sorted in ascending order.</span></span>