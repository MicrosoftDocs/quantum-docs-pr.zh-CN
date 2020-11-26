---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b4e9b62b20e12a8dce544ce16dcddcf15fdf2680
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206521"
---
# <a name="isresultzero-function"></a><span data-ttu-id="87c7f-102">IsResultZero 函数</span><span class="sxs-lookup"><span data-stu-id="87c7f-102">IsResultZero function</span></span>

<span data-ttu-id="87c7f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="87c7f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="87c7f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87c7f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87c7f-105">测试给定结果值是否等于 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="87c7f-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="87c7f-106">输入</span><span class="sxs-lookup"><span data-stu-id="87c7f-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="87c7f-107">输入：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="87c7f-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="87c7f-108">`Result` 要测试的值。</span><span class="sxs-lookup"><span data-stu-id="87c7f-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="87c7f-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="87c7f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="87c7f-110">如果等于，则返回 `true` `input` `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="87c7f-110">Returns `true` if `input` is equal to `Zero`.</span></span>