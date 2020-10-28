---
uid: Microsoft.Quantum.Canon.Angle
title: Angle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696392"
---
# <a name="angle-function"></a><span data-ttu-id="d4963-102">Angle 函数</span><span class="sxs-lookup"><span data-stu-id="d4963-102">Angle function</span></span>

<span data-ttu-id="d4963-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d4963-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d4963-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4963-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4963-105">如果的值为奇数，则返回 1; `index` 如果的值为偶数，则返回-1 `index` 。</span><span class="sxs-lookup"><span data-stu-id="d4963-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="d4963-106">说明</span><span class="sxs-lookup"><span data-stu-id="d4963-106">Description</span></span>

<span data-ttu-id="d4963-107">值对应于指定赋值的 n 变量和函数的 Rademacher-Walsh 的系数的符号，用于决定旋转角度。</span><span class="sxs-lookup"><span data-stu-id="d4963-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="d4963-108">输入</span><span class="sxs-lookup"><span data-stu-id="d4963-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="d4963-109">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4963-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4963-110">输入分配作为整数 (，从0到 2 ^ n-1) </span><span class="sxs-lookup"><span data-stu-id="d4963-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="d4963-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4963-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

