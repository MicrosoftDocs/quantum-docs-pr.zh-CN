---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853691"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="b59b2-102">DrawRandomBool 操作</span><span class="sxs-lookup"><span data-stu-id="b59b2-102">DrawRandomBool operation</span></span>

<span data-ttu-id="b59b2-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b59b2-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b59b2-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b59b2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b59b2-105">如果获得成功概率，则返回一个在给定概率下为 true 的单个伯努利试用期。</span><span class="sxs-lookup"><span data-stu-id="b59b2-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b59b2-106">输入</span><span class="sxs-lookup"><span data-stu-id="b59b2-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="b59b2-107">successProbability： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b59b2-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b59b2-108">应返回的概率 `true` 。</span><span class="sxs-lookup"><span data-stu-id="b59b2-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b59b2-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="b59b2-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b59b2-110">`true` 具有概率 `successProbability` 和 `false` 有概率的 `1.0 - successProbability` 。</span><span class="sxs-lookup"><span data-stu-id="b59b2-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="b59b2-111">示例</span><span class="sxs-lookup"><span data-stu-id="b59b2-111">Example</span></span>

<span data-ttu-id="b59b2-112">以下 Q # 代码段示例从偏向硬币上翻：</span><span class="sxs-lookup"><span data-stu-id="b59b2-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```