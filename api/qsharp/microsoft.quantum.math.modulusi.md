---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847288"
---
# <a name="modulusi-function"></a><span data-ttu-id="3aa5a-102">ModulusI 函数</span><span class="sxs-lookup"><span data-stu-id="3aa5a-102">ModulusI function</span></span>

<span data-ttu-id="3aa5a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3aa5a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3aa5a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3aa5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3aa5a-105">计算模的规范 residue `value` `modulus` 。</span><span class="sxs-lookup"><span data-stu-id="3aa5a-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="3aa5a-106">输入</span><span class="sxs-lookup"><span data-stu-id="3aa5a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="3aa5a-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3aa5a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3aa5a-108">计算 residue 的值</span><span class="sxs-lookup"><span data-stu-id="3aa5a-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="3aa5a-109">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3aa5a-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3aa5a-110">Residues 所采用的模数必须为正数</span><span class="sxs-lookup"><span data-stu-id="3aa5a-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="3aa5a-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3aa5a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3aa5a-112">0之间的整数 $r $， `modulus - 1` 这可 `value - r` 被模数整除</span><span class="sxs-lookup"><span data-stu-id="3aa5a-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="3aa5a-113">备注</span><span class="sxs-lookup"><span data-stu-id="3aa5a-113">Remarks</span></span>

<span data-ttu-id="3aa5a-114">此函数的行为与运算符 `%` 在 c # 和 Q # 中的行为方式有所不同，因为结果中始终是0到之间的一个非负整数 `modulus - 1` ，即使值为负。</span><span class="sxs-lookup"><span data-stu-id="3aa5a-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>