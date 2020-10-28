---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: fa8845fd92e5c16b4ff15436caf42df4f1e151cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696037"
---
# <a name="isresultone-function"></a><span data-ttu-id="530a2-102">IsResultOne 函数</span><span class="sxs-lookup"><span data-stu-id="530a2-102">IsResultOne function</span></span>

<span data-ttu-id="530a2-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="530a2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="530a2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="530a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="530a2-105">测试给定结果值是否等于 `One` 。</span><span class="sxs-lookup"><span data-stu-id="530a2-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="530a2-106">输入</span><span class="sxs-lookup"><span data-stu-id="530a2-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="530a2-107">输入： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="530a2-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="530a2-108">`Result` 要测试的值。</span><span class="sxs-lookup"><span data-stu-id="530a2-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="530a2-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="530a2-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="530a2-110">如果等于，则返回 `true` `input` `One` 。</span><span class="sxs-lookup"><span data-stu-id="530a2-110">Returns `true` if `input` is equal to `One`.</span></span>