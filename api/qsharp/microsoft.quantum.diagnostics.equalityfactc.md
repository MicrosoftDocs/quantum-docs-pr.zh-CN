---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695570"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="4f02d-102">EqualityFactC 函数</span><span class="sxs-lookup"><span data-stu-id="4f02d-102">EqualityFactC function</span></span>

<span data-ttu-id="4f02d-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4f02d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4f02d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f02d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f02d-105">断言复数具有预期值。</span><span class="sxs-lookup"><span data-stu-id="4f02d-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4f02d-106">输入</span><span class="sxs-lookup"><span data-stu-id="4f02d-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="4f02d-107">实际： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="4f02d-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="4f02d-108">要检查的值。</span><span class="sxs-lookup"><span data-stu-id="4f02d-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="4f02d-109">应为： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="4f02d-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="4f02d-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="4f02d-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="4f02d-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4f02d-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4f02d-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="4f02d-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f02d-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f02d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

