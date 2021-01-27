---
uid: Microsoft.Quantum.Synthesis.TBSStep
title: TBSStep 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TBSStep
qsharp.summary: Computes gate masks to transform perm[x] to x and updates the current permutation.
ms.openlocfilehash: 8980cd359c2159d875444acb727290d1dc9a1b38
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855293"
---
# <a name="tbsstep-function"></a><span data-ttu-id="be47d-102">TBSStep 函数</span><span class="sxs-lookup"><span data-stu-id="be47d-102">TBSStep function</span></span>

<span data-ttu-id="be47d-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="be47d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="be47d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be47d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be47d-105">计算用于将永久状态 [x] 转换为 x 并更新当前排列的入口掩码。</span><span class="sxs-lookup"><span data-stu-id="be47d-105">Computes gate masks to transform perm[x] to x and updates the current permutation.</span></span>

```qsharp
function TBSStep (state : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[]), x : Int) : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[])
```


## <a name="input"></a><span data-ttu-id="be47d-106">输入</span><span class="sxs-lookup"><span data-stu-id="be47d-106">Input</span></span>

### <a name="state--intmcmtmask"></a><span data-ttu-id="be47d-107">state： ([Int](xref:microsoft.quantum.lang-ref.int)[]，[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[] ) </span><span class="sxs-lookup"><span data-stu-id="be47d-107">state : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>




### <a name="x--int"></a><span data-ttu-id="be47d-108">x： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be47d-108">x : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intmcmtmask"></a><span data-ttu-id="be47d-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)[]，[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[] ) </span><span class="sxs-lookup"><span data-stu-id="be47d-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>

