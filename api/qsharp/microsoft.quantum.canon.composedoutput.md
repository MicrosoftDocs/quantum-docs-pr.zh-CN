---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207456"
---
# <a name="composedoutput-function"></a><span data-ttu-id="48009-102">ComposedOutput 函数</span><span class="sxs-lookup"><span data-stu-id="48009-102">ComposedOutput function</span></span>

<span data-ttu-id="48009-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="48009-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="48009-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48009-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48009-105">返回给定输入的和的组合的输出 `inner` `outer` 。</span><span class="sxs-lookup"><span data-stu-id="48009-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="48009-106">输入</span><span class="sxs-lookup"><span data-stu-id="48009-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="48009-107">外部： "U->" V</span><span class="sxs-lookup"><span data-stu-id="48009-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="48009-108">内部：不 > "U</span><span class="sxs-lookup"><span data-stu-id="48009-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="48009-109">目标： t</span><span class="sxs-lookup"><span data-stu-id="48009-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="48009-110">输出： "V</span><span class="sxs-lookup"><span data-stu-id="48009-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="48009-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="48009-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48009-112">找</span><span class="sxs-lookup"><span data-stu-id="48009-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="48009-113">' U</span><span class="sxs-lookup"><span data-stu-id="48009-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="48009-114">' V</span><span class="sxs-lookup"><span data-stu-id="48009-114">'V</span></span>

