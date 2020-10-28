---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: 1a00fe91889e3100e4d3272d258877b4ec88618f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696364"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="1e9f2-102">ApplyCurriedOpC 操作</span><span class="sxs-lookup"><span data-stu-id="1e9f2-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="1e9f2-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1e9f2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1e9f2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e9f2-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="1e9f2-105">输入</span><span class="sxs-lookup"><span data-stu-id="1e9f2-105">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="1e9f2-106">curriedOp：不 > "U => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="1e9f2-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="1e9f2-107">第一个：不</span><span class="sxs-lookup"><span data-stu-id="1e9f2-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="1e9f2-108">第二个： "U</span><span class="sxs-lookup"><span data-stu-id="1e9f2-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="1e9f2-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e9f2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1e9f2-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="1e9f2-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1e9f2-111">找</span><span class="sxs-lookup"><span data-stu-id="1e9f2-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="1e9f2-112">' U</span><span class="sxs-lookup"><span data-stu-id="1e9f2-112">'U</span></span>

