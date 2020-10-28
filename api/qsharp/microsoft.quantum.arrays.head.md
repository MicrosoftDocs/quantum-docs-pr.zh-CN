---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 7b26a9c414ab2caad70f96f3c26c2d1cf0b03e95
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696508"
---
# <a name="head-function"></a><span data-ttu-id="da388-102">Head 函数</span><span class="sxs-lookup"><span data-stu-id="da388-102">Head function</span></span>

<span data-ttu-id="da388-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="da388-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="da388-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da388-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da388-105">返回数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="da388-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="da388-106">输入</span><span class="sxs-lookup"><span data-stu-id="da388-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="da388-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="da388-107">array : 'A[]</span></span>

<span data-ttu-id="da388-108">从中获取第一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="da388-108">Array of which the first element is taken.</span></span> <span data-ttu-id="da388-109">数组的长度必须至少为1。</span><span class="sxs-lookup"><span data-stu-id="da388-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="da388-110">输出： "A</span><span class="sxs-lookup"><span data-stu-id="da388-110">Output : 'A</span></span>

<span data-ttu-id="da388-111">数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="da388-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="da388-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="da388-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="da388-113">' A</span><span class="sxs-lookup"><span data-stu-id="da388-113">'A</span></span>

<span data-ttu-id="da388-114">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="da388-114">The type of the array elements.</span></span>