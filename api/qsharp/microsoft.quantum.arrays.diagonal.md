---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 对角函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696541"
---
# <a name="diagonal-function"></a><span data-ttu-id="4a291-102">对角函数</span><span class="sxs-lookup"><span data-stu-id="4a291-102">Diagonal function</span></span>

<span data-ttu-id="4a291-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4a291-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4a291-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a291-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a291-105">返回二维数组的对角元素数组</span><span class="sxs-lookup"><span data-stu-id="4a291-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="4a291-106">说明</span><span class="sxs-lookup"><span data-stu-id="4a291-106">Description</span></span>

<span data-ttu-id="4a291-107">如果二维数组没有方形形状，则返回超出行数和列数的最小值。</span><span class="sxs-lookup"><span data-stu-id="4a291-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="4a291-108">输入</span><span class="sxs-lookup"><span data-stu-id="4a291-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="4a291-109">matrix： t [] []</span><span class="sxs-lookup"><span data-stu-id="4a291-109">matrix : 'T[][]</span></span>

<span data-ttu-id="4a291-110">按行顺序排列的二维矩阵</span><span class="sxs-lookup"><span data-stu-id="4a291-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="4a291-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="4a291-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4a291-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="4a291-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a291-113">找</span><span class="sxs-lookup"><span data-stu-id="4a291-113">'T</span></span>

<span data-ttu-id="4a291-114">的每个元素的类型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="4a291-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a291-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a291-115">See Also</span></span>

- [<span data-ttu-id="4a291-116">。转换</span><span class="sxs-lookup"><span data-stu-id="4a291-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)