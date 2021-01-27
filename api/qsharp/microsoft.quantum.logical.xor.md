---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848456"
---
# <a name="xor-function"></a><span data-ttu-id="303be-102">Xor 函数</span><span class="sxs-lookup"><span data-stu-id="303be-102">Xor function</span></span>

<span data-ttu-id="303be-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="303be-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="303be-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="303be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="303be-105">返回两个值的布尔互斥析取。</span><span class="sxs-lookup"><span data-stu-id="303be-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="303be-106">输入</span><span class="sxs-lookup"><span data-stu-id="303be-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="303be-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="303be-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="303be-108">要考虑的第一个值。</span><span class="sxs-lookup"><span data-stu-id="303be-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="303be-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="303be-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="303be-110">要考虑的第二个值。</span><span class="sxs-lookup"><span data-stu-id="303be-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="303be-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="303be-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="303be-112">`true` 当且仅当和中只有 `a` 一个 `b` 为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="303be-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>