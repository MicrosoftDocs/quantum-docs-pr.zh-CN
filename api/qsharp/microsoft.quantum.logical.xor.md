---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700516"
---
# <a name="xor-function"></a><span data-ttu-id="683f1-102">Xor 函数</span><span class="sxs-lookup"><span data-stu-id="683f1-102">Xor function</span></span>

<span data-ttu-id="683f1-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="683f1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="683f1-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="683f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="683f1-105">返回两个值的布尔互斥析取。</span><span class="sxs-lookup"><span data-stu-id="683f1-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="683f1-106">输入</span><span class="sxs-lookup"><span data-stu-id="683f1-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="683f1-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="683f1-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="683f1-108">要考虑的第一个值。</span><span class="sxs-lookup"><span data-stu-id="683f1-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="683f1-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="683f1-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="683f1-110">要考虑的第二个值。</span><span class="sxs-lookup"><span data-stu-id="683f1-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="683f1-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="683f1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="683f1-112">`true` 当且仅当和中只有 `a` 一个 `b` 为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="683f1-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>