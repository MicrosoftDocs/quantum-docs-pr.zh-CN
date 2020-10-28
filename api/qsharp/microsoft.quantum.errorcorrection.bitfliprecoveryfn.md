---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695529"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="f89fe-102">BitFlipRecoveryFn 函数</span><span class="sxs-lookup"><span data-stu-id="f89fe-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="f89fe-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f89fe-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f89fe-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f89fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f89fe-105">针对⟦3，1，1⟧位翻转代码的表查找，针对给定的症状度量的恢复 Pauli 操作的函数。</span><span class="sxs-lookup"><span data-stu-id="f89fe-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="f89fe-106">输出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="f89fe-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="f89fe-107">`RecoveryFn`采用症状度量 `Result[]` 并返回 `Pauli[]` 更正检测到的错误的操作的类型的函数。</span><span class="sxs-lookup"><span data-stu-id="f89fe-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="f89fe-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f89fe-108">See Also</span></span>

- [<span data-ttu-id="f89fe-109">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="f89fe-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)