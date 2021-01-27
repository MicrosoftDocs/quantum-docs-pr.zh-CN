---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846226"
---
# <a name="constantarray-function"></a><span data-ttu-id="c3f3f-102">ConstantArray 函数</span><span class="sxs-lookup"><span data-stu-id="c3f3f-102">ConstantArray function</span></span>

<span data-ttu-id="c3f3f-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c3f3f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c3f3f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3f3f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3f3f-105">创建一个给定长度的数组，其中的所有元素都等于给定的值。</span><span class="sxs-lookup"><span data-stu-id="c3f3f-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c3f3f-106">输入</span><span class="sxs-lookup"><span data-stu-id="c3f3f-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="c3f3f-107">长度： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3f3f-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3f3f-108">新数组的长度。</span><span class="sxs-lookup"><span data-stu-id="c3f3f-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="c3f3f-109">值： t</span><span class="sxs-lookup"><span data-stu-id="c3f3f-109">value : 'T</span></span>

<span data-ttu-id="c3f3f-110">新数组的每个元素的值。</span><span class="sxs-lookup"><span data-stu-id="c3f3f-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="c3f3f-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="c3f3f-111">Output : 'T[]</span></span>

<span data-ttu-id="c3f3f-112">一个新的长度数组 `length` ，使每个元素都是 `value` 。</span><span class="sxs-lookup"><span data-stu-id="c3f3f-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3f3f-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="c3f3f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3f3f-114">找</span><span class="sxs-lookup"><span data-stu-id="c3f3f-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="c3f3f-115">示例</span><span class="sxs-lookup"><span data-stu-id="c3f3f-115">Example</span></span>

<span data-ttu-id="c3f3f-116">下面的代码创建一个具有3个布尔值的数组，每个数组等于 `true` ：</span><span class="sxs-lookup"><span data-stu-id="c3f3f-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```