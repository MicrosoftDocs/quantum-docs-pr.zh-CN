---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200877"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="4ba78-102">FiveQubitCode 函数</span><span class="sxs-lookup"><span data-stu-id="4ba78-102">FiveQubitCode function</span></span>

<span data-ttu-id="4ba78-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4ba78-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4ba78-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ba78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ba78-105">返回一个 QECC 值，该值表示⟦5、1、3⟧代码编码器和解码器，并提供就地的症状度量。</span><span class="sxs-lookup"><span data-stu-id="4ba78-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="4ba78-106">输出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="4ba78-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="4ba78-107">通过指定类型返回量程错误更正代码的实现 `QECC` 。</span><span class="sxs-lookup"><span data-stu-id="4ba78-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ba78-108">备注</span><span class="sxs-lookup"><span data-stu-id="4ba78-108">Remarks</span></span>

<span data-ttu-id="4ba78-109">以下两篇文章中单独找到了此代码：</span><span class="sxs-lookup"><span data-stu-id="4ba78-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="4ba78-110">C.</span><span class="sxs-lookup"><span data-stu-id="4ba78-110">C.</span></span> <span data-ttu-id="4ba78-111">H.</span><span class="sxs-lookup"><span data-stu-id="4ba78-111">H.</span></span> <span data-ttu-id="4ba78-112">Bennett，DiVincenzo，J。</span><span class="sxs-lookup"><span data-stu-id="4ba78-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="4ba78-113">Smolin 和 K. K。</span><span class="sxs-lookup"><span data-stu-id="4ba78-113">Smolin and W. K.</span></span> <span data-ttu-id="4ba78-114">Wootters，"混合状态牵连和量程错误更正" Phys，54 (1996) pp 3824-3851; https://arxiv.org/abs/quant-ph/9604024 和</span><span class="sxs-lookup"><span data-stu-id="4ba78-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="4ba78-115">R.</span><span class="sxs-lookup"><span data-stu-id="4ba78-115">R.</span></span> <span data-ttu-id="4ba78-116">Laflamme，Miquel，J P。</span><span class="sxs-lookup"><span data-stu-id="4ba78-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="4ba78-117">巴斯和 W.x.y.z。</span><span class="sxs-lookup"><span data-stu-id="4ba78-117">Paz and W. H.</span></span> <span data-ttu-id="4ba78-118">Zurek "完美的量程错误纠正代码" Phys Lett。</span><span class="sxs-lookup"><span data-stu-id="4ba78-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="4ba78-119">77 (1996) pp 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="4ba78-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>