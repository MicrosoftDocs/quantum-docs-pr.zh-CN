---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221107"
---
# <a name="head-function"></a><span data-ttu-id="93e67-102">Head 函数</span><span class="sxs-lookup"><span data-stu-id="93e67-102">Head function</span></span>

<span data-ttu-id="93e67-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="93e67-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="93e67-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93e67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93e67-105">返回数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="93e67-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="93e67-106">输入</span><span class="sxs-lookup"><span data-stu-id="93e67-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="93e67-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="93e67-107">array : 'A[]</span></span>

<span data-ttu-id="93e67-108">从中获取第一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="93e67-108">Array of which the first element is taken.</span></span> <span data-ttu-id="93e67-109">数组的长度必须至少为1。</span><span class="sxs-lookup"><span data-stu-id="93e67-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="93e67-110">输出： "A</span><span class="sxs-lookup"><span data-stu-id="93e67-110">Output : 'A</span></span>

<span data-ttu-id="93e67-111">数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="93e67-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="93e67-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="93e67-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="93e67-113">' A</span><span class="sxs-lookup"><span data-stu-id="93e67-113">'A</span></span>

<span data-ttu-id="93e67-114">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="93e67-114">The type of the array elements.</span></span>