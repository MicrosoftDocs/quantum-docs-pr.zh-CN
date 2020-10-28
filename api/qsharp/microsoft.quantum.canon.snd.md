---
uid: Microsoft.Quantum.Canon.Snd
title: Snd 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695951"
---
# <a name="snd-function"></a><span data-ttu-id="c9dae-102">Snd 函数</span><span class="sxs-lookup"><span data-stu-id="c9dae-102">Snd function</span></span>

<span data-ttu-id="c9dae-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9dae-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9dae-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9dae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9dae-105">如果给定对，则返回第二个元素。</span><span class="sxs-lookup"><span data-stu-id="c9dae-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="c9dae-106">输入</span><span class="sxs-lookup"><span data-stu-id="c9dae-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="c9dae-107">配对： ( ' U) </span><span class="sxs-lookup"><span data-stu-id="c9dae-107">pair : ('T,'U)</span></span>

<span data-ttu-id="c9dae-108">具有两个元素的元组。</span><span class="sxs-lookup"><span data-stu-id="c9dae-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="c9dae-109">输出： U</span><span class="sxs-lookup"><span data-stu-id="c9dae-109">Output : 'U</span></span>

<span data-ttu-id="c9dae-110">的第二个元素 `pair` 。</span><span class="sxs-lookup"><span data-stu-id="c9dae-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c9dae-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="c9dae-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9dae-112">找</span><span class="sxs-lookup"><span data-stu-id="c9dae-112">'T</span></span>

<span data-ttu-id="c9dae-113">对的第一个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="c9dae-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="c9dae-114">' U</span><span class="sxs-lookup"><span data-stu-id="c9dae-114">'U</span></span>

<span data-ttu-id="c9dae-115">对的第二个成员的类型。</span><span class="sxs-lookup"><span data-stu-id="c9dae-115">The type of the pair's second member.</span></span>