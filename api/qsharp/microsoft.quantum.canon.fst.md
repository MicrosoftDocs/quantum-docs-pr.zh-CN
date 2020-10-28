---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696056"
---
# <a name="fst-function"></a><span data-ttu-id="45425-102">Fst 函数</span><span class="sxs-lookup"><span data-stu-id="45425-102">Fst function</span></span>

<span data-ttu-id="45425-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45425-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45425-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45425-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45425-105">给定一对，返回其第一个元素。</span><span class="sxs-lookup"><span data-stu-id="45425-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="45425-106">输入</span><span class="sxs-lookup"><span data-stu-id="45425-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="45425-107">配对： ( ' U) </span><span class="sxs-lookup"><span data-stu-id="45425-107">pair : ('T,'U)</span></span>

<span data-ttu-id="45425-108">具有两个元素的元组。</span><span class="sxs-lookup"><span data-stu-id="45425-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="45425-109">输出：不</span><span class="sxs-lookup"><span data-stu-id="45425-109">Output : 'T</span></span>

<span data-ttu-id="45425-110">`pair` 的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="45425-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="45425-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="45425-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45425-112">找</span><span class="sxs-lookup"><span data-stu-id="45425-112">'T</span></span>

<span data-ttu-id="45425-113">对的第一个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="45425-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="45425-114">' U</span><span class="sxs-lookup"><span data-stu-id="45425-114">'U</span></span>

<span data-ttu-id="45425-115">对的第二个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="45425-115">The type of the pair's second member.</span></span>