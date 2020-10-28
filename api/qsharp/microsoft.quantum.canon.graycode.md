---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696053"
---
# <a name="graycode-function"></a><span data-ttu-id="f7133-102">GrayCode 函数</span><span class="sxs-lookup"><span data-stu-id="f7133-102">GrayCode function</span></span>

<span data-ttu-id="f7133-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7133-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7133-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7133-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7133-105">创建灰色代码序列</span><span class="sxs-lookup"><span data-stu-id="f7133-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="f7133-106">输入</span><span class="sxs-lookup"><span data-stu-id="f7133-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="f7133-107">n： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7133-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7133-108">位数</span><span class="sxs-lookup"><span data-stu-id="f7133-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="f7133-109">Output： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="f7133-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="f7133-110">元组的数组。</span><span class="sxs-lookup"><span data-stu-id="f7133-110">Array of tuples.</span></span> <span data-ttu-id="f7133-111">元组中的第一个值为 GrayCode 中的值。元组中的第二个值是要在当前值中更改以获取下一项的位置</span><span class="sxs-lookup"><span data-stu-id="f7133-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>