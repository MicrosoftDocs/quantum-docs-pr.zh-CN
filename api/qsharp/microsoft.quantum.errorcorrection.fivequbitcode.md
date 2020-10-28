---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695507"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="0b66e-102">FiveQubitCode 函数</span><span class="sxs-lookup"><span data-stu-id="0b66e-102">FiveQubitCode function</span></span>

<span data-ttu-id="0b66e-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0b66e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0b66e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b66e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b66e-105">返回一个 QECC 值，该值表示⟦5、1、3⟧代码编码器和解码器，并提供就地的症状度量。</span><span class="sxs-lookup"><span data-stu-id="0b66e-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="0b66e-106">输出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="0b66e-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="0b66e-107">通过指定类型返回量程错误更正代码的实现 `QECC` 。</span><span class="sxs-lookup"><span data-stu-id="0b66e-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b66e-108">注解</span><span class="sxs-lookup"><span data-stu-id="0b66e-108">Remarks</span></span>

<span data-ttu-id="0b66e-109">以下两篇文章中单独找到了此代码：</span><span class="sxs-lookup"><span data-stu-id="0b66e-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="0b66e-110">C.</span><span class="sxs-lookup"><span data-stu-id="0b66e-110">C.</span></span> <span data-ttu-id="0b66e-111">H.</span><span class="sxs-lookup"><span data-stu-id="0b66e-111">H.</span></span> <span data-ttu-id="0b66e-112">Bennett，DiVincenzo，J。</span><span class="sxs-lookup"><span data-stu-id="0b66e-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="0b66e-113">Smolin 和 K. K。</span><span class="sxs-lookup"><span data-stu-id="0b66e-113">Smolin and W. K.</span></span> <span data-ttu-id="0b66e-114">Wootters，"混合状态牵连和量程错误更正" Phys，54 (1996) pp 3824-3851; https://arxiv.org/abs/quant-ph/9604024 和</span><span class="sxs-lookup"><span data-stu-id="0b66e-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="0b66e-115">R.</span><span class="sxs-lookup"><span data-stu-id="0b66e-115">R.</span></span> <span data-ttu-id="0b66e-116">Laflamme，Miquel，J P。</span><span class="sxs-lookup"><span data-stu-id="0b66e-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="0b66e-117">巴斯和 W.x.y.z。</span><span class="sxs-lookup"><span data-stu-id="0b66e-117">Paz and W. H.</span></span> <span data-ttu-id="0b66e-118">Zurek "完美的量程错误纠正代码" Phys Lett。</span><span class="sxs-lookup"><span data-stu-id="0b66e-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="0b66e-119">77 (1996) pp 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="0b66e-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>