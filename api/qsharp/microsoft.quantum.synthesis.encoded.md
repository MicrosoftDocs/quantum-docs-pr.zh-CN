---
uid: Microsoft.Quantum.Synthesis.Encoded
title: 编码函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203172"
---
# <a name="encoded-function"></a><span data-ttu-id="15ba4-102">编码函数</span><span class="sxs-lookup"><span data-stu-id="15ba4-102">Encoded function</span></span>

<span data-ttu-id="15ba4-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="15ba4-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="15ba4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15ba4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15ba4-105">{1,-1}编码事实数据表</span><span class="sxs-lookup"><span data-stu-id="15ba4-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="15ba4-106">输入</span><span class="sxs-lookup"><span data-stu-id="15ba4-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="15ba4-107">table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="15ba4-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="15ba4-108">事实数据表作为真值数组</span><span class="sxs-lookup"><span data-stu-id="15ba4-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="15ba4-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="15ba4-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="15ba4-110">作为整数数组的事实数据表 {1,-1}</span><span class="sxs-lookup"><span data-stu-id="15ba4-110">Truth table as array of {1,-1} integers</span></span>