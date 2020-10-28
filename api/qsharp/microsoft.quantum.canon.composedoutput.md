---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696099"
---
# <a name="composedoutput-function"></a><span data-ttu-id="bcf29-102">ComposedOutput 函数</span><span class="sxs-lookup"><span data-stu-id="bcf29-102">ComposedOutput function</span></span>

<span data-ttu-id="bcf29-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bcf29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bcf29-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bcf29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bcf29-105">返回给定输入的和的组合的输出 `inner` `outer` 。</span><span class="sxs-lookup"><span data-stu-id="bcf29-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="bcf29-106">输入</span><span class="sxs-lookup"><span data-stu-id="bcf29-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="bcf29-107">外部： "U->" V</span><span class="sxs-lookup"><span data-stu-id="bcf29-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="bcf29-108">内部：不 > "U</span><span class="sxs-lookup"><span data-stu-id="bcf29-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="bcf29-109">目标： t</span><span class="sxs-lookup"><span data-stu-id="bcf29-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="bcf29-110">输出： "V</span><span class="sxs-lookup"><span data-stu-id="bcf29-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bcf29-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="bcf29-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bcf29-112">找</span><span class="sxs-lookup"><span data-stu-id="bcf29-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="bcf29-113">' U</span><span class="sxs-lookup"><span data-stu-id="bcf29-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="bcf29-114">' V</span><span class="sxs-lookup"><span data-stu-id="bcf29-114">'V</span></span>

