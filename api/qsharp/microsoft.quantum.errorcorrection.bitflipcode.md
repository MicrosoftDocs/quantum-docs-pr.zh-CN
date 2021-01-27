---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 0a5a028f85b80575b754b93a797a1460d21bb552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853196"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="a8a02-102">BitFlipCode 函数</span><span class="sxs-lookup"><span data-stu-id="a8a02-102">BitFlipCode function</span></span>

<span data-ttu-id="a8a02-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a8a02-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a8a02-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8a02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8a02-105">返回一个 QECC 值，该值表示⟦3，1，1⟧位翻转代码编码器和解码器，并使用就地症状度量。</span><span class="sxs-lookup"><span data-stu-id="a8a02-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="a8a02-106">输出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="a8a02-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="a8a02-107">通过指定类型返回量程错误更正代码的实现 `QECC` 。</span><span class="sxs-lookup"><span data-stu-id="a8a02-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>