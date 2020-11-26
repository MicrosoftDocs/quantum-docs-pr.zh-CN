---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194825"
---
# <a name="plusa-function"></a><span data-ttu-id="06a29-102">PlusA 函数</span><span class="sxs-lookup"><span data-stu-id="06a29-102">PlusA function</span></span>

<span data-ttu-id="06a29-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="06a29-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="06a29-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06a29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06a29-105">返回两个输入 (串联) 的总和。</span><span class="sxs-lookup"><span data-stu-id="06a29-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="06a29-106">输入</span><span class="sxs-lookup"><span data-stu-id="06a29-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="06a29-107">a： ' Element []</span><span class="sxs-lookup"><span data-stu-id="06a29-107">a : 'Element[]</span></span>

<span data-ttu-id="06a29-108">要求和 $a $ 的第一个输入。</span><span class="sxs-lookup"><span data-stu-id="06a29-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="06a29-109">b： "Element []</span><span class="sxs-lookup"><span data-stu-id="06a29-109">b : 'Element[]</span></span>

<span data-ttu-id="06a29-110">要求和 $b $ 的第二个输入。</span><span class="sxs-lookup"><span data-stu-id="06a29-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="06a29-111">Output： "Element []</span><span class="sxs-lookup"><span data-stu-id="06a29-111">Output : 'Element[]</span></span>

<span data-ttu-id="06a29-112">Sum $a + b $。</span><span class="sxs-lookup"><span data-stu-id="06a29-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="06a29-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="06a29-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="06a29-114">' 元素</span><span class="sxs-lookup"><span data-stu-id="06a29-114">'Element</span></span>

<span data-ttu-id="06a29-115">两个输入数组中每个元素的类型。</span><span class="sxs-lookup"><span data-stu-id="06a29-115">The type of each element in each of the two input arrays.</span></span>