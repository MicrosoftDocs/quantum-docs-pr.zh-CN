---
uid: Microsoft.Quantum.Bitwise.And
title: And 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: And
qsharp.summary: Returns the bitwise AND of two integers. This performs the same computation as the built-in `&&&` operator.
ms.openlocfilehash: 56eae4ef222a6593fd97966a9af21d559f613bc3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842163"
---
# <a name="and-function"></a><span data-ttu-id="f6fd6-102">And 函数</span><span class="sxs-lookup"><span data-stu-id="f6fd6-102">And function</span></span>

<span data-ttu-id="f6fd6-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="f6fd6-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="f6fd6-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f6fd6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f6fd6-105">返回两个整数的按位 "与"。</span><span class="sxs-lookup"><span data-stu-id="f6fd6-105">Returns the bitwise AND of two integers.</span></span>
<span data-ttu-id="f6fd6-106">这会执行与内置运算符相同的计算 `&&&` 。</span><span class="sxs-lookup"><span data-stu-id="f6fd6-106">This performs the same computation as the built-in `&&&` operator.</span></span>

```qsharp
function And (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f6fd6-107">输入</span><span class="sxs-lookup"><span data-stu-id="f6fd6-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f6fd6-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f6fd6-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="f6fd6-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f6fd6-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="f6fd6-110">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f6fd6-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="f6fd6-111">示例</span><span class="sxs-lookup"><span data-stu-id="f6fd6-111">Example</span></span>

```qsharp
let a = 248;       //                11111000₂
let b = 63;        //                00111111₂
let x = And(a, b); // x : Int = 56 = 00111000₂.
```

## <a name="remarks"></a><span data-ttu-id="f6fd6-112">备注</span><span class="sxs-lookup"><span data-stu-id="f6fd6-112">Remarks</span></span>

<span data-ttu-id="f6fd6-113">有关更多详细信息，请参阅 [c # &amp; 运算符](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (二进制) 。</span><span class="sxs-lookup"><span data-stu-id="f6fd6-113">See the [C# &amp; Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (binary) for more details.</span></span>