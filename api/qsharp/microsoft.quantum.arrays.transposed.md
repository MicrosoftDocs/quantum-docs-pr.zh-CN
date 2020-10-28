---
uid: Microsoft.Quantum.Arrays.Transposed
title: 转置函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696446"
---
# <a name="transposed-function"></a><span data-ttu-id="d3f2a-102">转置函数</span><span class="sxs-lookup"><span data-stu-id="d3f2a-102">Transposed function</span></span>

<span data-ttu-id="d3f2a-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d3f2a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d3f2a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3f2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3f2a-105">返回一个矩阵的换位，该矩阵表示为数组的数组。</span><span class="sxs-lookup"><span data-stu-id="d3f2a-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="d3f2a-106">说明</span><span class="sxs-lookup"><span data-stu-id="d3f2a-106">Description</span></span>

<span data-ttu-id="d3f2a-107">使用 $r $ rows 和 $c $ 列作为 $r \times c $ matrix 的输入。</span><span class="sxs-lookup"><span data-stu-id="d3f2a-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="d3f2a-108">矩阵是基于行的，即， `matrix[i][j]` 访问行 $i $ 和 column $j $ 的元素。</span><span class="sxs-lookup"><span data-stu-id="d3f2a-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="d3f2a-109">此函数返回作为输入矩阵换位的 $c \times r $ matrix。</span><span class="sxs-lookup"><span data-stu-id="d3f2a-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="d3f2a-110">输入</span><span class="sxs-lookup"><span data-stu-id="d3f2a-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="d3f2a-111">matrix： t [] []</span><span class="sxs-lookup"><span data-stu-id="d3f2a-111">matrix : 'T[][]</span></span>

<span data-ttu-id="d3f2a-112">基于行的 $r \times c $ matrix</span><span class="sxs-lookup"><span data-stu-id="d3f2a-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="d3f2a-113">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="d3f2a-113">Output : 'T[][]</span></span>

<span data-ttu-id="d3f2a-114">$C \times r $ matrix</span><span class="sxs-lookup"><span data-stu-id="d3f2a-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d3f2a-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="d3f2a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3f2a-116">找</span><span class="sxs-lookup"><span data-stu-id="d3f2a-116">'T</span></span>

<span data-ttu-id="d3f2a-117">的每个元素的类型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="d3f2a-117">The type of each element of `matrix`.</span></span>