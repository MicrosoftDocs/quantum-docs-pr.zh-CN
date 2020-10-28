---
uid: Microsoft.Quantum.Synthesis.Encoded
title: 编码函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701061"
---
# <a name="encoded-function"></a><span data-ttu-id="b06bf-102">编码函数</span><span class="sxs-lookup"><span data-stu-id="b06bf-102">Encoded function</span></span>

<span data-ttu-id="b06bf-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b06bf-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b06bf-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b06bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b06bf-105">{1,-1}编码事实数据表</span><span class="sxs-lookup"><span data-stu-id="b06bf-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="b06bf-106">输入</span><span class="sxs-lookup"><span data-stu-id="b06bf-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="b06bf-107">table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b06bf-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b06bf-108">事实数据表作为真值数组</span><span class="sxs-lookup"><span data-stu-id="b06bf-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="b06bf-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b06bf-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b06bf-110">作为整数数组的事实数据表 {1,-1}</span><span class="sxs-lookup"><span data-stu-id="b06bf-110">Truth table as array of {1,-1} integers</span></span>