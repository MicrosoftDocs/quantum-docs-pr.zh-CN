---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210091"
---
# <a name="columnat-function"></a><span data-ttu-id="12a5c-102">ColumnAt 函数</span><span class="sxs-lookup"><span data-stu-id="12a5c-102">ColumnAt function</span></span>

<span data-ttu-id="12a5c-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="12a5c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="12a5c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12a5c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12a5c-105">提取矩阵中的列。</span><span class="sxs-lookup"><span data-stu-id="12a5c-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="12a5c-106">描述</span><span class="sxs-lookup"><span data-stu-id="12a5c-106">Description</span></span>

<span data-ttu-id="12a5c-107">此函数按行顺序提取矩阵中的列。</span><span class="sxs-lookup"><span data-stu-id="12a5c-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="12a5c-108">提取第一个索引的行 corrsponds 到元素的访问权限，因此无需进一步处理。</span><span class="sxs-lookup"><span data-stu-id="12a5c-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="12a5c-109">输入</span><span class="sxs-lookup"><span data-stu-id="12a5c-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="12a5c-110">列： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12a5c-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12a5c-111">矩阵的列</span><span class="sxs-lookup"><span data-stu-id="12a5c-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="12a5c-112">matrix： t [] []</span><span class="sxs-lookup"><span data-stu-id="12a5c-112">matrix : 'T[][]</span></span>

<span data-ttu-id="12a5c-113">按行顺序排列的二维矩阵</span><span class="sxs-lookup"><span data-stu-id="12a5c-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="12a5c-114">输出： t []</span><span class="sxs-lookup"><span data-stu-id="12a5c-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="12a5c-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="12a5c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="12a5c-116">找</span><span class="sxs-lookup"><span data-stu-id="12a5c-116">'T</span></span>

<span data-ttu-id="12a5c-117">的每个元素的类型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="12a5c-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="12a5c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12a5c-118">See Also</span></span>

- [<span data-ttu-id="12a5c-119">。转换</span><span class="sxs-lookup"><span data-stu-id="12a5c-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="12a5c-120">Microsoft 量子. 对角线</span><span class="sxs-lookup"><span data-stu-id="12a5c-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)