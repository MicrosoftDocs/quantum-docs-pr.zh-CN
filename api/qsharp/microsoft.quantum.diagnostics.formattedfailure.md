---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695555"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="b15c3-102">FormattedFailure 函数</span><span class="sxs-lookup"><span data-stu-id="b15c3-102">FormattedFailure function</span></span>

<span data-ttu-id="b15c3-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b15c3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b15c3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b15c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b15c3-105">用于在出现有意义的错误消息时失败的内部函数。</span><span class="sxs-lookup"><span data-stu-id="b15c3-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b15c3-106">输入</span><span class="sxs-lookup"><span data-stu-id="b15c3-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="b15c3-107">实际：不</span><span class="sxs-lookup"><span data-stu-id="b15c3-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="b15c3-108">应为： t</span><span class="sxs-lookup"><span data-stu-id="b15c3-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="b15c3-109">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b15c3-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="b15c3-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b15c3-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b15c3-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="b15c3-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b15c3-112">找</span><span class="sxs-lookup"><span data-stu-id="b15c3-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b15c3-113">注解</span><span class="sxs-lookup"><span data-stu-id="b15c3-113">Remarks</span></span>

<span data-ttu-id="b15c3-114">此函数旨在由模拟运行时进行模拟，以便允许格式矛盾转发。</span><span class="sxs-lookup"><span data-stu-id="b15c3-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>