---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192955"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="51d1b-102">DrawRandomBool 操作</span><span class="sxs-lookup"><span data-stu-id="51d1b-102">DrawRandomBool operation</span></span>

<span data-ttu-id="51d1b-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="51d1b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="51d1b-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="51d1b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="51d1b-105">如果获得成功概率，则返回一个在给定概率下为 true 的单个伯努利试用期。</span><span class="sxs-lookup"><span data-stu-id="51d1b-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="51d1b-106">输入</span><span class="sxs-lookup"><span data-stu-id="51d1b-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="51d1b-107">successProbability： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="51d1b-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="51d1b-108">应返回的概率 `true` 。</span><span class="sxs-lookup"><span data-stu-id="51d1b-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="51d1b-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="51d1b-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="51d1b-110">`true` 具有概率 `successProbability` 和 `false` 有概率的 `1.0 - successProbability` 。</span><span class="sxs-lookup"><span data-stu-id="51d1b-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>