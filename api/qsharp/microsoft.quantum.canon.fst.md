---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840515"
---
# <a name="fst-function"></a><span data-ttu-id="95b1e-102">Fst 函数</span><span class="sxs-lookup"><span data-stu-id="95b1e-102">Fst function</span></span>

<span data-ttu-id="95b1e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="95b1e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="95b1e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95b1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95b1e-105">给定一对，返回其第一个元素。</span><span class="sxs-lookup"><span data-stu-id="95b1e-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="95b1e-106">输入</span><span class="sxs-lookup"><span data-stu-id="95b1e-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="95b1e-107">配对： ( ' U) </span><span class="sxs-lookup"><span data-stu-id="95b1e-107">pair : ('T,'U)</span></span>

<span data-ttu-id="95b1e-108">具有两个元素的元组。</span><span class="sxs-lookup"><span data-stu-id="95b1e-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="95b1e-109">输出：不</span><span class="sxs-lookup"><span data-stu-id="95b1e-109">Output : 'T</span></span>

<span data-ttu-id="95b1e-110">`pair` 的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="95b1e-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="95b1e-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="95b1e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95b1e-112">找</span><span class="sxs-lookup"><span data-stu-id="95b1e-112">'T</span></span>

<span data-ttu-id="95b1e-113">对的第一个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="95b1e-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="95b1e-114">' U</span><span class="sxs-lookup"><span data-stu-id="95b1e-114">'U</span></span>

<span data-ttu-id="95b1e-115">对的第二个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="95b1e-115">The type of the pair's second member.</span></span>