---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: 此时函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846175"
---
# <a name="emptyarray-function"></a><span data-ttu-id="1a15c-102">此时函数</span><span class="sxs-lookup"><span data-stu-id="1a15c-102">EmptyArray function</span></span>

<span data-ttu-id="1a15c-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1a15c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1a15c-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1a15c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1a15c-105">返回给定类型的空数组。</span><span class="sxs-lookup"><span data-stu-id="1a15c-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="1a15c-106">输出： "TElement []</span><span class="sxs-lookup"><span data-stu-id="1a15c-106">Output : 'TElement[]</span></span>

<span data-ttu-id="1a15c-107">空数组。</span><span class="sxs-lookup"><span data-stu-id="1a15c-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1a15c-108">类型参数</span><span class="sxs-lookup"><span data-stu-id="1a15c-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="1a15c-109">' TElement</span><span class="sxs-lookup"><span data-stu-id="1a15c-109">'TElement</span></span>

<span data-ttu-id="1a15c-110">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="1a15c-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="1a15c-111">示例</span><span class="sxs-lookup"><span data-stu-id="1a15c-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```