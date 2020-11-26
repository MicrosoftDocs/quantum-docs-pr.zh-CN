---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224456"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="08934-102">BoolArrayAsResultArray 函数</span><span class="sxs-lookup"><span data-stu-id="08934-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="08934-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="08934-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="08934-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08934-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08934-105">将 `Bool[]` 类型转换为 `Result[]` 类型，其中 `true` 映射到 `One` 并 `false` 映射到 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="08934-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="08934-106">输入</span><span class="sxs-lookup"><span data-stu-id="08934-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="08934-107">输入： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="08934-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="08934-108">`Bool[]` 要转换的。</span><span class="sxs-lookup"><span data-stu-id="08934-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="08934-109">输出：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="08934-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="08934-110">表示 `input` 的 `Result[]`。</span><span class="sxs-lookup"><span data-stu-id="08934-110">A `Result[]` representing the `input`.</span></span>