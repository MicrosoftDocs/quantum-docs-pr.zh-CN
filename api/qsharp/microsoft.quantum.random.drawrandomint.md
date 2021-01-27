---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851142"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="f1923-102">DrawRandomInt 操作</span><span class="sxs-lookup"><span data-stu-id="f1923-102">DrawRandomInt operation</span></span>

<span data-ttu-id="f1923-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f1923-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f1923-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f1923-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f1923-105">绘制给定范围内的随机整数。</span><span class="sxs-lookup"><span data-stu-id="f1923-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f1923-106">输入</span><span class="sxs-lookup"><span data-stu-id="f1923-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="f1923-107">min： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1923-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1923-108">要绘制的最小整数。</span><span class="sxs-lookup"><span data-stu-id="f1923-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="f1923-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1923-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1923-110">要绘制的最大整数。</span><span class="sxs-lookup"><span data-stu-id="f1923-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="f1923-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1923-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1923-112">中从到的一个整数，其值 `min` 为 `max` 统一的概率。</span><span class="sxs-lookup"><span data-stu-id="f1923-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="f1923-113">示例</span><span class="sxs-lookup"><span data-stu-id="f1923-113">Example</span></span>

<span data-ttu-id="f1923-114">以下 Q # 代码段随机滚动六面骰子：</span><span class="sxs-lookup"><span data-stu-id="f1923-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="f1923-115">备注</span><span class="sxs-lookup"><span data-stu-id="f1923-115">Remarks</span></span>

<span data-ttu-id="f1923-116">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="f1923-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1923-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1923-117">See Also</span></span>

- [<span data-ttu-id="f1923-118">DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="f1923-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)