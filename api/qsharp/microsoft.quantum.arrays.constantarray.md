---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696546"
---
# <a name="constantarray-function"></a><span data-ttu-id="4d9a7-102">ConstantArray 函数</span><span class="sxs-lookup"><span data-stu-id="4d9a7-102">ConstantArray function</span></span>

<span data-ttu-id="4d9a7-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4d9a7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4d9a7-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d9a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d9a7-105">创建一个给定长度的数组，其中的所有元素都等于给定的值。</span><span class="sxs-lookup"><span data-stu-id="4d9a7-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4d9a7-106">输入</span><span class="sxs-lookup"><span data-stu-id="4d9a7-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="4d9a7-107">长度： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d9a7-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d9a7-108">新数组的长度。</span><span class="sxs-lookup"><span data-stu-id="4d9a7-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="4d9a7-109">值： t</span><span class="sxs-lookup"><span data-stu-id="4d9a7-109">value : 'T</span></span>

<span data-ttu-id="4d9a7-110">新数组的每个元素的值。</span><span class="sxs-lookup"><span data-stu-id="4d9a7-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="4d9a7-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="4d9a7-111">Output : 'T[]</span></span>

<span data-ttu-id="4d9a7-112">一个新的长度数组 `length` ，使每个元素都是 `value` 。</span><span class="sxs-lookup"><span data-stu-id="4d9a7-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4d9a7-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="4d9a7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4d9a7-114">找</span><span class="sxs-lookup"><span data-stu-id="4d9a7-114">'T</span></span>

