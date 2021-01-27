---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847607"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="a39ef-102">_DeltaParityCNOTbitstring 函数</span><span class="sxs-lookup"><span data-stu-id="a39ef-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="a39ef-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a39ef-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="a39ef-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a39ef-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="a39ef-105">的传统处理步骤 `ApplyDeltaParity` 。</span><span class="sxs-lookup"><span data-stu-id="a39ef-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="a39ef-106">这会计算控制 qubits 的列表，用于评估任意两个 PQRS 之间的奇偶校验差异 .。。偶数的长度。</span><span class="sxs-lookup"><span data-stu-id="a39ef-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="a39ef-107">输入</span><span class="sxs-lookup"><span data-stu-id="a39ef-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="a39ef-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a39ef-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="a39ef-109">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a39ef-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="a39ef-110">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) </span><span class="sxs-lookup"><span data-stu-id="a39ef-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="a39ef-111">备注</span><span class="sxs-lookup"><span data-stu-id="a39ef-111">Remarks</span></span>

<span data-ttu-id="a39ef-112">这假定字词的长度为偶数。</span><span class="sxs-lookup"><span data-stu-id="a39ef-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="a39ef-113">计算任意两个字词之间的奇偶校验差异的控件列表。</span><span class="sxs-lookup"><span data-stu-id="a39ef-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="a39ef-114">这假定输入列表按升序排序。</span><span class="sxs-lookup"><span data-stu-id="a39ef-114">This assumes that the input lists is sorted in ascending order.</span></span>