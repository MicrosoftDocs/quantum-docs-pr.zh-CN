---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0190529dd804922a69499fbf1c2c4c916c4b720a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214239"
---
# <a name="boolasresult-function"></a><span data-ttu-id="ae1a2-102">BoolAsResult 函数</span><span class="sxs-lookup"><span data-stu-id="ae1a2-102">BoolAsResult function</span></span>

<span data-ttu-id="ae1a2-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ae1a2-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ae1a2-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae1a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae1a2-105">将 `Bool` 类型转换为 `Result` 类型，其中 `true` 映射到 `One` 并 `false` 映射到 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="ae1a2-105">Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a><span data-ttu-id="ae1a2-106">输入</span><span class="sxs-lookup"><span data-stu-id="ae1a2-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="ae1a2-107">输入：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="ae1a2-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ae1a2-108">`Bool` 要转换的。</span><span class="sxs-lookup"><span data-stu-id="ae1a2-108">`Bool` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ae1a2-109">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="ae1a2-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ae1a2-110">表示 `input` 的 `Result`。</span><span class="sxs-lookup"><span data-stu-id="ae1a2-110">A `Result` representing the `input`.</span></span>