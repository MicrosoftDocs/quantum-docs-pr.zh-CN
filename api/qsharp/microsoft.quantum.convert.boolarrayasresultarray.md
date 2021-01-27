---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834194"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="32833-102">BoolArrayAsResultArray 函数</span><span class="sxs-lookup"><span data-stu-id="32833-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="32833-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="32833-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="32833-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32833-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32833-105">将 `Bool[]` 类型转换为 `Result[]` 类型，其中 `true` 映射到 `One` 并 `false` 映射到 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="32833-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="32833-106">输入</span><span class="sxs-lookup"><span data-stu-id="32833-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="32833-107">输入： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="32833-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="32833-108">`Bool[]` 要转换的。</span><span class="sxs-lookup"><span data-stu-id="32833-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="32833-109">输出：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="32833-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="32833-110">表示 `input` 的 `Result[]`。</span><span class="sxs-lookup"><span data-stu-id="32833-110">A `Result[]` representing the `input`.</span></span>