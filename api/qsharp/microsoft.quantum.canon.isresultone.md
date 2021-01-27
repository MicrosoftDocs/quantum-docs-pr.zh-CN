---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: f259c21e6cc0a4886332e9ffcb546e527ec7def1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840330"
---
# <a name="isresultone-function"></a><span data-ttu-id="93c01-102">IsResultOne 函数</span><span class="sxs-lookup"><span data-stu-id="93c01-102">IsResultOne function</span></span>

<span data-ttu-id="93c01-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="93c01-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="93c01-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93c01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93c01-105">测试给定结果值是否等于 `One` 。</span><span class="sxs-lookup"><span data-stu-id="93c01-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="93c01-106">输入</span><span class="sxs-lookup"><span data-stu-id="93c01-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="93c01-107">输入：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="93c01-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="93c01-108">`Result` 要测试的值。</span><span class="sxs-lookup"><span data-stu-id="93c01-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="93c01-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="93c01-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93c01-110">如果等于，则返回 `true` `input` `One` 。</span><span class="sxs-lookup"><span data-stu-id="93c01-110">Returns `true` if `input` is equal to `One`.</span></span>