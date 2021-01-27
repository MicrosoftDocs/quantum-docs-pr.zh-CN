---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840496"
---
# <a name="graycode-function"></a><span data-ttu-id="0e7b6-102">GrayCode 函数</span><span class="sxs-lookup"><span data-stu-id="0e7b6-102">GrayCode function</span></span>

<span data-ttu-id="0e7b6-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0e7b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0e7b6-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e7b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e7b6-105">创建灰色代码序列</span><span class="sxs-lookup"><span data-stu-id="0e7b6-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="0e7b6-106">输入</span><span class="sxs-lookup"><span data-stu-id="0e7b6-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="0e7b6-107">n： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0e7b6-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0e7b6-108">位数</span><span class="sxs-lookup"><span data-stu-id="0e7b6-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="0e7b6-109">Output： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="0e7b6-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="0e7b6-110">元组的数组。</span><span class="sxs-lookup"><span data-stu-id="0e7b6-110">Array of tuples.</span></span> <span data-ttu-id="0e7b6-111">元组中的第一个值为 GrayCode 中的值。元组中的第二个值是要在当前值中更改以获取下一项的位置</span><span class="sxs-lookup"><span data-stu-id="0e7b6-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>

## <a name="example"></a><span data-ttu-id="0e7b6-112">示例</span><span class="sxs-lookup"><span data-stu-id="0e7b6-112">Example</span></span>

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```