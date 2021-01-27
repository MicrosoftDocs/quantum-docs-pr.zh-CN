---
uid: Microsoft.Quantum.Math.ModL
title: ModL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: f044ae16d93d31d0f28f5fcf076cff2bfef62eb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846837"
---
# <a name="modl-function"></a><span data-ttu-id="95b78-102">ModL 函数</span><span class="sxs-lookup"><span data-stu-id="95b78-102">ModL function</span></span>

<span data-ttu-id="95b78-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="95b78-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="95b78-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95b78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95b78-105">返回与另一个数字相关的数字的模数。</span><span class="sxs-lookup"><span data-stu-id="95b78-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="95b78-106">输入</span><span class="sxs-lookup"><span data-stu-id="95b78-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="95b78-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="95b78-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="95b78-108">要返回其模数的输入 $a $。</span><span class="sxs-lookup"><span data-stu-id="95b78-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="95b78-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="95b78-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="95b78-110">要返回其 $a $ 的模数的相对数量。</span><span class="sxs-lookup"><span data-stu-id="95b78-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="95b78-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="95b78-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="95b78-112">取模 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="95b78-112">The modulus $a \bmod b$.</span></span>