---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 0d768114c84025a067e0b60762e6834fbd36deb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228179"
---
# <a name="inversemodl-function"></a><span data-ttu-id="3ea94-102">InverseModL 函数</span><span class="sxs-lookup"><span data-stu-id="3ea94-102">InverseModL function</span></span>

<span data-ttu-id="3ea94-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3ea94-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3ea94-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ea94-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ea94-105">返回 $b $ $a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="3ea94-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="3ea94-106">输入</span><span class="sxs-lookup"><span data-stu-id="3ea94-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="3ea94-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3ea94-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3ea94-108">要反转的数字</span><span class="sxs-lookup"><span data-stu-id="3ea94-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="3ea94-109">模数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3ea94-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3ea94-110">与数字相反的模数</span><span class="sxs-lookup"><span data-stu-id="3ea94-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="3ea94-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3ea94-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3ea94-112">整数 $b $，$a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="3ea94-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>