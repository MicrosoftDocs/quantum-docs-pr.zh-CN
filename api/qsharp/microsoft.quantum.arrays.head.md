---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848572"
---
# <a name="head-function"></a><span data-ttu-id="fa1bd-102">Head 函数</span><span class="sxs-lookup"><span data-stu-id="fa1bd-102">Head function</span></span>

<span data-ttu-id="fa1bd-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fa1bd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fa1bd-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa1bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa1bd-105">返回数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="fa1bd-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="fa1bd-106">输入</span><span class="sxs-lookup"><span data-stu-id="fa1bd-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="fa1bd-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="fa1bd-107">array : 'A[]</span></span>

<span data-ttu-id="fa1bd-108">从中获取第一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="fa1bd-108">Array of which the first element is taken.</span></span> <span data-ttu-id="fa1bd-109">数组的长度必须至少为1。</span><span class="sxs-lookup"><span data-stu-id="fa1bd-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="fa1bd-110">输出： "A</span><span class="sxs-lookup"><span data-stu-id="fa1bd-110">Output : 'A</span></span>

<span data-ttu-id="fa1bd-111">数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="fa1bd-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fa1bd-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="fa1bd-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="fa1bd-113">' A</span><span class="sxs-lookup"><span data-stu-id="fa1bd-113">'A</span></span>

<span data-ttu-id="fa1bd-114">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="fa1bd-114">The type of the array elements.</span></span>