---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695568"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="ed083-102">EqualityFactCP 函数</span><span class="sxs-lookup"><span data-stu-id="ed083-102">EqualityFactCP function</span></span>

<span data-ttu-id="ed083-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ed083-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ed083-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed083-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed083-105">断言复数具有预期值。</span><span class="sxs-lookup"><span data-stu-id="ed083-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ed083-106">输入</span><span class="sxs-lookup"><span data-stu-id="ed083-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="ed083-107">实际： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="ed083-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="ed083-108">要检查的值。</span><span class="sxs-lookup"><span data-stu-id="ed083-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="ed083-109">应为： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="ed083-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="ed083-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="ed083-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="ed083-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ed083-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ed083-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="ed083-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ed083-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed083-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
