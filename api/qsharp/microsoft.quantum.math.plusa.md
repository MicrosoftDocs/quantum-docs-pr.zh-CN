---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695116"
---
# <a name="plusa-function"></a><span data-ttu-id="63b99-102">PlusA 函数</span><span class="sxs-lookup"><span data-stu-id="63b99-102">PlusA function</span></span>

<span data-ttu-id="63b99-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="63b99-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="63b99-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63b99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63b99-105">返回两个输入 (串联) 的总和。</span><span class="sxs-lookup"><span data-stu-id="63b99-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="63b99-106">输入</span><span class="sxs-lookup"><span data-stu-id="63b99-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="63b99-107">a： ' Element []</span><span class="sxs-lookup"><span data-stu-id="63b99-107">a : 'Element[]</span></span>

<span data-ttu-id="63b99-108">要求和 $a $ 的第一个输入。</span><span class="sxs-lookup"><span data-stu-id="63b99-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="63b99-109">b： "Element []</span><span class="sxs-lookup"><span data-stu-id="63b99-109">b : 'Element[]</span></span>

<span data-ttu-id="63b99-110">要求和 $b $ 的第二个输入。</span><span class="sxs-lookup"><span data-stu-id="63b99-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="63b99-111">Output： "Element []</span><span class="sxs-lookup"><span data-stu-id="63b99-111">Output : 'Element[]</span></span>

<span data-ttu-id="63b99-112">Sum $a + b $。</span><span class="sxs-lookup"><span data-stu-id="63b99-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63b99-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="63b99-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="63b99-114">' 元素</span><span class="sxs-lookup"><span data-stu-id="63b99-114">'Element</span></span>

<span data-ttu-id="63b99-115">两个输入数组中每个元素的类型。</span><span class="sxs-lookup"><span data-stu-id="63b99-115">The type of each element in each of the two input arrays.</span></span>