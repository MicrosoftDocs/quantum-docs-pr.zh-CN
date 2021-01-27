---
uid: Microsoft.Quantum.Math.ModI
title: ModI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 8f4ff37767e5120b99834a63ed19055ba1806907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848061"
---
# <a name="modi-function"></a><span data-ttu-id="62198-102">ModI 函数</span><span class="sxs-lookup"><span data-stu-id="62198-102">ModI function</span></span>

<span data-ttu-id="62198-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="62198-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="62198-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62198-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62198-105">返回与另一个数字相关的数字的模数。</span><span class="sxs-lookup"><span data-stu-id="62198-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="62198-106">输入</span><span class="sxs-lookup"><span data-stu-id="62198-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="62198-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="62198-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="62198-108">要返回其模数的输入 $a $。</span><span class="sxs-lookup"><span data-stu-id="62198-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="62198-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="62198-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="62198-110">要返回其 $a $ 的模数的相对数量。</span><span class="sxs-lookup"><span data-stu-id="62198-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="62198-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="62198-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="62198-112">取模 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="62198-112">The modulus $a \bmod b$.</span></span>