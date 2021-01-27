---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: c252eceb6a307ea9514aaa8aa3a3de1f9fa1b698
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841922"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="0908e-102">ApplyCurriedOp 操作</span><span class="sxs-lookup"><span data-stu-id="0908e-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="0908e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0908e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0908e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0908e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="0908e-105">输入</span><span class="sxs-lookup"><span data-stu-id="0908e-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="0908e-106">curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0908e-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="0908e-107">第一个：不</span><span class="sxs-lookup"><span data-stu-id="0908e-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="0908e-108">第二个： "U</span><span class="sxs-lookup"><span data-stu-id="0908e-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="0908e-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0908e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0908e-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="0908e-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0908e-111">找</span><span class="sxs-lookup"><span data-stu-id="0908e-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="0908e-112">' U</span><span class="sxs-lookup"><span data-stu-id="0908e-112">'U</span></span>

