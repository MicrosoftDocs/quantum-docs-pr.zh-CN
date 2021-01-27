---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853057"
---
# <a name="steanecode-function"></a><span data-ttu-id="ef187-102">SteaneCode 函数</span><span class="sxs-lookup"><span data-stu-id="ef187-102">SteaneCode function</span></span>

<span data-ttu-id="ef187-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ef187-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ef187-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef187-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef187-105">返回一个 CSS 值，它表示⟦7，1，3⟧ Steane 代码编码器，并使用就地的症状度量来表示解码器。</span><span class="sxs-lookup"><span data-stu-id="ef187-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="ef187-106">输出： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="ef187-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="ef187-107">CSS 类型的一个对象，该对象收集所有相关数据，以便对⟦7、1、3⟧ Steane 代码执行编码和错误更正。</span><span class="sxs-lookup"><span data-stu-id="ef187-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef187-108">备注</span><span class="sxs-lookup"><span data-stu-id="ef187-108">Remarks</span></span>

<span data-ttu-id="ef187-109">此代码在以下文章中找到：</span><span class="sxs-lookup"><span data-stu-id="ef187-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="ef187-110">A.</span><span class="sxs-lookup"><span data-stu-id="ef187-110">A.</span></span> <span data-ttu-id="ef187-111">Steane，"多粒子干扰和量程错误纠正"，过程。</span><span class="sxs-lookup"><span data-stu-id="ef187-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="ef187-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="ef187-112">Roy.</span></span> <span data-ttu-id="ef187-113">Lond。</span><span class="sxs-lookup"><span data-stu-id="ef187-113">Soc. Lond.</span></span> <span data-ttu-id="ef187-114">A452 (1996) pp 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="ef187-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>