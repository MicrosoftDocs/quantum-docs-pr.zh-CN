---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696711"
---
# <a name="realmod-function"></a><span data-ttu-id="f4e9a-102">RealMod 函数</span><span class="sxs-lookup"><span data-stu-id="f4e9a-102">RealMod function</span></span>

<span data-ttu-id="f4e9a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f4e9a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f4e9a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4e9a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4e9a-105">计算两个实数之间的模数。</span><span class="sxs-lookup"><span data-stu-id="f4e9a-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="f4e9a-106">输入</span><span class="sxs-lookup"><span data-stu-id="f4e9a-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="f4e9a-107">值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4e9a-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4e9a-108">一个实数 $x $ 来取的模数。</span><span class="sxs-lookup"><span data-stu-id="f4e9a-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="f4e9a-109">取模： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4e9a-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4e9a-110">要对其求 $x $ 的模数的实数。</span><span class="sxs-lookup"><span data-stu-id="f4e9a-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="f4e9a-111">minValue： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4e9a-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4e9a-112">此函数将返回的最小值。</span><span class="sxs-lookup"><span data-stu-id="f4e9a-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="f4e9a-113">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4e9a-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="f4e9a-114">注解</span><span class="sxs-lookup"><span data-stu-id="f4e9a-114">Remarks</span></span>

<span data-ttu-id="f4e9a-115">此函数通过包装关于单位圆的实际行，然后查找与输入对应的单位圆上的角度来计算实际的模数。</span><span class="sxs-lookup"><span data-stu-id="f4e9a-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="f4e9a-116">`minValue`然后，输入有效地指定要将单位圆剪切到何处。</span><span class="sxs-lookup"><span data-stu-id="f4e9a-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>