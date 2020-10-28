---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: ef9be0f0628c8ba8c5f131cc558bdcda6bb6ea55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701140"
---
# <a name="rmencoding-function"></a><span data-ttu-id="a682a-102">RMEncoding 函数</span><span class="sxs-lookup"><span data-stu-id="a682a-102">RMEncoding function</span></span>

<span data-ttu-id="a682a-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a682a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a682a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a682a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a682a-105">{-1,1} 布尔值事实值的编码</span><span class="sxs-lookup"><span data-stu-id="a682a-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="a682a-106">输入</span><span class="sxs-lookup"><span data-stu-id="a682a-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="a682a-107">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a682a-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a682a-108">布尔值</span><span class="sxs-lookup"><span data-stu-id="a682a-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="a682a-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a682a-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a682a-110">如果为 false，则为 1; `b` 否则为-1</span><span class="sxs-lookup"><span data-stu-id="a682a-110">1, if `b` is false, otherwise -1</span></span>