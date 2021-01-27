---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855320"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="0cc39-102">SizeAdjustedTruthTable 函数</span><span class="sxs-lookup"><span data-stu-id="0cc39-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="0cc39-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0cc39-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0cc39-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0cc39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0cc39-105">根据变量的数量，根据布尔值数组调整事实数据表</span><span class="sxs-lookup"><span data-stu-id="0cc39-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="0cc39-106">返回长度为的新数组 `2^numVars` ，可能要求 `table` 使用条目扩展大小或将 `false` 其截断到 `2^numVars` 元素。</span><span class="sxs-lookup"><span data-stu-id="0cc39-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="0cc39-107">输入</span><span class="sxs-lookup"><span data-stu-id="0cc39-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="0cc39-108">table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="0cc39-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="0cc39-109">事实数据表作为真值数组</span><span class="sxs-lookup"><span data-stu-id="0cc39-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="0cc39-110">numVars： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0cc39-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0cc39-111">变量数</span><span class="sxs-lookup"><span data-stu-id="0cc39-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="0cc39-112">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="0cc39-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="0cc39-113">调整大小的事实数据表</span><span class="sxs-lookup"><span data-stu-id="0cc39-113">Size adjusted truth table</span></span>