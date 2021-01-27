---
uid: Microsoft.Quantum.Bitwise.Xor
title: Xor 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Xor
qsharp.summary: Returns the bitwise exclusive-OR (XOR) of two integers. This performs the same computation as the built-in `^^^` operator.
ms.openlocfilehash: ac31ba973ff06424dbd16168dac14a79b2691b3f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842086"
---
# <a name="xor-function"></a><span data-ttu-id="7b65e-102">Xor 函数</span><span class="sxs-lookup"><span data-stu-id="7b65e-102">Xor function</span></span>

<span data-ttu-id="7b65e-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="7b65e-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="7b65e-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7b65e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7b65e-105">返回两个整数的按位异或 (XOR) 。</span><span class="sxs-lookup"><span data-stu-id="7b65e-105">Returns the bitwise exclusive-OR (XOR) of two integers.</span></span>
<span data-ttu-id="7b65e-106">这会执行与内置运算符相同的计算 `^^^` 。</span><span class="sxs-lookup"><span data-stu-id="7b65e-106">This performs the same computation as the built-in `^^^` operator.</span></span>

```qsharp
function Xor (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="7b65e-107">输入</span><span class="sxs-lookup"><span data-stu-id="7b65e-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="7b65e-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b65e-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="7b65e-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b65e-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="7b65e-110">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b65e-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="7b65e-111">示例</span><span class="sxs-lookup"><span data-stu-id="7b65e-111">Example</span></span>

```qsharp
let a = 248;       //                 11111000₂
let b = 63;        //                 00111111₂
let x = Xor(a, b); // x : Int = 199 = 11000111₂.
```

## <a name="remarks"></a><span data-ttu-id="7b65e-112">备注</span><span class="sxs-lookup"><span data-stu-id="7b65e-112">Remarks</span></span>

<span data-ttu-id="7b65e-113">有关更多详细信息，请参阅 [c # ^ 运算符](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) 。</span><span class="sxs-lookup"><span data-stu-id="7b65e-113">See the [C# ^ Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) for more details.</span></span>