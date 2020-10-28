---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: 2b0f86efe79654e1f886f0ccd0287e07225cbf83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696366"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="9ebd5-102">ApplyCurriedOpA 操作</span><span class="sxs-lookup"><span data-stu-id="9ebd5-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="9ebd5-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ebd5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ebd5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ebd5-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="9ebd5-105">输入</span><span class="sxs-lookup"><span data-stu-id="9ebd5-105">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="9ebd5-106">curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="9ebd5-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="9ebd5-107">第一个：不</span><span class="sxs-lookup"><span data-stu-id="9ebd5-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="9ebd5-108">第二个： "U</span><span class="sxs-lookup"><span data-stu-id="9ebd5-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="9ebd5-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ebd5-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9ebd5-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="9ebd5-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ebd5-111">找</span><span class="sxs-lookup"><span data-stu-id="9ebd5-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="9ebd5-112">' U</span><span class="sxs-lookup"><span data-stu-id="9ebd5-112">'U</span></span>

