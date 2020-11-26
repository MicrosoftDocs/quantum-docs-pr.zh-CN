---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206878"
---
# <a name="graycode-function"></a><span data-ttu-id="c0cb4-102">GrayCode 函数</span><span class="sxs-lookup"><span data-stu-id="c0cb4-102">GrayCode function</span></span>

<span data-ttu-id="c0cb4-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c0cb4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c0cb4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0cb4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0cb4-105">创建灰色代码序列</span><span class="sxs-lookup"><span data-stu-id="c0cb4-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="c0cb4-106">输入</span><span class="sxs-lookup"><span data-stu-id="c0cb4-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="c0cb4-107">n： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c0cb4-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c0cb4-108">位数</span><span class="sxs-lookup"><span data-stu-id="c0cb4-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="c0cb4-109">Output： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="c0cb4-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="c0cb4-110">元组的数组。</span><span class="sxs-lookup"><span data-stu-id="c0cb4-110">Array of tuples.</span></span> <span data-ttu-id="c0cb4-111">元组中的第一个值为 GrayCode 中的值。元组中的第二个值是要在当前值中更改以获取下一项的位置</span><span class="sxs-lookup"><span data-stu-id="c0cb4-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>