---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: 22e2ace51175ed9df1c70bf75ce2b497f8449020
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696367"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="b22ea-102">ApplyCurriedOp 操作</span><span class="sxs-lookup"><span data-stu-id="b22ea-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="b22ea-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b22ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b22ea-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b22ea-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="b22ea-105">输入</span><span class="sxs-lookup"><span data-stu-id="b22ea-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="b22ea-106">curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b22ea-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="b22ea-107">第一个：不</span><span class="sxs-lookup"><span data-stu-id="b22ea-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="b22ea-108">第二个： "U</span><span class="sxs-lookup"><span data-stu-id="b22ea-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="b22ea-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b22ea-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b22ea-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="b22ea-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b22ea-111">找</span><span class="sxs-lookup"><span data-stu-id="b22ea-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="b22ea-112">' U</span><span class="sxs-lookup"><span data-stu-id="b22ea-112">'U</span></span>

