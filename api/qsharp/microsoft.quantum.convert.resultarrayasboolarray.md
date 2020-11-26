---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: f3af3abd4ee58f495d4ea60ec4f21a2690abec1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224218"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="4ceea-102">ResultArrayAsBoolArray 函数</span><span class="sxs-lookup"><span data-stu-id="4ceea-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="4ceea-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4ceea-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4ceea-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ceea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ceea-105">将 `Result[]` 类型转换为 `Bool[]` 类型，其中 `One` 映射到 `true` 并 `Zero` 映射到 `false` 。</span><span class="sxs-lookup"><span data-stu-id="4ceea-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="4ceea-106">输入</span><span class="sxs-lookup"><span data-stu-id="4ceea-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="4ceea-107">输入：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="4ceea-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="4ceea-108">`Result[]` 要转换的。</span><span class="sxs-lookup"><span data-stu-id="4ceea-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4ceea-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4ceea-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4ceea-110">表示 `input` 的 `Bool[]`。</span><span class="sxs-lookup"><span data-stu-id="4ceea-110">A `Bool[]` representing the `input`.</span></span>