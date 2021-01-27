---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828279"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="6929f-102">FormattedFailure 函数</span><span class="sxs-lookup"><span data-stu-id="6929f-102">FormattedFailure function</span></span>

<span data-ttu-id="6929f-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6929f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6929f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6929f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6929f-105">用于在出现有意义的错误消息时失败的内部函数。</span><span class="sxs-lookup"><span data-stu-id="6929f-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6929f-106">输入</span><span class="sxs-lookup"><span data-stu-id="6929f-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="6929f-107">实际：不</span><span class="sxs-lookup"><span data-stu-id="6929f-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="6929f-108">应为： t</span><span class="sxs-lookup"><span data-stu-id="6929f-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="6929f-109">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6929f-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="6929f-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6929f-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6929f-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="6929f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6929f-112">找</span><span class="sxs-lookup"><span data-stu-id="6929f-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6929f-113">备注</span><span class="sxs-lookup"><span data-stu-id="6929f-113">Remarks</span></span>

<span data-ttu-id="6929f-114">此函数旨在由模拟运行时进行模拟，以便允许格式矛盾转发。</span><span class="sxs-lookup"><span data-stu-id="6929f-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>