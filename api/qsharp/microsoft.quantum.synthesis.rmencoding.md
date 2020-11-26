---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: a506ccb637b331a392ea75383c8bd605114af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202934"
---
# <a name="rmencoding-function"></a><span data-ttu-id="1e85f-102">RMEncoding 函数</span><span class="sxs-lookup"><span data-stu-id="1e85f-102">RMEncoding function</span></span>

<span data-ttu-id="1e85f-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="1e85f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="1e85f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e85f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e85f-105">{-1,1} 布尔值事实值的编码</span><span class="sxs-lookup"><span data-stu-id="1e85f-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="1e85f-106">输入</span><span class="sxs-lookup"><span data-stu-id="1e85f-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="1e85f-107">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1e85f-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1e85f-108">布尔值</span><span class="sxs-lookup"><span data-stu-id="1e85f-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="1e85f-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e85f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e85f-110">如果为 false，则为 1; `b` 否则为-1</span><span class="sxs-lookup"><span data-stu-id="1e85f-110">1, if `b` is false, otherwise -1</span></span>