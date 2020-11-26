---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: db3f63cbe2ee5ef048c7e378864d68696f55331f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218948"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="5ebfe-102">ApplyCurriedOpA 操作</span><span class="sxs-lookup"><span data-stu-id="5ebfe-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="5ebfe-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ebfe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ebfe-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ebfe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5ebfe-105">输入</span><span class="sxs-lookup"><span data-stu-id="5ebfe-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="5ebfe-106">curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="5ebfe-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="5ebfe-107">第一个：不</span><span class="sxs-lookup"><span data-stu-id="5ebfe-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="5ebfe-108">第二个： "U</span><span class="sxs-lookup"><span data-stu-id="5ebfe-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="5ebfe-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ebfe-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5ebfe-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="5ebfe-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ebfe-111">找</span><span class="sxs-lookup"><span data-stu-id="5ebfe-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="5ebfe-112">' U</span><span class="sxs-lookup"><span data-stu-id="5ebfe-112">'U</span></span>

