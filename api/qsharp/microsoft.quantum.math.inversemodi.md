---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 474146e644bcd042e85b917bc43135a674bedce1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846889"
---
# <a name="inversemodi-function"></a><span data-ttu-id="8d720-102">InverseModI 函数</span><span class="sxs-lookup"><span data-stu-id="8d720-102">InverseModI function</span></span>

<span data-ttu-id="8d720-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8d720-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8d720-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d720-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d720-105">返回 $b $ $a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="8d720-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="8d720-106">输入</span><span class="sxs-lookup"><span data-stu-id="8d720-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="8d720-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d720-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d720-108">要反转的数字</span><span class="sxs-lookup"><span data-stu-id="8d720-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="8d720-109">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d720-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d720-110">与数字相反的模数</span><span class="sxs-lookup"><span data-stu-id="8d720-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="8d720-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d720-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d720-112">整数 $b $，$a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="8d720-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>