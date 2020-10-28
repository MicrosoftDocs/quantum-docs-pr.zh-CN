---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696447"
---
# <a name="tail-function"></a><span data-ttu-id="acbc3-102">Tail 函数</span><span class="sxs-lookup"><span data-stu-id="acbc3-102">Tail function</span></span>

<span data-ttu-id="acbc3-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="acbc3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="acbc3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="acbc3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="acbc3-105">返回数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="acbc3-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="acbc3-106">输入</span><span class="sxs-lookup"><span data-stu-id="acbc3-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="acbc3-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="acbc3-107">array : 'A[]</span></span>

<span data-ttu-id="acbc3-108">要获取其最后一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="acbc3-108">Array of which the last element is taken.</span></span> <span data-ttu-id="acbc3-109">数组的长度必须至少为1。</span><span class="sxs-lookup"><span data-stu-id="acbc3-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="acbc3-110">输出： "A</span><span class="sxs-lookup"><span data-stu-id="acbc3-110">Output : 'A</span></span>

<span data-ttu-id="acbc3-111">数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="acbc3-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="acbc3-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="acbc3-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="acbc3-113">' A</span><span class="sxs-lookup"><span data-stu-id="acbc3-113">'A</span></span>

<span data-ttu-id="acbc3-114">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="acbc3-114">The type of the array elements.</span></span>