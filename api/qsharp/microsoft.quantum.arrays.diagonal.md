---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 对角函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842832"
---
# <a name="diagonal-function"></a><span data-ttu-id="79797-102">对角函数</span><span class="sxs-lookup"><span data-stu-id="79797-102">Diagonal function</span></span>

<span data-ttu-id="79797-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="79797-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="79797-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79797-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79797-105">返回二维数组的对角元素数组</span><span class="sxs-lookup"><span data-stu-id="79797-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="79797-106">说明</span><span class="sxs-lookup"><span data-stu-id="79797-106">Description</span></span>

<span data-ttu-id="79797-107">如果二维数组没有方形形状，则返回超出行数和列数的最小值。</span><span class="sxs-lookup"><span data-stu-id="79797-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="79797-108">输入</span><span class="sxs-lookup"><span data-stu-id="79797-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="79797-109">matrix： t [] []</span><span class="sxs-lookup"><span data-stu-id="79797-109">matrix : 'T[][]</span></span>

<span data-ttu-id="79797-110">按行顺序排列的二维矩阵</span><span class="sxs-lookup"><span data-stu-id="79797-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="79797-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="79797-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="79797-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="79797-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="79797-113">找</span><span class="sxs-lookup"><span data-stu-id="79797-113">'T</span></span>

<span data-ttu-id="79797-114">的每个元素的类型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="79797-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="79797-115">示例</span><span class="sxs-lookup"><span data-stu-id="79797-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="79797-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79797-116">See Also</span></span>

- [<span data-ttu-id="79797-117">。转换</span><span class="sxs-lookup"><span data-stu-id="79797-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)