---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840891"
---
# <a name="composedoutput-function"></a><span data-ttu-id="e7f8b-102">ComposedOutput 函数</span><span class="sxs-lookup"><span data-stu-id="e7f8b-102">ComposedOutput function</span></span>

<span data-ttu-id="e7f8b-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e7f8b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e7f8b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7f8b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7f8b-105">返回给定输入的和的组合的输出 `inner` `outer` 。</span><span class="sxs-lookup"><span data-stu-id="e7f8b-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="e7f8b-106">输入</span><span class="sxs-lookup"><span data-stu-id="e7f8b-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="e7f8b-107">外部： "U->" V</span><span class="sxs-lookup"><span data-stu-id="e7f8b-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="e7f8b-108">内部：不 > "U</span><span class="sxs-lookup"><span data-stu-id="e7f8b-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="e7f8b-109">目标： t</span><span class="sxs-lookup"><span data-stu-id="e7f8b-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="e7f8b-110">输出： "V</span><span class="sxs-lookup"><span data-stu-id="e7f8b-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e7f8b-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="e7f8b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e7f8b-112">找</span><span class="sxs-lookup"><span data-stu-id="e7f8b-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="e7f8b-113">' U</span><span class="sxs-lookup"><span data-stu-id="e7f8b-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="e7f8b-114">' V</span><span class="sxs-lookup"><span data-stu-id="e7f8b-114">'V</span></span>

