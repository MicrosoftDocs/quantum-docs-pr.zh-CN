---
uid: Microsoft.Quantum.Canon.ApplyBoundCA
title: ApplyBoundCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyBoundCA
qsharp.summary: ''
ms.openlocfilehash: 8eb41318fbb9cbee46159ac3a570b21874358d32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219203"
---
# <a name="applyboundca-operation"></a><span data-ttu-id="0b5a1-102">ApplyBoundCA 操作</span><span class="sxs-lookup"><span data-stu-id="0b5a1-102">ApplyBoundCA operation</span></span>

<span data-ttu-id="0b5a1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b5a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b5a1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b5a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyBoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[], target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0b5a1-105">输入</span><span class="sxs-lookup"><span data-stu-id="0b5a1-105">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="0b5a1-106">操作：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为调整 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="0b5a1-106">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>




### <a name="target--t"></a><span data-ttu-id="0b5a1-107">目标： t</span><span class="sxs-lookup"><span data-stu-id="0b5a1-107">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="0b5a1-108">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b5a1-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0b5a1-109">类型参数</span><span class="sxs-lookup"><span data-stu-id="0b5a1-109">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b5a1-110">找</span><span class="sxs-lookup"><span data-stu-id="0b5a1-110">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="0b5a1-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b5a1-111">See Also</span></span>

- [<span data-ttu-id="0b5a1-112">Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="0b5a1-112">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)