---
uid: Microsoft.Quantum.Canon.Snd
title: Snd 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205314"
---
# <a name="snd-function"></a><span data-ttu-id="1e236-102">Snd 函数</span><span class="sxs-lookup"><span data-stu-id="1e236-102">Snd function</span></span>

<span data-ttu-id="1e236-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1e236-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1e236-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e236-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e236-105">如果给定对，则返回第二个元素。</span><span class="sxs-lookup"><span data-stu-id="1e236-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="1e236-106">输入</span><span class="sxs-lookup"><span data-stu-id="1e236-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="1e236-107">配对： ( ' U) </span><span class="sxs-lookup"><span data-stu-id="1e236-107">pair : ('T,'U)</span></span>

<span data-ttu-id="1e236-108">具有两个元素的元组。</span><span class="sxs-lookup"><span data-stu-id="1e236-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="1e236-109">输出： U</span><span class="sxs-lookup"><span data-stu-id="1e236-109">Output : 'U</span></span>

<span data-ttu-id="1e236-110">的第二个元素 `pair` 。</span><span class="sxs-lookup"><span data-stu-id="1e236-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1e236-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="1e236-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1e236-112">找</span><span class="sxs-lookup"><span data-stu-id="1e236-112">'T</span></span>

<span data-ttu-id="1e236-113">对的第一个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="1e236-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="1e236-114">' U</span><span class="sxs-lookup"><span data-stu-id="1e236-114">'U</span></span>

<span data-ttu-id="1e236-115">对的第二个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="1e236-115">The type of the pair's second member.</span></span>