---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 9de7ca64992e0a4d73c1d00218b3eab4ab545a1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832567"
---
# <a name="resultasbool-function"></a><span data-ttu-id="81286-102">ResultAsBool 函数</span><span class="sxs-lookup"><span data-stu-id="81286-102">ResultAsBool function</span></span>

<span data-ttu-id="81286-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="81286-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="81286-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81286-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81286-105">将 `Result` 类型转换为 `Bool` 类型，其中 `One` 映射到 `true` 并 `Zero` 映射到 `false` 。</span><span class="sxs-lookup"><span data-stu-id="81286-105">Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="81286-106">输入</span><span class="sxs-lookup"><span data-stu-id="81286-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="81286-107">输入：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="81286-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="81286-108">`Result` 要转换的。</span><span class="sxs-lookup"><span data-stu-id="81286-108">`Result` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="81286-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="81286-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="81286-110">表示 `input` 的 `Bool`。</span><span class="sxs-lookup"><span data-stu-id="81286-110">A `Bool` representing the `input`.</span></span>