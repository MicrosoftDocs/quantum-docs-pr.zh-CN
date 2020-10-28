---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
title: OptimizedBEGeneratorSystem 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEGeneratorSystem
qsharp.summary: Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.
ms.openlocfilehash: 06d13a8a64a3c572821ec97f8776d6f1dbe4a4ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695735"
---
# <a name="optimizedbegeneratorsystem-user-defined-type"></a><span data-ttu-id="37c2d-102">OptimizedBEGeneratorSystem 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="37c2d-102">OptimizedBEGeneratorSystem user defined type</span></span>

<span data-ttu-id="37c2d-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="37c2d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="37c2d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37c2d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37c2d-105">一个函数，它返回 `OptimizedBETermIndex` 给定整数的术语的数据，以及中的字词 `n` `n` 数 `Int` 和中所有字词系数的绝对值之和 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="37c2d-105">Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.</span></span>

```qsharp

newtype OptimizedBEGeneratorSystem = (Int, Double, (Int -> Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex));
```

