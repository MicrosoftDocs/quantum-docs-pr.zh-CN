---
uid: Microsoft.Quantum.Bitwise.Not
title: Not 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Not
qsharp.summary: Returns the bitwise NOT of an integer. This performs the same computation as the built-in `~~~` operator.
ms.openlocfilehash: 9c7642770c4f1db4878ccc1aba288fb9254e017e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842116"
---
# <a name="not-function"></a><span data-ttu-id="daba3-102">Not 函数</span><span class="sxs-lookup"><span data-stu-id="daba3-102">Not function</span></span>

<span data-ttu-id="daba3-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="daba3-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="daba3-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="daba3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="daba3-105">返回整数的按位 "非"。</span><span class="sxs-lookup"><span data-stu-id="daba3-105">Returns the bitwise NOT of an integer.</span></span>
<span data-ttu-id="daba3-106">这会执行与内置运算符相同的计算 `~~~` 。</span><span class="sxs-lookup"><span data-stu-id="daba3-106">This performs the same computation as the built-in `~~~` operator.</span></span>

```qsharp
function Not (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="daba3-107">输入</span><span class="sxs-lookup"><span data-stu-id="daba3-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="daba3-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="daba3-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="daba3-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="daba3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="daba3-110">示例</span><span class="sxs-lookup"><span data-stu-id="daba3-110">Example</span></span>

```qsharp
let a = 248;
let x = Not(a); // x : Int = -249, due to two's complement representation.
```

## <a name="remarks"></a><span data-ttu-id="daba3-111">备注</span><span class="sxs-lookup"><span data-stu-id="daba3-111">Remarks</span></span>

<span data-ttu-id="daba3-112">有关更多详细信息，请参阅 [c # ~ 运算符](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) 。</span><span class="sxs-lookup"><span data-stu-id="daba3-112">See the [C# ~ Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) for more details.</span></span>