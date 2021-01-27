---
uid: Microsoft.Quantum.Canon.IsRangeEmpty
title: IsRangeEmpty 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsRangeEmpty
qsharp.summary: Returns true if and only if input range is empty.
ms.openlocfilehash: a36d174bd0e89df0f546290fc469214fd820aa5c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840339"
---
# <a name="israngeempty-function"></a><span data-ttu-id="ae32a-102">IsRangeEmpty 函数</span><span class="sxs-lookup"><span data-stu-id="ae32a-102">IsRangeEmpty function</span></span>

<span data-ttu-id="ae32a-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae32a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae32a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae32a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae32a-105">当且仅当输入范围为空时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="ae32a-105">Returns true if and only if input range is empty.</span></span>

```qsharp
function IsRangeEmpty (rng : Range) : Bool
```


## <a name="input"></a><span data-ttu-id="ae32a-106">输入</span><span class="sxs-lookup"><span data-stu-id="ae32a-106">Input</span></span>

### <a name="rng--range"></a><span data-ttu-id="ae32a-107">rng： [Range](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ae32a-107">rng : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="ae32a-108">任意范围</span><span class="sxs-lookup"><span data-stu-id="ae32a-108">Any range</span></span>



## <a name="output--bool"></a><span data-ttu-id="ae32a-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="ae32a-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ae32a-110">如果且仅当为空时为 True `rng`</span><span class="sxs-lookup"><span data-stu-id="ae32a-110">True, if and only if `rng` is empty</span></span>