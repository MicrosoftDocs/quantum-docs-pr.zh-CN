---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 0fcfe553d7a0050a9ab35a43ac5fe2b1958514db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853367"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="5d5b4-102">EqualityFactC 函数</span><span class="sxs-lookup"><span data-stu-id="5d5b4-102">EqualityFactC function</span></span>

<span data-ttu-id="5d5b4-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5d5b4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5d5b4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5d5b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5d5b4-105">断言复数具有预期值。</span><span class="sxs-lookup"><span data-stu-id="5d5b4-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="5d5b4-106">输入</span><span class="sxs-lookup"><span data-stu-id="5d5b4-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="5d5b4-107">实际： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="5d5b4-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="5d5b4-108">要检查的值。</span><span class="sxs-lookup"><span data-stu-id="5d5b4-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="5d5b4-109">应为： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="5d5b4-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="5d5b4-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="5d5b4-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="5d5b4-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5d5b4-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5d5b4-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="5d5b4-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5d5b4-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d5b4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

