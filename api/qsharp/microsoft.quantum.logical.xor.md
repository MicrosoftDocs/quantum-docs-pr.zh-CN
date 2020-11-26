---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197086"
---
# <a name="xor-function"></a><span data-ttu-id="e7184-102">Xor 函数</span><span class="sxs-lookup"><span data-stu-id="e7184-102">Xor function</span></span>

<span data-ttu-id="e7184-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e7184-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e7184-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7184-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7184-105">返回两个值的布尔互斥析取。</span><span class="sxs-lookup"><span data-stu-id="e7184-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="e7184-106">输入</span><span class="sxs-lookup"><span data-stu-id="e7184-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="e7184-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e7184-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e7184-108">要考虑的第一个值。</span><span class="sxs-lookup"><span data-stu-id="e7184-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="e7184-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e7184-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e7184-110">要考虑的第二个值。</span><span class="sxs-lookup"><span data-stu-id="e7184-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e7184-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="e7184-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e7184-112">`true` 当且仅当和中只有 `a` 一个 `b` 为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="e7184-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>