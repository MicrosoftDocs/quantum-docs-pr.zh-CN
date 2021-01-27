---
uid: Microsoft.Quantum.Bitwise.Or
title: Or 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Or
qsharp.summary: Returns the bitwise OR of two integers. This performs the same computation as the built-in `|||` operator.
ms.openlocfilehash: 811e7cf64424e8302c5745c4c71d76de50ab8c08
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845266"
---
# <a name="or-function"></a><span data-ttu-id="6397a-102">Or 函数</span><span class="sxs-lookup"><span data-stu-id="6397a-102">Or function</span></span>

<span data-ttu-id="6397a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="6397a-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="6397a-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6397a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6397a-105">返回两个整数的按位 "或"。</span><span class="sxs-lookup"><span data-stu-id="6397a-105">Returns the bitwise OR of two integers.</span></span>
<span data-ttu-id="6397a-106">这会执行与内置运算符相同的计算 `|||` 。</span><span class="sxs-lookup"><span data-stu-id="6397a-106">This performs the same computation as the built-in `|||` operator.</span></span>

```qsharp
function Or (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="6397a-107">输入</span><span class="sxs-lookup"><span data-stu-id="6397a-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6397a-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6397a-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="6397a-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6397a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="6397a-110">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6397a-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="6397a-111">示例</span><span class="sxs-lookup"><span data-stu-id="6397a-111">Example</span></span>

```qsharp
let a = 248;      //                 11111000₂
let b = 63;       //                 00111111₂
let x = Or(a, b); // x : Int = 255 = 11111111₂.
```

## <a name="remarks"></a><span data-ttu-id="6397a-112">备注</span><span class="sxs-lookup"><span data-stu-id="6397a-112">Remarks</span></span>

<span data-ttu-id="6397a-113">请参阅 [c # |运算符](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) 了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="6397a-113">See the [C# | Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) for more details.</span></span>