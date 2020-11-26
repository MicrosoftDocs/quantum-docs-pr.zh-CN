---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: faca9b3f6d9a132b591a532c9e2ce54af1f0b182
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218931"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="d2523-102">ApplyCurriedOpC 操作</span><span class="sxs-lookup"><span data-stu-id="d2523-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="d2523-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d2523-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d2523-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2523-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="d2523-105">输入</span><span class="sxs-lookup"><span data-stu-id="d2523-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="d2523-106">curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="d2523-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="d2523-107">第一个：不</span><span class="sxs-lookup"><span data-stu-id="d2523-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="d2523-108">第二个： "U</span><span class="sxs-lookup"><span data-stu-id="d2523-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="d2523-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2523-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d2523-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="d2523-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d2523-111">找</span><span class="sxs-lookup"><span data-stu-id="d2523-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="d2523-112">' U</span><span class="sxs-lookup"><span data-stu-id="d2523-112">'U</span></span>

