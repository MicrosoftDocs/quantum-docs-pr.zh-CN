---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b1e7cf6324a2a90f10b6aa93811f2df60fe3afbd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840313"
---
# <a name="isresultzero-function"></a><span data-ttu-id="d2e16-102">IsResultZero 函数</span><span class="sxs-lookup"><span data-stu-id="d2e16-102">IsResultZero function</span></span>

<span data-ttu-id="d2e16-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d2e16-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d2e16-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2e16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2e16-105">测试给定结果值是否等于 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="d2e16-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="d2e16-106">输入</span><span class="sxs-lookup"><span data-stu-id="d2e16-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="d2e16-107">输入：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="d2e16-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="d2e16-108">`Result` 要测试的值。</span><span class="sxs-lookup"><span data-stu-id="d2e16-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d2e16-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="d2e16-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d2e16-110">如果等于，则返回 `true` `input` `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="d2e16-110">Returns `true` if `input` is equal to `Zero`.</span></span>