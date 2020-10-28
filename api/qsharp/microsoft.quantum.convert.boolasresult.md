---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: eea6c062afdbb3172e63261e52a82e2576c14011
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695685"
---
# <a name="boolasresult-function"></a><span data-ttu-id="5c889-102">BoolAsResult 函数</span><span class="sxs-lookup"><span data-stu-id="5c889-102">BoolAsResult function</span></span>

<span data-ttu-id="5c889-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="5c889-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="5c889-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c889-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c889-105">将 `Bool` 类型转换为 `Result` 类型，其中 `true` 映射到 `One` 并 `false` 映射到 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="5c889-105">Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a><span data-ttu-id="5c889-106">输入</span><span class="sxs-lookup"><span data-stu-id="5c889-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="5c889-107">输入：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="5c889-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c889-108">`Bool` 要转换的。</span><span class="sxs-lookup"><span data-stu-id="5c889-108">`Bool` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="5c889-109">输出： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="5c889-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="5c889-110">表示 `input` 的 `Result`。</span><span class="sxs-lookup"><span data-stu-id="5c889-110">A `Result` representing the `input`.</span></span>