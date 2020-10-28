---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: 790551690cfba42df4cf7aa77e53e303050bdf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696034"
---
# <a name="isresultzero-function"></a><span data-ttu-id="1499a-102">IsResultZero 函数</span><span class="sxs-lookup"><span data-stu-id="1499a-102">IsResultZero function</span></span>

<span data-ttu-id="1499a-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1499a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1499a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1499a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1499a-105">测试给定结果值是否等于 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="1499a-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="1499a-106">输入</span><span class="sxs-lookup"><span data-stu-id="1499a-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="1499a-107">输入： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="1499a-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="1499a-108">`Result` 要测试的值。</span><span class="sxs-lookup"><span data-stu-id="1499a-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1499a-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="1499a-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1499a-110">如果等于，则返回 `true` `input` `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="1499a-110">Returns `true` if `input` is equal to `Zero`.</span></span>