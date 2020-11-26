---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 对角函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221532"
---
# <a name="diagonal-function"></a><span data-ttu-id="09b76-102">对角函数</span><span class="sxs-lookup"><span data-stu-id="09b76-102">Diagonal function</span></span>

<span data-ttu-id="09b76-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="09b76-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="09b76-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09b76-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09b76-105">返回二维数组的对角元素数组</span><span class="sxs-lookup"><span data-stu-id="09b76-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="09b76-106">描述</span><span class="sxs-lookup"><span data-stu-id="09b76-106">Description</span></span>

<span data-ttu-id="09b76-107">如果二维数组没有方形形状，则返回超出行数和列数的最小值。</span><span class="sxs-lookup"><span data-stu-id="09b76-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="09b76-108">输入</span><span class="sxs-lookup"><span data-stu-id="09b76-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="09b76-109">matrix： t [] []</span><span class="sxs-lookup"><span data-stu-id="09b76-109">matrix : 'T[][]</span></span>

<span data-ttu-id="09b76-110">按行顺序排列的二维矩阵</span><span class="sxs-lookup"><span data-stu-id="09b76-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="09b76-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="09b76-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="09b76-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="09b76-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09b76-113">找</span><span class="sxs-lookup"><span data-stu-id="09b76-113">'T</span></span>

<span data-ttu-id="09b76-114">的每个元素的类型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="09b76-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="09b76-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09b76-115">See Also</span></span>

- [<span data-ttu-id="09b76-116">。转换</span><span class="sxs-lookup"><span data-stu-id="09b76-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)