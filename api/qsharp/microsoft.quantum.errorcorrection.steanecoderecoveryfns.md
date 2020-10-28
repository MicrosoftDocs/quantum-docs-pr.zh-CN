---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: SteaneCodeRecoveryFns 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: b1dd1c2e9a71e58bd8a86d1759a8b6af13a49614
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695478"
---
# <a name="steanecoderecoveryfns-function"></a><span data-ttu-id="61363-102">SteaneCodeRecoveryFns 函数</span><span class="sxs-lookup"><span data-stu-id="61363-102">SteaneCodeRecoveryFns function</span></span>

<span data-ttu-id="61363-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="61363-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="61363-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="61363-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="61363-105">⟦7，1，3⟧ Steane 量程代码的稳定 X 和 Z 部分的解码器。</span><span class="sxs-lookup"><span data-stu-id="61363-105">Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a><span data-ttu-id="61363-106">Output： ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)，[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)) </span><span class="sxs-lookup"><span data-stu-id="61363-106">Output : ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span></span>

<span data-ttu-id="61363-107">类型为的函数的元组 `RecoveryFn` ，它采用一个症状度量 `Result[]` ，并返回 `Pauli[]` 纠正检测到的错误的操作。</span><span class="sxs-lookup"><span data-stu-id="61363-107">Tuple of functions of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="61363-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61363-108">See Also</span></span>

- [<span data-ttu-id="61363-109">ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="61363-109">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="61363-110">ErrorCorrection. SteaneCodeRecoveryZ</span><span class="sxs-lookup"><span data-stu-id="61363-110">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)