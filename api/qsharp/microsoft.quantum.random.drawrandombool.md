---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696690"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="840e1-102">DrawRandomBool 操作</span><span class="sxs-lookup"><span data-stu-id="840e1-102">DrawRandomBool operation</span></span>

<span data-ttu-id="840e1-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="840e1-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="840e1-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="840e1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="840e1-105">如果获得成功概率，则返回一个在给定概率下为 true 的单个伯努利试用期。</span><span class="sxs-lookup"><span data-stu-id="840e1-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="840e1-106">输入</span><span class="sxs-lookup"><span data-stu-id="840e1-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="840e1-107">successProbability： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="840e1-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="840e1-108">应返回的概率 `true` 。</span><span class="sxs-lookup"><span data-stu-id="840e1-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="840e1-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="840e1-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="840e1-110">`true` 具有概率 `successProbability` 和 `false` 有概率的 `1.0 - successProbability` 。</span><span class="sxs-lookup"><span data-stu-id="840e1-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>