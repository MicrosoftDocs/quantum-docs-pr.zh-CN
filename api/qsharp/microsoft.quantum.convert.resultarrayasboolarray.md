---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 0356fe9c98306ee3e1857f4af311aef9b3789a7d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695652"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="28c72-102">ResultArrayAsBoolArray 函数</span><span class="sxs-lookup"><span data-stu-id="28c72-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="28c72-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="28c72-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="28c72-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28c72-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28c72-105">将 `Result[]` 类型转换为 `Bool[]` 类型，其中 `One` 映射到 `true` 并 `Zero` 映射到 `false` 。</span><span class="sxs-lookup"><span data-stu-id="28c72-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="28c72-106">输入</span><span class="sxs-lookup"><span data-stu-id="28c72-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="28c72-107">输入： __无效 <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="28c72-107">input : __invalid<Result>__ []</span></span>

<span data-ttu-id="28c72-108">`Result[]` 要转换的。</span><span class="sxs-lookup"><span data-stu-id="28c72-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="28c72-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="28c72-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="28c72-110">表示 `input` 的 `Bool[]`。</span><span class="sxs-lookup"><span data-stu-id="28c72-110">A `Bool[]` representing the `input`.</span></span>