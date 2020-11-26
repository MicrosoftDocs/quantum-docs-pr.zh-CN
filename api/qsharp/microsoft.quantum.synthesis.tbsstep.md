---
uid: Microsoft.Quantum.Synthesis.TBSStep
title: TBSStep 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TBSStep
qsharp.summary: Computes gate masks to transform perm[x] to x and updates the current permutation.
ms.openlocfilehash: 272ab3221e02127074fe6bfc65aee47c40eb88b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231052"
---
# <a name="tbsstep-function"></a><span data-ttu-id="bae0a-102">TBSStep 函数</span><span class="sxs-lookup"><span data-stu-id="bae0a-102">TBSStep function</span></span>

<span data-ttu-id="bae0a-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="bae0a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="bae0a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bae0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bae0a-105">计算用于将永久状态 [x] 转换为 x 并更新当前排列的入口掩码。</span><span class="sxs-lookup"><span data-stu-id="bae0a-105">Computes gate masks to transform perm[x] to x and updates the current permutation.</span></span>

```qsharp
function TBSStep (state : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[]), x : Int) : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[])
```


## <a name="input"></a><span data-ttu-id="bae0a-106">输入</span><span class="sxs-lookup"><span data-stu-id="bae0a-106">Input</span></span>

### <a name="state--intmcmtmask"></a><span data-ttu-id="bae0a-107">state： ([Int](xref:microsoft.quantum.lang-ref.int)[]，[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[] ) </span><span class="sxs-lookup"><span data-stu-id="bae0a-107">state : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>




### <a name="x--int"></a><span data-ttu-id="bae0a-108">x： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bae0a-108">x : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intmcmtmask"></a><span data-ttu-id="bae0a-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)[]，[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[] ) </span><span class="sxs-lookup"><span data-stu-id="bae0a-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>

