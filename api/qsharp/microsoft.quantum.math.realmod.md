---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228247"
---
# <a name="realmod-function"></a><span data-ttu-id="99dfe-102">RealMod 函数</span><span class="sxs-lookup"><span data-stu-id="99dfe-102">RealMod function</span></span>

<span data-ttu-id="99dfe-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="99dfe-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="99dfe-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99dfe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99dfe-105">计算两个实数之间的模数。</span><span class="sxs-lookup"><span data-stu-id="99dfe-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="99dfe-106">输入</span><span class="sxs-lookup"><span data-stu-id="99dfe-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="99dfe-107">值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="99dfe-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="99dfe-108">一个实数 $x $ 来取的模数。</span><span class="sxs-lookup"><span data-stu-id="99dfe-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="99dfe-109">取模： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="99dfe-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="99dfe-110">要对其求 $x $ 的模数的实数。</span><span class="sxs-lookup"><span data-stu-id="99dfe-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="99dfe-111">minValue： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="99dfe-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="99dfe-112">此函数将返回的最小值。</span><span class="sxs-lookup"><span data-stu-id="99dfe-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="99dfe-113">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="99dfe-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="99dfe-114">备注</span><span class="sxs-lookup"><span data-stu-id="99dfe-114">Remarks</span></span>

<span data-ttu-id="99dfe-115">此函数通过包装关于单位圆的实际行，然后查找与输入对应的单位圆上的角度来计算实际的模数。</span><span class="sxs-lookup"><span data-stu-id="99dfe-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="99dfe-116">`minValue`然后，输入有效地指定要将单位圆剪切到何处。</span><span class="sxs-lookup"><span data-stu-id="99dfe-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>