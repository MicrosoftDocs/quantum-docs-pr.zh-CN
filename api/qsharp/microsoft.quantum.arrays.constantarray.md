---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210057"
---
# <a name="constantarray-function"></a><span data-ttu-id="fe905-102">ConstantArray 函数</span><span class="sxs-lookup"><span data-stu-id="fe905-102">ConstantArray function</span></span>

<span data-ttu-id="fe905-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fe905-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fe905-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe905-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe905-105">创建一个给定长度的数组，其中的所有元素都等于给定的值。</span><span class="sxs-lookup"><span data-stu-id="fe905-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="fe905-106">输入</span><span class="sxs-lookup"><span data-stu-id="fe905-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="fe905-107">长度： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fe905-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fe905-108">新数组的长度。</span><span class="sxs-lookup"><span data-stu-id="fe905-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="fe905-109">值： t</span><span class="sxs-lookup"><span data-stu-id="fe905-109">value : 'T</span></span>

<span data-ttu-id="fe905-110">新数组的每个元素的值。</span><span class="sxs-lookup"><span data-stu-id="fe905-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="fe905-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="fe905-111">Output : 'T[]</span></span>

<span data-ttu-id="fe905-112">一个新的长度数组 `length` ，使每个元素都是 `value` 。</span><span class="sxs-lookup"><span data-stu-id="fe905-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fe905-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="fe905-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fe905-114">找</span><span class="sxs-lookup"><span data-stu-id="fe905-114">'T</span></span>

