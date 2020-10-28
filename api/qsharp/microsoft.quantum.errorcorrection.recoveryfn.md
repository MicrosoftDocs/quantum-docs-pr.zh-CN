---
uid: Microsoft.Quantum.ErrorCorrection.RecoveryFn
title: RecoveryFn 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoveryFn
qsharp.summary: Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.
ms.openlocfilehash: 6f4db7312fadbd8ca4c6b8533f78c2c5a886f30e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695486"
---
# <a name="recoveryfn-user-defined-type"></a><span data-ttu-id="ed220-102">RecoveryFn 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="ed220-102">RecoveryFn user defined type</span></span>

<span data-ttu-id="ed220-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ed220-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ed220-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed220-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed220-105">用于将错误症状映射到一系列可 `Pauli[]` 更正检测到的错误的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="ed220-105">Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.</span></span>

```qsharp

newtype RecoveryFn = ((Microsoft.Quantum.ErrorCorrection.Syndrome -> Pauli[]));
```

