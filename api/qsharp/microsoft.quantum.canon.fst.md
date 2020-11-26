---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206929"
---
# <a name="fst-function"></a><span data-ttu-id="b5a05-102">Fst 函数</span><span class="sxs-lookup"><span data-stu-id="b5a05-102">Fst function</span></span>

<span data-ttu-id="b5a05-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b5a05-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b5a05-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5a05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5a05-105">给定一对，返回其第一个元素。</span><span class="sxs-lookup"><span data-stu-id="b5a05-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="b5a05-106">输入</span><span class="sxs-lookup"><span data-stu-id="b5a05-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="b5a05-107">配对： ( ' U) </span><span class="sxs-lookup"><span data-stu-id="b5a05-107">pair : ('T,'U)</span></span>

<span data-ttu-id="b5a05-108">具有两个元素的元组。</span><span class="sxs-lookup"><span data-stu-id="b5a05-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b5a05-109">输出：不</span><span class="sxs-lookup"><span data-stu-id="b5a05-109">Output : 'T</span></span>

<span data-ttu-id="b5a05-110">`pair` 的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="b5a05-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b5a05-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="b5a05-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5a05-112">找</span><span class="sxs-lookup"><span data-stu-id="b5a05-112">'T</span></span>

<span data-ttu-id="b5a05-113">对的第一个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="b5a05-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="b5a05-114">' U</span><span class="sxs-lookup"><span data-stu-id="b5a05-114">'U</span></span>

<span data-ttu-id="b5a05-115">对的第二个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="b5a05-115">The type of the pair's second member.</span></span>