---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 4f4631bb49f769816a3df772f7b2f346c8ccfc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842859"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="2b5ef-102">ColumnAtUnchecked 函数</span><span class="sxs-lookup"><span data-stu-id="2b5ef-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="2b5ef-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2b5ef-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2b5ef-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b5ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b5ef-105">此函数不检查矩阵形状</span><span class="sxs-lookup"><span data-stu-id="2b5ef-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="2b5ef-106">说明</span><span class="sxs-lookup"><span data-stu-id="2b5ef-106">Description</span></span>

<span data-ttu-id="2b5ef-107">此函数可用于其他多维函数，这些函数已检查输入矩阵的有效矩形。</span><span class="sxs-lookup"><span data-stu-id="2b5ef-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="2b5ef-108">输入</span><span class="sxs-lookup"><span data-stu-id="2b5ef-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="2b5ef-109">列： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b5ef-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="2b5ef-110">matrix： t [] []</span><span class="sxs-lookup"><span data-stu-id="2b5ef-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="2b5ef-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="2b5ef-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2b5ef-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="2b5ef-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2b5ef-113">找</span><span class="sxs-lookup"><span data-stu-id="2b5ef-113">'T</span></span>

