---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848347"
---
# <a name="realmod-function"></a><span data-ttu-id="c83fc-102">RealMod 函数</span><span class="sxs-lookup"><span data-stu-id="c83fc-102">RealMod function</span></span>

<span data-ttu-id="c83fc-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c83fc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c83fc-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c83fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c83fc-105">计算两个实数之间的模数。</span><span class="sxs-lookup"><span data-stu-id="c83fc-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="c83fc-106">输入</span><span class="sxs-lookup"><span data-stu-id="c83fc-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="c83fc-107">值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c83fc-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c83fc-108">一个实数 $x $ 来取的模数。</span><span class="sxs-lookup"><span data-stu-id="c83fc-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="c83fc-109">取模： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c83fc-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c83fc-110">要对其求 $x $ 的模数的实数。</span><span class="sxs-lookup"><span data-stu-id="c83fc-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="c83fc-111">minValue： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c83fc-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c83fc-112">此函数将返回的最小值。</span><span class="sxs-lookup"><span data-stu-id="c83fc-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="c83fc-113">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c83fc-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="c83fc-114">示例</span><span class="sxs-lookup"><span data-stu-id="c83fc-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="c83fc-115">备注</span><span class="sxs-lookup"><span data-stu-id="c83fc-115">Remarks</span></span>

<span data-ttu-id="c83fc-116">此函数通过包装关于单位圆的实际行，然后查找与输入对应的单位圆上的角度来计算实际的模数。</span><span class="sxs-lookup"><span data-stu-id="c83fc-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="c83fc-117">`minValue`然后，输入有效地指定要将单位圆剪切到何处。</span><span class="sxs-lookup"><span data-stu-id="c83fc-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>