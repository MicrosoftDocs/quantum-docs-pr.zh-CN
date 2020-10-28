---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695484"
---
# <a name="steanecode-function"></a><span data-ttu-id="c0180-102">SteaneCode 函数</span><span class="sxs-lookup"><span data-stu-id="c0180-102">SteaneCode function</span></span>

<span data-ttu-id="c0180-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c0180-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c0180-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0180-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0180-105">返回一个 CSS 值，它表示⟦7，1，3⟧ Steane 代码编码器，并使用就地的症状度量来表示解码器。</span><span class="sxs-lookup"><span data-stu-id="c0180-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="c0180-106">输出： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="c0180-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="c0180-107">CSS 类型的一个对象，该对象收集所有相关数据，以便对⟦7、1、3⟧ Steane 代码执行编码和错误更正。</span><span class="sxs-lookup"><span data-stu-id="c0180-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0180-108">注解</span><span class="sxs-lookup"><span data-stu-id="c0180-108">Remarks</span></span>

<span data-ttu-id="c0180-109">此代码在以下文章中找到：</span><span class="sxs-lookup"><span data-stu-id="c0180-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="c0180-110">A.</span><span class="sxs-lookup"><span data-stu-id="c0180-110">A.</span></span> <span data-ttu-id="c0180-111">Steane，"多粒子干扰和量程错误纠正"，过程。</span><span class="sxs-lookup"><span data-stu-id="c0180-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="c0180-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="c0180-112">Roy.</span></span> <span data-ttu-id="c0180-113">Lond。</span><span class="sxs-lookup"><span data-stu-id="c0180-113">Soc. Lond.</span></span> <span data-ttu-id="c0180-114">A452 (1996) pp 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="c0180-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>