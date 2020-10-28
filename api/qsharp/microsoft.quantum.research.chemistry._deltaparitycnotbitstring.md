---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695294"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="6baaf-102">_DeltaParityCNOTbitstring 函数</span><span class="sxs-lookup"><span data-stu-id="6baaf-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="6baaf-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6baaf-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="6baaf-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6baaf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6baaf-105">的传统处理步骤 `ApplyDeltaParity` 。</span><span class="sxs-lookup"><span data-stu-id="6baaf-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="6baaf-106">这会计算控制 qubits 的列表，用于评估任意两个 PQRS 之间的奇偶校验差异 .。。偶数的长度。</span><span class="sxs-lookup"><span data-stu-id="6baaf-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="6baaf-107">输入</span><span class="sxs-lookup"><span data-stu-id="6baaf-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="6baaf-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6baaf-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="6baaf-109">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6baaf-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="6baaf-110">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) </span><span class="sxs-lookup"><span data-stu-id="6baaf-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="6baaf-111">注解</span><span class="sxs-lookup"><span data-stu-id="6baaf-111">Remarks</span></span>

<span data-ttu-id="6baaf-112">这假定字词的长度为偶数。</span><span class="sxs-lookup"><span data-stu-id="6baaf-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="6baaf-113">计算任意两个字词之间的奇偶校验差异的控件列表。</span><span class="sxs-lookup"><span data-stu-id="6baaf-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="6baaf-114">这假定输入列表按升序排序。</span><span class="sxs-lookup"><span data-stu-id="6baaf-114">This assumes that the input lists is sorted in ascending order.</span></span>