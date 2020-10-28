---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696553"
---
# <a name="columnat-function"></a><span data-ttu-id="a0835-102">ColumnAt 函数</span><span class="sxs-lookup"><span data-stu-id="a0835-102">ColumnAt function</span></span>

<span data-ttu-id="a0835-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a0835-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a0835-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a0835-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a0835-105">提取矩阵中的列。</span><span class="sxs-lookup"><span data-stu-id="a0835-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="a0835-106">说明</span><span class="sxs-lookup"><span data-stu-id="a0835-106">Description</span></span>

<span data-ttu-id="a0835-107">此函数按行顺序提取矩阵中的列。</span><span class="sxs-lookup"><span data-stu-id="a0835-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="a0835-108">提取第一个索引的行 corrsponds 到元素的访问权限，因此无需进一步处理。</span><span class="sxs-lookup"><span data-stu-id="a0835-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="a0835-109">输入</span><span class="sxs-lookup"><span data-stu-id="a0835-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="a0835-110">列： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a0835-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a0835-111">矩阵的列</span><span class="sxs-lookup"><span data-stu-id="a0835-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="a0835-112">matrix： t [] []</span><span class="sxs-lookup"><span data-stu-id="a0835-112">matrix : 'T[][]</span></span>

<span data-ttu-id="a0835-113">按行顺序排列的二维矩阵</span><span class="sxs-lookup"><span data-stu-id="a0835-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="a0835-114">输出： t []</span><span class="sxs-lookup"><span data-stu-id="a0835-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a0835-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="a0835-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a0835-116">找</span><span class="sxs-lookup"><span data-stu-id="a0835-116">'T</span></span>

<span data-ttu-id="a0835-117">的每个元素的类型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="a0835-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0835-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0835-118">See Also</span></span>

- [<span data-ttu-id="a0835-119">。转换</span><span class="sxs-lookup"><span data-stu-id="a0835-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="a0835-120">Microsoft 量子. 对角线</span><span class="sxs-lookup"><span data-stu-id="a0835-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)