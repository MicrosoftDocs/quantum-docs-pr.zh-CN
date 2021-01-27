---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842705"
---
# <a name="plusa-function"></a><span data-ttu-id="bba38-102">PlusA 函数</span><span class="sxs-lookup"><span data-stu-id="bba38-102">PlusA function</span></span>

<span data-ttu-id="bba38-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="bba38-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="bba38-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bba38-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bba38-105">返回两个输入 (串联) 的总和。</span><span class="sxs-lookup"><span data-stu-id="bba38-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="bba38-106">输入</span><span class="sxs-lookup"><span data-stu-id="bba38-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="bba38-107">a： ' Element []</span><span class="sxs-lookup"><span data-stu-id="bba38-107">a : 'Element[]</span></span>

<span data-ttu-id="bba38-108">要求和 $a $ 的第一个输入。</span><span class="sxs-lookup"><span data-stu-id="bba38-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="bba38-109">b： "Element []</span><span class="sxs-lookup"><span data-stu-id="bba38-109">b : 'Element[]</span></span>

<span data-ttu-id="bba38-110">要求和 $b $ 的第二个输入。</span><span class="sxs-lookup"><span data-stu-id="bba38-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="bba38-111">Output： "Element []</span><span class="sxs-lookup"><span data-stu-id="bba38-111">Output : 'Element[]</span></span>

<span data-ttu-id="bba38-112">Sum $a + b $。</span><span class="sxs-lookup"><span data-stu-id="bba38-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bba38-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="bba38-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="bba38-114">' 元素</span><span class="sxs-lookup"><span data-stu-id="bba38-114">'Element</span></span>

<span data-ttu-id="bba38-115">两个输入数组中每个元素的类型。</span><span class="sxs-lookup"><span data-stu-id="bba38-115">The type of each element in each of the two input arrays.</span></span>