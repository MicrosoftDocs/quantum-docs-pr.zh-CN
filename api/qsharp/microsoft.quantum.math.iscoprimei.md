---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 2c110f9abf18ee81bd72a68601d5c41ff756290a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851355"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="41961-102">IsCoprimeI 函数</span><span class="sxs-lookup"><span data-stu-id="41961-102">IsCoprimeI function</span></span>

<span data-ttu-id="41961-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="41961-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="41961-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41961-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41961-105">如果 $a $ 和 $b $ 是共同质数，则返回 true; 否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="41961-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="41961-106">输入</span><span class="sxs-lookup"><span data-stu-id="41961-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="41961-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="41961-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="41961-108">正在测试的 primality 的第一个数字</span><span class="sxs-lookup"><span data-stu-id="41961-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="41961-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="41961-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="41961-110">正在测试的 primality 的第二个数字</span><span class="sxs-lookup"><span data-stu-id="41961-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="41961-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="41961-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="41961-112">如果 $a $ 和 $b $ 是共同质数 (例如，其最大公因数为 1 ) ，则为 True; 否则为 false。</span><span class="sxs-lookup"><span data-stu-id="41961-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>