---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696552"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="7b83f-102">ColumnAtUnchecked 函数</span><span class="sxs-lookup"><span data-stu-id="7b83f-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="7b83f-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7b83f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7b83f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b83f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b83f-105">此函数不检查矩阵形状</span><span class="sxs-lookup"><span data-stu-id="7b83f-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="7b83f-106">说明</span><span class="sxs-lookup"><span data-stu-id="7b83f-106">Description</span></span>

<span data-ttu-id="7b83f-107">此函数可用于其他多维函数，这些函数已检查输入矩阵的有效矩形。</span><span class="sxs-lookup"><span data-stu-id="7b83f-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="7b83f-108">输入</span><span class="sxs-lookup"><span data-stu-id="7b83f-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="7b83f-109">列： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b83f-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="7b83f-110">matrix： t [] []</span><span class="sxs-lookup"><span data-stu-id="7b83f-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="7b83f-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="7b83f-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7b83f-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="7b83f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b83f-113">找</span><span class="sxs-lookup"><span data-stu-id="7b83f-113">'T</span></span>

